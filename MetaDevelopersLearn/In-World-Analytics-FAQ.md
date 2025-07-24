# In-World Analytics FAQ

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/in-world-analytics-faq)

## Getting Started

#### Where can I view the API Reference for Analytics?

Go to [https://developers.meta.com/horizon-worlds/reference/2.0.0/](https://developers.meta.com/horizon-worlds/reference/2.0.0/) to see the Meta Horizon Worlds API Reference and select **analytics** on the left.

#### Why can’t I see the API area in Script Settings?

If you do not see these API options, you will need to import the horizon/core API by adding a script to your world. When you add a script to your world with the plus button, it will populate with code which includes the `import \* as hz from horizon/core;` which will enable access to the API settings.

#### How do I register my world to use the API?

If you are importing the TurboAnalytics.ts script from one of the demo worlds or shared assets folder, make sure it is attached to an entity (like a textbox or script holder) in your world.

## Turbo Actions

#### How do Turbo Actions relate to AnalyticsManager event handlers?

Most Turbo Actions represent a 1:1 mapping with each AnalyticsManager event handler. Some actions are simple pass-throughs to logging, whereas others may affect the Player State in critical ways.

#### Do Turbo Actions affect the Player State?

Certain Areas designated as Lobbies might automatically change the TurboState of a player. Similarly, certain automated rules are triggered when an AFK Event is sent.

#### How do I send payloads to the Turbo Engine?

To send payloads to the engine, use the AnalyticsManager as a wrapper. A concise helper function has been provided to easily call the static instance assigned. Each function has an implied Turbo Action and ActionData based on the Payload type. // Analytics Manager Code (TurboAnalytics.ts)

```
onFrictionHit(player: hz.Player) {
  const turboData: FrictionHitData = {
    player,
    frictionItemKey: this.frictionKey,
    frictionIsImplied: false,
    frictionNumTimes: 1,
    frictionAmount: 1
  };
  Analytics()?.sendFrictionHit(turboData);
}
```

#### Can Turbo Analytics get information from local scripts?

Turbo Analytics methods must be called from a script in Default execution mode. To send events from a local script to the analytics manager, you will need bridge broadcasts to subscribe to the event and log the payload. Without a bridge broadcast, Turbo Analytics will not track local events.

#### Can I track which object a player was interacting with when they performed an action?

Yes, Turbo Analytics can help you gather this type of data. For example, when a player grabs a weapon, Turbo Engine captures that data point as part of a payload. When they use that weapon to KO another player, the data of which weapon they used is also included in the player data. Note: For privacy reasons, there is a two day delay on this type of data arriving in the Creator Insights portal, and your world needs to have 100 daily active users to access this level of information.

## Turbo Modules

#### What do Turbo Modules Track?

Enabled modules get processed and send associated events and data to the analytics engine. **Note**: To ensure optimal performance, only enable the modules that you need for your specific use case to avoid decreased performance.

### Turbo Module Descriptions

| Module | Description |
| --- | --- |
| Abilities | Abilities are special powers in games, distinct from weapons, with limited use and cooldowns. |
| AFK | Tracks when players are Away from Keyboard (AFK) and its impact on gameplay. |
| Area | Defines physical sections in a world, tracking player movement and time spent. |
| Discovery | Logs when players discover or experience new things in the game. |
| Friction | Identifies negative experiences that slow player progress. |
| Death | Tracks player knockouts (KOs) in PvP and PvE games. |
| KOEnemy | Logs when a player defeats a non-player enemy. |
| KOPlayer | Records player-versus-player knockouts. |
| LevelUp | Tracks player progression and leveling up events. |
| Rewards | Monitors rewards like collectibles and points earned by players. |
| Rounds | Tracks game rounds and player participation. |
| Stages | Breaks down player progress within stages of a game. |
| Sections | Monitors specific sections within a stage for detailed analysis. |
| Tasks | Measures specific activities or steps players complete. |
| WeaponEquip | Logs when players equip weapons. |
| WeaponGrabAndRelease | Tracks when players grab and release weapons, including usage time. |
| Wearables | Monitors when players equip and detach wearables |

## Understanding Areas

### How can I implement Turbo Areas?

There are two ways to implement Turbo Areas:

*   Using TurboAreaTrigger (Recommended): Leverage the TurboAreaTrigger provided as part of the Turbo Assets.

*   Use `Turbo.send(...)` within the TypeScript: If the Game Engine presumes when a player enters or exits an area, creators can simply add the `Turbo.send()` call to their existing game code and pass the relevant data.

```
// Analytics Manager Code (TurboAnalytics.ts)
sendAreaEnter(turboData: AreaEnterPayload): boolean {
  if (player.id == this.serverPlayerID) {
    return false
  };
  return Turbo.send(TurboEvents.OnAreaEnter, player, turboData as AreaEnterPayload);
}
```

### How many areas can I have in my world?

It’s recommended to have between 5-15 unique areas (keys) in your world. This range provides a good balance between getting useful insights and avoiding unnecessary granularity.

## Viewing and Managing Analytics

## Where can I view tracked analytics?

The analytics for Turbo Modules are viewable within Horizon Creator Portal. For more detailed guidance on individual analytics see [World Analytics](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/world-analytics) .

### Can tables be created with the data?

Yes, Turbo Modules support the creation of tables based on the data collected. You can export your world’s data from the dashboard as CSV files.

### Is there a limit to the number of metrics we can track?

While there is no explicit limit mentioned, it’s important to only use the necessary modules to help maintain performance and efficiency.

### Why isn’t any data showing on my Dashboard?

If you’re not seeing the expected data in your analytics, it may be because your world hasn’t met the minimum requirements. To access full analytics, your world must be published and have at least 10 daily visitors.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 