# Capturing Custom In-World Analytics

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/custom-in-world-analytics)

To track additional data and gain more control over [In-World Analytics](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/using-in-world-analytics/) , the Analytics API lets you create an analytics manager that is customized for your world. This allows you to collect deeper analytics and optimize data collection towards the design of your world beyond what the [helper methods](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/using-in-world-analytics#sending-turbo-actions) provide in the Turbo Analytics module.

When sending built-in analytics events to the In-World Analytics system, helper methods such as the `sendDiscoveryMade()` method provide stronger type safety, predictability, and require less coding than calling the Analytics API directly. However, these are wrapper methods for Analytics API calls. The Analytics API allows you to send analytics events directly using your own wrapper methods, which provides more flexibility and control.

## Analytics API

To implement an analytics manager, the Analytics API provides the [Turbo](/horizon-worlds/reference/2.0.0/analytics_turbo) variable, which is a shared instance of the `TurboManager` class. The `TurboManager` class provides several important methods to call from your analytics manager:

*   `Turbo.register(component, configs)`
    

*   `Turbo.send(event, payload)`
    

The [TurboEvents](/horizon-worlds/reference/2.0.0/analytics_turboevents) variable provides access to the available built-in Turbo events. It also includes the available data fields for the payloads of each event type. The Type Alias section of the Analytics API documentation lists the payload types for each Turbo event. For example, the [DamageEnemyPayload](/horizon-worlds/reference/2.0.0/analytics_damageenemypayload) type is the payload type for the `TurboEvents.OnDamageEnemy` event.

### Setting up the API

Before using the Analytics API, you must enable the **horizon/analytics** package and **TurboAnalytics** module in Desktop editor.

For detailed steps, see [Adding In-World Analytics](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/using-in-world-analytics#adding-in-world-analytics-to-a-world) .

## Creating an analytics manager

To create an analytics manager, you must complete these steps:

*   Add an [entity](/horizon-worlds/reference/2.0.0/core_entity) to your world that you can attach to your analytics manager script. This can be an empty entity.
    

*   Create a script for your analytics manager by extending the [Component](/horizon-worlds/reference/2.0.0/core_component) class.
    

*   Import the `horizon/core` and `horizon/analytics` modules based on the types you’re using.
    

*   Configure your [Turbo settings](#configure-turbo-settings) based on your use case.
    

*   Register your analytics manager class with the Turbo interface by calling the [Turbo.register()](/horizon-worlds/reference/2.0.0/analytics_turbo) method and passing your component and [Turbo settings](#configure-turbo-settings) to the method.
    

*   In Desktop editor, attach the script to the entity you created.
    

This example demonstrates how to create and register an analytics manager in TypeScript.

```
import * as hz from 'horizon/core';
import {Turbo, TurboDefaultSettings} from 'horizon/analytics';

export const areaEntered = new hz.LocalEvent<{ player: hz.Player, area: string }>("areaEntered");

export class AnalyticsManager extends hz.Component {
 static propsDefinition = {
   overrideDebug: { type: hz.PropTypes.Boolean, default: false },
 };
 static s_instance: AnalyticsManager;
 serverPlayer!: hz.Player;
 serverPlayerID!: number;
 overrideDebug!: boolean;

 start() {
   Turbo.register(this, TurboDefaultSettings);
   AnalyticsManager.s_instance = this;
   this.subscribeToEvents();
  }

 // You can group event subscriptions in this method.
 private subscribeToEvents() {

 }
}
```

### Configuring Turbo settings

You can disable unused functionality and configure other settings for an analytics manager. The settings are defined by the [ITurboSettings](/horizon-worlds/reference/2.0.0/analytics_iturbosettings) interface and many of them correspond to [Turbo actions](/horizon-worlds/reference/2.0.0/analytics_action) . If you disable any Turbo settings, the corresponding Turbo actions are also disabled.

By default, all Turbo actions are enabled. The default settings are defined by the [TurboDefaultSettings](/horizon-worlds/reference/2.0.0/analytics_turbodefaultsettings) variable.

To use the default Turbo settings, in the [Component.start()](/horizon-worlds/reference/2.0.0/core_component) method, pass a `TurboDefaultSettings` object to the `Turbo.register()` method.

Here’s a an example that sets the Turbo settings to the default settings in the `register()` method.

```
Turbo.register(this, TurboDefaultSettings);
```

To configure your Turbo settings, update the relevant properties in an `ITurboSettings` object and pass it to the `Turbo.register()` method in the [Component.start()](/horizon-worlds/reference/2.0.0/core_component#start) method.

This example demonstrates how to disable several Turbo settings.

```
start() {
   const turboSettings: ITurboSettings = {
    useAFK: false,
    useFriction: false,
    useHeartBeats
  };

   Turbo.register(this, turboSettings);
   AnalyticsManager.s_instance = this;
   this.subscribeToEvents();
  }
```

### Sending Turbo events

When capturing analytics, you can send events by calling the `Turbo.send(event, payload)` method and passing it a [Turbo event](/horizon-worlds/reference/2.0.0/analytics_turboevents) and corresponding payload.

Here’s a description of the **parameters**:

*   event: The name of the event to send. The event must be a member of the [TurboEvents](/horizon-worlds/reference/2.0.0/analytics_turboevents) variable, which lists all available analytics events.
    

*   payload: The event data to send. The payloads for Turbo events are accessed using type aliases such as the [DeathPayload](/horizon-worlds/reference/2.0.0/analytics_deathpayload) type, which is sent by the `OnDeath` event. The available payload fields are listed for each event in the `TurboEvents` variable. For example, the `OnDeathByPlayer` event includes the mandatory `killedByPlayer` field and an optional `KilledByWeaponKey` field. You muse also add the `player: string` field to the payload. For example `player: this.serverPlayer`. This field is not defined in the `TurboEvents` variable because it is defined in the underlying type, so it is required.
    

For example, sending a `TurboEvents.OnLevelUp` event with a `LevelUpPayload` looks like the following.

```
Turbo.send(TurboEvents.OnLevelUp, {
  player: this.serverPlayer,
  playerLevel: 10,
  playerTitle: `Gladiator`
} as LevelUpPayload);
```

In most cases, you call the `send()` method from an event listener inside the [Component.start()](/horizon-worlds/reference/2.0.0/core_component) method that is called in your analytics manager.

This example implements an analytics manager that sends the `OnAreaEnter` event when the current player enters the lobby area of the world.

```
import * as hz from 'horizon/core';
import {Turbo, TurboDefaultSettings, TurboEvents, AreaEnterPayload} from 'horizon/analytics';

export const areaEntered = new hz.LocalEvent<{ player: hz.Player, area: string }>("areaEntered");

export class AnalyticsManager extends hz.Component {
 static propsDefinition = {
   overrideDebug: { type: hz.PropTypes.Boolean, default: false },
 };
 static s_instance: AnalyticsManager;
 serverPlayer!: hz.Player;
 serverPlayerID!: number;
 overrideDebug!: boolean;

 start() {
   Turbo.register(this, TurboDefaultSettings);
   AnalyticsManager.s_instance = this;
   this.subscribeToEvents();
  }

 // You can group event subscriptions in here.
 private subscribeToEvents() {
   // This subscription sends a Turbo Analytics event.
   this.connectLocalBroadcastEvent(areaEntered, (data) => {
     Turbo.send(TurboEvents.OnAreaEnter, {
      player: this.serverPlayer,
      actionArea: "Lobby",
      actionAreaIsLobbySection: true,
      actionAreaIsPlayerReadyZone: false } as AreaEnterPayload
     );
  });
 }
}
```

This example creates and sends the payload for an `OnAreaEnter` event as a variable instead of passing the fields inline in the method call. Despite sending the same type of payload as the previous example, this payload includes a different set of optional fields.

```
const areaEnterPayload: AreaEnterPayload = {
    actionArea: `CombatTutorial`,
    actionAreaIsLobbySection: false,
    actionAreaIsPlayerReadyZone: true,
    turboState: ParticipationEnum.IN_ROUND,
    nextArea: {
      actionArea: `Stage1`,
      actionAreaIsLobbySection: false,
      actionAreaIsPlayerReadyZone: true,
    },
    player: this.serverPlayer
  };

   // This subscription sends a Turbo Analytics event.
   this.connectLocalBroadcastEvent(areaEntered, (data) => {
    Turbo.send(TurboEvents.OnAreaEnter, areaEnterPayload);
   });
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 