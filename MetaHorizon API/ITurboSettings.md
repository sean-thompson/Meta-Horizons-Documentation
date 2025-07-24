# ITurboSettings Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/analytics_iturbosettings)

The available settings for a [Turbo](/horizon-worlds/reference/2.0.0/analytics_turbo) instance including the ability to enable and disable specific types of analytics tracking. Many of these settings configure a corresponding set of Turbo [actions](/horizon-worlds/reference/2.0.0/analytics_action) and [TurboEvents](/horizon-worlds/reference/2.0.0/analytics_turboevents) .

## Signature

```
export interface ITurboSettings
```

## Remarks

The [TurboDefaultSettings](/horizon-worlds/reference/2.0.0/analytics_turbodefaultsettings) variable defines the default settings.

  

To apply your Turbo settings, populate your `ITurboSettings` object and pass it to the `Turbo.register(component, configs)` method. For details, see the [Turbo](/horizon-worlds/reference/2.0.0/analytics_turbo) variable.

## Examples

This example demonstrates how to disable several Turbo settings when calling the Turbo.register() method.

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

## Properties

<table>
  <tbody>
    <tr>
      <td>**debug**</td>
      <td>`true`

 to enable Turbo debugging functionality, such as logs and tools; `false` to disable it.

Signature

```
debug: boolean;
```</td>
    </tr>
    <tr>
      <td>**eventsForWeaponGrabAndRelease**</td>
      <td>`true`

 to enable logging for weapon equip and release events on the backend server; `false` to disable it.

Signature

```
eventsForWeaponGrabAndRelease: boolean;
```

Remarks

To use this setting, you must enable the property.

  

Player state updates can still reflect current the weapon and timers without logging the actual events.</td>
    </tr>
    <tr>
      <td>**eventsForWearableEquipAndRelease**</td>
      <td>`true`

 to enable logging for wearable equip and release events on the backend server; `false` to disable it.

Signature

```
eventsForWearableEquipAndRelease: boolean;
```

Remarks

To use this setting, you must enable the [ITurboSettings.useWearableEquipAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usewearableequipandrelease) property.

  

Player state updates can still reflect current the wearables and timers without logging the actual events.</td>
    </tr>
    <tr>
      <td>**experiments**</td>
      <td>A method that enables a set of experiments for the player.

Signature

```
experiments: Set<string>;
```</td>
    </tr>
    <tr>
      <td>**frictionNoKOsTimerSeconds**</td>
      <td>A timer that creates a friction event whenever no player kills occur within the specified duration during gameplay. The timer specified in seconds.

Signature

```
frictionNoKOsTimerSeconds: number;
```

Remarks

The property must be `true`; otherwise, this timer is ignored.</td>
    </tr>
    <tr>
      <td>**gameMode**</td>
      <td>The name of a custom game mode, such as arena, or adventure.

Signature

```
gameMode: string;
```

Remarks

The property must be enabled to track game mode events and data.</td>
    </tr>
    <tr>
      <td>**heartbeatFrequencySeconds**</td>
      <td>The frequency, in seconds, for capturing a heartbeat event for each active player.

Signature

```
heartbeatFrequencySeconds: number;
```

Remarks

The setting must be enabled to track heartbeat events.</td>
    </tr>
    <tr>
      <td>**maxAFKSecondsBeforeRemove**</td>
      <td>The number of seconds before deleting an AFK player.

Signature

```
maxAFKSecondsBeforeRemove: number;
```

Remarks

Deleting AFK players after the specified duration can help avoid memory leak issues.</td>
    </tr>
    <tr>
      <td>**maxFrictionNoKOEvents**</td>
      <td>The maximum number of times to send friction events due to no player kills occuring within the timer.

Signature

```
maxFrictionNoKOEvents: number;
```

Remarks

The setting must be enabled in order to track this event type.</td>
    </tr>
    <tr>
      <td>**playerInitialArea**</td>
      <td>The name of the initial area where a player first enters a world.

Signature

```
playerInitialArea: string;
```</td>
    </tr>
    <tr>
      <td>**playerInitialState**</td>
      <td>The player's initial participation state when a player first enters a world.

Signature

```
playerInitialState: ParticipationEnum;
```</td>
    </tr>
    <tr>
      <td>**turboUpdateSeconds**</td>
      <td>The frequency, in seconds, for Turbo Manger to update the game state.

Signature

```
turboUpdateSeconds: number;
```

Remarks

Setting this proprety lower affects performance; higher impacts accuracy.</td>
    </tr>
    <tr>
      <td>**useAFK**</td>
      <td>`true`

 to track AFK enter and AFK exit events and data; `false` otherwise.

Signature

```
useAFK: boolean;
```

Remarks

This setting enables the `AFK_ENTER` and 

`AFK_EXIT` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useAbilities**</td>
      <td>`true`

 to track abilities events and data; `false` otherwise.

Signature

```
useAbilities: boolean;
```</td>
    </tr>
    <tr>
      <td>**useArmor**</td>
      <td>`true`

 to track armor events and data; `false` otherwise.

Signature

```
useArmor: boolean;
```

Remarks

This setting enables the `ARMOR_EQUIP` and 

`ARMOR_DEQUIP` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useDamage**</td>
      <td>`true`

 to track damage events and data; `false` otherwise.

Signature

```
useDamage: boolean;
```

Remarks

This setting enables the `DAMAGE_ENEMY` and 

`DAMAGE_PLAYER` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useDiscovery**</td>
      <td>`true`

 to track events and data for player discoveries; `false` otherwise.

Signature

```
useDiscovery: boolean;
```

Remarks

This setting enables the 

`DISCOVERY_MADE` [action](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useForward**</td>
      <td>`true`

 to log forward vectors with each player action; `false` otherwise.

Signature

```
useForward: boolean;
```</td>
    </tr>
    <tr>
      <td>**useFriction**</td>
      <td>`true`

 to track friction events and data; `false` otherwise.

Signature

```
useFriction: boolean;
```

Remarks

This setting enables the `FRICTION_HIT` and 

`FRICTION_CAUSED` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .

  

Friction events can be derived or deliberate, and slow player pogression.</td>
    </tr>
    <tr>
      <td>**useFrictionNoKOs**</td>
      <td>`true`

 to track friction events and data caused when no player kills occur within a specified duration; `false` otherwise.

Signature

```
useFrictionNoKOs: boolean;
```

Remarks

This setting enables events and data tracking based on the the [ITurboSettings.frictionNoKOsTimerSeconds](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#frictionnokostimerseconds) property.</td>
    </tr>
    <tr>
      <td>**useGameMode**</td>
      <td>`true`

 to track custom game mode events and data; `false` otherwise.

Signature

```
useGameMode: boolean;
```

Remarks

This setting enables the [ITurboSettings.gameMode](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#gamemode) property.

  

Game modes are custom variations of the game, such as arena and guild wars.</td>
    </tr>
    <tr>
      <td>**useHeartbeats**</td>
      <td>`true`

 to track track heartbeat events and data at the specified duration; `false` otherwise.

Signature

```
useHeartbeats: boolean;
```

Remarks

The [ITurboSettings.heartbeatFrequencySeconds](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#heartbeatfrequencyseconds) property specifies the tracking duration.</td>
    </tr>
    <tr>
      <td>**useLevelUp**</td>
      <td>`true`

 to track player level and level up events and data; `false` otherwise.

Signature

```
useLevelUp: boolean;
```

Remarks

This setting enables the 

`LEVEL_UP` [action](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useQuests**</td>
      <td>`true`

 to enable quest and achievement analytics; `false` otherwise.

Signature

```
useQuests: boolean;
```</td>
    </tr>
    <tr>
      <td>**useRewards**</td>
      <td>`true`

 to track rewards events and data; `false` otherwise.

Signature

```
useRewards: boolean;
```

Remarks

This setting can track data such as collectibles, XP, points, and bonuses. Reward tracking ensures rewards are being received and provide insight into how, when, and why those rewards are earned or missed.</td>
    </tr>
    <tr>
      <td>**useRotation**</td>
      <td>`true`

 to log rotation using Eurler angles with each player action; `false` otherwise.

Signature

```
useRotation: boolean;
```</td>
    </tr>
    <tr>
      <td>**useRounds**</td>
      <td>`true`

 to track events and data for rounds; `false` otherwise.

Signature

```
useRounds: boolean;
```

Remarks

A round is a full completion of a game and represent the overall loop of funnel progression analytics, which consists of rounds, stages, and sections.

  

This setting enables the `ROUND_ABANDONED`, 

`ROUND_END`, `ROUND_LOST`, 

`ROUND_REJOINED`, `ROUND_START`, 

`ROUND_STATS`, and 

`ROUND_WIN` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useSections**</td>
      <td>`true`

 to track events and data for sections; `false` otherwise.

Signature

```
useSections: boolean;
```

Remarks

Sections are subdivisions of in funnel progression analytics. Sections track progression when a player starts, completes, or enters a subsection of a stage, wave, or level. The purpose of this setting is to track more granular portions of the areas where an event occurs or a player is navigating.

  

This setting enables the `SECTION_ABANDONED`, 

`SECTION_END`, `SECTION_RESTART`, 

`SECTION_START`, and 

`SECTION_STATS` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useStages**</td>
      <td>`true`

 to track events and data for stages; `false` otherwise.

Signature

```
useStages: boolean;
```

Remarks

Stages are subdivisions of in funnel progression analytics.

  

This setting enables the `STAGE_ABANDONED`, 

`STAGE_END`, `STAGE_PROGRESS`, 

`STAGE_RESTART`, `STAGE_START`, and 

`STAGE_STATS` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useTasks**</td>
      <td>`true`

 to track events and data for tasks and task steps, such as activities, challenges, and puzzles. Otherwise, `false`.

Signature

```
useTasks: boolean;
```

Remarks

Tasks and task steps were designed to measure specific activities where a player has a series of steps to follow. In comparison to rounds, stages, and sections, tasks are more discrete units that can occur within those items.

  

This setting enables the `TASK_ABANDONED`, 

`TASK_END`, `TASK_FAIL`, 

`TASK_START`, `TASK_STEP_END`, 

`TASK_STEP_FAIL`, `TASK_STEP_START`, 

`TASK_STEP_SUCCESS`, and 

`TASK_SUCCESS` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .</td>
    </tr>
    <tr>
      <td>**useTeamAndRole**</td>
      <td>`true`

 to track team and role based data using the player state; `false` otherwise.

Signature

```
useTeamAndRole: boolean;
```</td>
    </tr>
    <tr>
      <td>**useTransforms**</td>
      <td>`true`

 to continuously track player position, rotation, distances, and other player transforms. `false` to only calculate player transforms for each action.

Signature

```
useTransforms: boolean;
```</td>
    </tr>
    <tr>
      <td>**useWeaponEquip**</td>
      <td>`true`

 to track when a player equips a weapon; `false` otherwise.

Signature

```
useWeaponEquip: boolean;
```

Remarks

This setting enables the 

`WEARABLE_EQUIP` [action](/horizon-worlds/reference/2.0.0/analytics_action) .

  

Weapon grab and release analytics are enabled with the [ITurboSettings.useWeaponGrabAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweapongrabandrelease) property.

  

Weapon usr analytics are enabled with the [ITurboSettings.useWeapons](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweapons) property.</td>
    </tr>
    <tr>
      <td>**useWeaponGrabAndRelease**</td>
      <td>`true`

 to enable tracking for weapon grab and release events and data. `false` to disable it.

Signature

```
useWeaponGrabAndRelease: boolean;
```

Remarks

This setting enables the `WEAPON_GRAB` and 

`WEAPON_RELEASE` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .

  

When players grab and release weapons, it updates weapon utilization timers and the current weapons data.

  

The property enables logging the individual grab and release events to the backend server.</td>
    </tr>
    <tr>
      <td>**useWeapons**</td>
      <td>`true`

 to track weapon use events and data; `false` otherwise.

Signature

```
useWeapons: boolean;
```

Remarks

This settings enables the 

`WEAPON_FIRED` [action](/horizon-worlds/reference/2.0.0/analytics_action) .

  

Weapon grab and release analytics are enabled with the [ITurboSettings.useWeaponGrabAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweapongrabandrelease) property.

  

Weapon equip analytics are enabled with the [ITurboSettings.useWeaponEquip](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweaponequip) property.</td>
    </tr>
    <tr>
      <td>**useWearableEquipAndRelease**</td>
      <td>`true`

 to track equip and release events and data for wearables; `false` otherwise.

Signature

```
useWearableEquipAndRelease: boolean;
```

Remarks

This setting enables the `WEARABLE_EQUIP` and 

`WEARABLE_RELEASE` [actions](/horizon-worlds/reference/2.0.0/analytics_action) .

  

The [ITurboSettings.eventsForWearableEquipAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#eventsforwearableequipandrelease) property enables logging the individual grab and release events to the backend server.</td>
    </tr>
    <tr>
      <td>**useWearables**</td>
      <td>`true`

 to track events and data for a wearables that are currently eqquiped by a player. `false` to disable it.

Signature

```
useWearables: boolean;
```

Remarks

The [ITurboSettings.useWearableEquipAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usewearableequipandrelease) property enables tracking of equip and release events for wearables.</td>
    </tr>
  </tbody>
</table>