# Using In-World Analytics

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/using-in-world-analytics)

## Getting Started With In-World Analytics

Use the following resources to learn about analytics before implementing it for your use case:

*   The [My First World tutorial](/horizon-worlds/learn/documentation/get-started/create-your-first-world) includes an optional step which offers an introduction to some of the basics of implementing In-World Analytics.

*   The [Chop ‘n’ Pop Graveyard Bash Analytics tutorial](/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-analytics-tutorial/module-1-setup) includes a more comprehensive implementation of In-World Analytics.

*   The In-World Analytics onboarding world includes demos, examples, and the latest scripts for your reference. This documentation can be combined with review of the In-World Analytics framework with in-line comments to enable faster self-paced onboarding and self-service.

## Introduction: What Is In-World Analytics?

In-World Analytics enables creators to record events that occur within the world by storing them in the analytics data for the world. It is an E2E solution that empowers creators to get deeper insights about their worlds. To simplify integration with your existing creation, the In-World Analytics framework consists of the following tools:

*   Turbo Analytics: A collection of TypeScript Scripts, available in the Asset Library, that can be added to your world

*   An Analytics API: A collection of APIs for sending analytics data through TypeScript ,

*   Creator Insights Portal: A web-based visualizer available on the creator portal which will show the analytics insights from your world.

## Adding In-World Analytics To A World

To use In-World Analytics:

*   Enable horizon/analytics API in your Script settings in the desktop editor. This enables the [TypeScript APIs](/horizon-worlds/reference/2.0.0/analytics_turbo) to be called from the scripts.
    
    *   Open the script folder and click the settings cog 
        
        ![Script settings](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476888965_651374574067164_2812474232980990084_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=luXNks7TdUcQ7kNvwH2XFDZ&_nc_oc=Adliq4RDIUbX0WWZLZ4Sg5ZVAxrQb2KkwfI_TqhJefeWKgVHW--ojZiZAm83sp6egVw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=auaWYXY-W-77s8FNWjqcGA&oh=00_AfTHuJ_A52SdeYBIfE9ttjhnJ4gsfOUNKUAwcPOhZcbX_A&oe=689B928C) 
    
    *   Choose API in the left hand menu 
        
        ![Script settings: API](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476751934_651374547400500_3699779970348890706_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=3Xuvrex661EQ7kNvwHHgbRn&_nc_oc=AdlanA5c03bNenZBJjCOc85WGgb3K7Y8IkVz0eJ6XbZMsmDOtg0_c3vYcE73QOOA4kE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=auaWYXY-W-77s8FNWjqcGA&oh=00_AfQ3zAmyhXHe43KY4bQ1xXPmXwZ6Y9EkHexNpsX04VFE-w&oe=689BB8AA) 
    
    *   Toggle on `horizon/analytics`![Script settings: Selecting the analytics API](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476833117_651374540733834_7899213470972344670_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=pVEPkoLFYZEQ7kNvwGKGRdA&_nc_oc=Adlz2bjrJEsGCtLwkmOxUU2WFByatbyKXXUcb0ipXEQUyx9iq87n1WlXrmkWf6VKXe4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=auaWYXY-W-77s8FNWjqcGA&oh=00_AfTnhnCvDMdlXvf0B9l-XXc3BbrG-9jZmvHCjmnnbaKVlQ&oe=689BA232)

*   Add Turbo Analytics from the Asset Library to your world. Turbo Analytics consists of a preconfigured set of Scripts and Entities that can be added to your world to accelerate implementation. 
    
    ![Asset Library: Turbo Analytics](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476815115_651374534067168_1757621722348386502_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=H6ixYVZZop0Q7kNvwFGQdiK&_nc_oc=Adnf94EhsmRdqsKlgwLdUCcAeMAE9OTUBqKw7PJ2e82zeItuvQwI9gcWH9kH1Ya91P8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=auaWYXY-W-77s8FNWjqcGA&oh=00_AfTURC9VLEIiVwxikiAcv4Dk8uunpk2V6FOGtPFEQfmCTg&oe=689BBD5C)
    
    *   Open the Asset Library
    
    *   Navigate to the Interactive category
    
    *   Find Turbo Analytics

## Sending In-World Analytics Events (Turbo Actions)

Turbo [Actions](/horizon-worlds/reference/2.0.0/analytics_action) are a crucial component of the In-World analytics platform, characterizing the trigger or player action that serves as the context for an event. These are sent to the in-world analytics engine for logging and player state updates, providing valuable insights into player behavior.

Most Turbo Actions represent a 1:1 mapping with each AnalyticsManager event handler. Some actions are simple pass-throughs to logging, while others may affect the Player State in critical ways. For example, certain Areas designated as Lobbies might automatically change the TurboState of a player, which will pause Round Timers and tick Lobby Overall seconds. Similarly, certain automated rules are triggered when an AFK Event is sent.

### Sending Turbo Actions

To send payloads to the engine, use the AnalyticsManager as a wrapper. A concise helper function has been provided to easily call the static instance assigned. Each function has an implied Turbo Action and ActionData based on the Payload type. Example Implementation: This example demonstrates how to send a Friction Hit event to the Analytics Engine using the AnalyticsManager wrapper. The sendFrictionHit function takes a FrictionHitData object as an argument, which contains the necessary data for the event.

```
/** Friction Hit by Player */
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

## In-World Analytics Modules

#### Area

Turbo Analytics methods: `sendAreaEnter`, 

`sendAreaExit`, `sendPlayerReadyEnter`, 

`sendPlayerReadyExit`

Related actions: `OnAreaEnter`, 

`OnAreaExit`, `OnPlayerReadyEnter`, 

`OnPlayerReadyExit`

Areas are custom defined ‘physical’ sections of a world that players can navigate to. Area Analytics can show how many players navigate to various sections in the world and how long they spend there.

Some Area Types are integrated in the engine due to their importance and relevance to all content experiences. These include Lobby and PlayerReadyZone.

Designating Areas as Lobby sections help creators measure critical engagement signals including Lobby Efficiency (Time to Fun), Game Participation (Made it to the Game) & Intent to Play (Player Ready Zone).

Lobby Sections have critical importance to a player’s overall experience. Lobbies are generally where players form their first impressions of a world and are almost always the entry-point to an experience. By distinguishing these from general “Areas” using `areaIsLobbySection` it is possible to track time distinctly (world seconds vs. lobby overall seconds). This results in more specific signals and better delineation between “In the Game/Experience” vs. “Not in the Game/Experience”.

Lobby Sections, when entered by a player, will change the ParticipationState (TurboState) of the player, which denotes where the player is ‘at’ in terms of the experience. TurboState (e.g. `IN_LOBBY` vs. `IN_ROUND` ) affects which events are listened to or logged at the time of the event due to the context. Some timers like `LobbyOverallSeconds` and `RoundTimers` only tick when the player is in the relevant analytical TurboState.

Player Ready is also an extension of Turbo Area, since many gaming worlds have a Player Ready Zone, where players show intent to play a game. When modeling the player experience as a Funnel, this can be a critical bottleneck that Turbo can provide insights about. For example, if Game Participation is low, but Intent to Play is High, that could signal issues with concurrency, or matchmaking, or worse (player re-spawning or game logic is broken) and can be an informative signal when considering lobby re-designs and optimizations.

Use Cases:

*   Worlds with unique areas/zones that players can navigate to (most). Often these areas play a semantic role in the game experience or represent a set of features or activity. For PvP games, these might be the larger sections of a battle arena. For hangout and entertainment worlds with less structure, these might be various pockets of the world.

*   Worlds with a Lobby separated from the main experience or game. Enables tracking of ‘pre-game’ activity, as well as delineating game participation from socializing or browsing a world without trying out the main experience.

#### Discovery

Turbo Analytics methods: `sendDiscoveryMade` Related actions: DiscoveryMade

Discovery events are the rocket fuel ingredients for Feature Analytics. They inform creators how often players discover or experience things in the world that they intended for their players to find, utilize, or engage with. These can be physical / intractable discoveries like easter eggs or more abstract ‘discoveries’ like successfully unlocking a gate or getting a super bonus.

Discoveries are positive things to surprise or delight players and help them deepen their engagement. This can range from exciting moments like getting an automatic hole-in-one or winning a game and receiving an unexpected trophy. Discoveries can also be used for more general tracking of players ‘picking up what the creators’ throwing down’, like a user ‘realizing’ or ‘experiencing’ a feature, possibly one that only arises in the right set of conditions when players follow the ‘cues’ (or seek the hints).

Use Cases:

*   Worlds with Easter Eggs, Hidden Gems, or otherwise positive things for users to discover.

#### Friction

Turbo Analytics methods: `sendFrictionHit`, 

`sendFrictionCaused`

Related actions: FrictionHit, FrictionCaused

Friction events are ‘Progression-slowing’ or Negative experiences that the user faces. Sometimes these are placed on purpose by design via obstacles or challenges, but other times they are inferred or derived Friction that represent a lack of fun (e.g. No KOs in 2 minutes during a PvP Round).

Friction Analytics helps creators ensure proper game balance and challenge for their players to optimize the fun. Friction events imply negative experiences which detract or challenge the user, such as falling down or having to wait too long to play. This module can also track timer-based events using derived friction such as players not winning or not getting any points/kos in a while, which can serve as a proxy for ‘not fun’ (been there…). Derived Friction (frictionIsImplied: true) may be ‘realized’ or ‘experienced’ based on certain conditions as opposed to an obvious punch to the face, for instance. Other typical friction points can be incredibly useful so that creators can automatically optimize their game long before players complain that it’s ‘too hard’ and other negative feedback. FrictionCaused was introduced in v15 to track when a player is causing friction for others. It could be similar to ‘Challenge’ where the player is simply too ‘good’ at a game and dominating others, or could lean a bit more in the integrity space (a player is disrupting the experience).

Use Cases: Worlds with obstacles, worlds with expected but negative events (e.g. loading taking too long, not progressing enough, being eaten by ghosts..). Worlds that specifically want to add friction/challenge but ensure the right amount of it will use this heavily.

#### Death

Turbo Analytics methods: `sendDeathByPlayer`, 

`sendDeathByEnemy`

Related actions: DeathByPlayer, DeathByEnemy

Death module is mostly for PvP and PvE games for keeping track of KOs. This is usually already managed in these types of games, so making calls to Turbo is simple. The Death module includes the Weapon Used and can increment counters automatically in Rounds, Stages, and Sections. It can also track of whom (or what) was the killer for aggregate statistics and matchmaking health.

Use Cases:

*   Player vs. player (PvP) game worlds

*   Player vs. environment (PvE) game worlds

#### KOEnemy

Turbo Analytics methods: `sendKOEnemy` Related actions: KillEnemy

Tracks KOs when a player kills a Monster/Enemy/Or bot. NOT another player.

Use Cases:

*   PvE

#### KOPlayer

Turbo Analytics methods: `sendKOPlayer` Related actions: KOPlayer

KOs, Kills, ‘Unalives’, whatever you call it, this module keeps track of KOs between players. The reason for splitting this out from KillEnemy is because Players have more metadata and attributes (and privacy handling) compared with Enemies. Enemies are just a ‘key/identifier’ whereas player interactions have deeper analytics and context within the round.

Use Cases:

*   PvP

#### LevelUp

Turbo Analytics methods: `sendLevelUp` Related actions: LevelUp

When a Player Levels Up (e.g. gains XP to the next threshold), creators can generate the Turbo event. This provides live tracking of leveling up events, but also gives additional contextual insights leading up to the player progression. For example, creators can look at level up events sliced by how long it took for them in that session and where they were physically (Area) and in the game context (Round/Stage)

Often creators leverage Player Variables (PVars) to track Level Ups, since levels can unlock rewards and leaderboard ranks. Meta has some analytics at the Daily level for PVars for insights, but Turbo takes this to another level. By enabling live tracking of these events, we know sooner how often these are happening (or not happening), but we can also learn more about how players of different experience levels navigate through the world. Player Level is also a decent proxy for ‘Experience’. Lots of insights can be gained when creators can look not just overall at progressions and activity, but comparing more veteran players with n00bs to identify gotchas on new user experience (or the other way around).

Use Cases:

*   Ensuring Player Level Progression

*   Player Level Analytics and Matchmaking

*   XP Threshold Evaluation

#### Rewards

Turbo Analytics methods: `sendRewardsEarned` Related actions: RewardsEarned

Rewards are used to track things like collectibles, XP, points, bonuses, etc. The ‘RewardsType’ is a key that can be used to distinguish. For logging efficiency, we decided to include this with a bit of abstraction so that creators can more easily track different types of rewards without having to anticipate every single type. Similar to Player Level, these rewards are often tracked as Player Variables since they affect gameplay with unlocks, etc. Also similar to player level, the reason for including in Turbo is to get more context around sessions/moments where rewards are earned to ensure that rewards are being received (health monitoring) and then gain additional insights into how, when, and why those rewards are earned (or not) to optimize for it.

NOTE: Sometimes these can be noisy, so we recommend batch updates to reduce overhead. This includes locally aggregating totals for a player locally during a time slice (round, stage, or frequency of time) and then sending a single event with the totals instead of individual collections.

For example, consider those crazy money machines that surround you in a hurricane of bills you need to collect. You don’t need to log every single dollar grabbed, just once at the end or optionally a few times throughout to ensure it’s not missed. 💸 👻💸

Use Cases:

*   Worlds with XP

*   Collectibles

*   Points

#### Rounds

Turbo Analytics methods: `sendAllRoundStart`, 

`sendAllRoundEnd`

Related actions: RoundStart, RoundEnd

Rounds (Funnel Slice: Hierarchy Level 1) Funnel Progression: This is something we argue applies to ALL Worlds, unless they literally don’t have an experience in a clear way. The ‘Round’ is a full loop of the game, ordered sequentially by ID. Round Start events for a player define ‘Game Participation’. In quick action, repeated games like PvP, Rounds also enable back-to-back and Avg Rounds / Session analyses. For larger adventure games, often just knowing ‘In Round’ vs. ‘In Lobby’ is sufficient.

Use Cases:

*   Worlds that have defined experiences and/or time-based segments

Metrics served:

*   Game Participation

*   Rounds

#### Stages

Turbo Analytics methods: `sendStageStart`, 

`sendStageEnd`

Related actions: StageStart, StageEnd

Stages (Funnel Slice: Hierarchy Level 2, 1+ Stages Make up a Round). Same concept as Rounds, but more granular within the experience.

Creators often refer to stages as ‘Levels’, ‘Rooms’, ‘Waves’, ‘Segments’. We use ‘Stage’ as a generic way to slice up moments.

TurboPlayerState tracks StageIds (Sequential) distinct from StageNames. StageNames can be distinct independent from StageId. This is especially useful for games/worlds that experiment with randomization or various choices for what users experience and in what order (Spy School as a key example).

For example, If a player needs to complete 3 rooms to get to the end of a round, those will be logged as StageIds: 1, 2, and 3, but if the creator has 20 ‘rooms/configurations’ to choose from, the StageName can be included to better understand the combinations of Stage Order vs. Stage Content and help with optimized configurations. 🥷Creators don’t have to provide Stage Names. Stage Names will default to ‘Stage 0‘, ‘Stage 1’ , etc. which is totally fine if they are equivalent to the Sequences.

Use Cases: Worlds that have granular steps/waves within a Funnel progression. Most applicable to Obstacle Courses, Adventure Games. Metrics served: Funnel Participation, Stages Dropoff vs. Completion, Waves Analyses (Dimensional Context)

#### Sections

Turbo Analytics methods: `sendSectionStart`, 

`sendSectionEnd`

Related actions: SectionStart, SectionEnd

Sections (Funnel Slice: Hierarchy Level 3, 1+ Sections Make up a Stage). This module helps us keep track of Funnel progressions where the player has started/completed or entered a sub-section or part of a Stage/Wave/Level of the Experience. Purpose: Keep track of more granular sections/areas on where an event occurred or a Player is Navigation. Exact concept as Stages, just one level deeper. We could go on recursively forever, but we won’t… 🙂. In all seriousness, this is for really specific sections of a big game. Imagine you have a Round with 10 giant levels. Each level is a ‘Stage’. Now imagine that every 1-2 minutes there’s a different ‘turn’ or ‘scene’ or even ‘enemy’. When creators wish to change one small area (~30 seconds of gameplay), enabling ‘Sections’ as a slice can be really powerful. Beyond that, we lose too much analytical power.

Use Cases:

*   Same as Stages with more granularity. Especially useful for games with a lot of options of experiences/pathways and obstacle courses (big levels, multiple levels, etc.).

Note that Unlike Area and Lobby, Sections can be used to slice experiences beyond “physically defined” parts of a world (i.e. not just x,y,z coordinates). Instead, sections can be leveraged to track variations/configurations/encounters within a stage and have more semantic relevance. For example, variations within Stages (battling this enemy) could be captured as a section, which may include running all over the map! In this way, the ‘section’ is really more like a ‘moment’. Enabling this as unique within a stage allows creators to experiment with different scenarios, configuration, or obstacles. This is flexible on purpose to drill down/slice by certain variations of the game, especially if there’s concerns that players can’t progress or if there’s a push to drive more engagement through a new ‘moment’.

#### Tasks

Turbo Analytics methods: `sendTaskStart`, 

`sendTaskStepStart`, `sendTaskStepEnd`, 

`sendTaskEnd`

Related actions: TaskStart, TaskEnd, TaskStepStart, TaskStepEnd

Tasks (and Task Steps) were designed to measure specific activities/funnels where the player has a series of steps to follow. This is similar to Rounds, Stages, and Sections, but those are more appropriate for an ‘overall experience’ (Levels of the Game, Waves, Rooms), whereas Tasks might happen within one of those Stages/Sections. It includes an updated TurboTimer (2.0) which zips the ‘Overall Task’ and the ‘Task Steps. Each task and task steps are given keys to uniquely identify them. While the nomenclature is generic, the idea came from small puzzles/challenges that would either be part of a mini-game or Escape Room. Creators could also decide to layer on this module to a specific flow or journey to better capture things like ‘Time to Fun’ or ‘Onboarding’. A great example of this would be in Welcome World, but the most appropriate would be something like a Challenge course.

### WeaponEquip

Turbo Analytics methods: `sendWeaponEquip` Related actions: WeaponEquip

WeaponEquip is a generic/simple way to log that a player equipped a weapon. It includes the weapon key for tracking and automatically Turbo will keep track of the current weapons available to the player. Use Cases: Games with Weapons that Don’t need to track Utilization (timers), but want to know current Weapons as part of Turbo State. Most Applicable to Adventure Games that want this data, but don’t need to track the details of frequent grabs and releases.

#### WeaponGrabAndRelease

Turbo Analytics methods: `sendWeaponGrab`, 

`sendWeaponRelease`

Related actions: WeaponGrab, WeaponRelease

WeaponGrabAndRelease is a more complex (and expensive) solution for understanding weapons that are grabbed, released, and includes Turbo Timers for Weapon Utilization (time spent held). Creators can use this for a ‘Weapon’ view (how much time is each weapon utilized in a round), a ‘Player view’ (how much is each player acquiring/hogging each weapon), and other Weapon balance signals. This combined with the Turbo Setting that will log each Grab and Release can be very log spammy, but for certain games where weapons balance is critical, it can be utilized. For some PvP, we used this to contrast with KOs (as a cross-signal). The analysis looked at grab frequency vs. KOs across all weapons to get a sense of how balanced the weapons were. Lower Grab rates with outsided High KOs (weapon Used in the KO) suggest some power players dominate by grabbing these weapons and destroying everyone with them (not very fun, especially for new players).

Use Cases: Games with Weapons that need to track Utilization and Inventory in a more granular way (usually PvP-Round based games where players compete for resources).

#### Wearables

Turbo Analytics methods: `sendWearableEquip`, 

`sendWearableRelease`

Related actions: WearableEquip, WearableRelease

Wearables is a module that operates similarly as Weapons. A ‘current_wearables’ is maintained as part of the TurboPlayer state. The creators can choose if they want to specifically track ‘WearableAttach’ and ‘WearableDetach’, or if they want to, grabbing + grab lock can also be used. Wearables include a wearables ‘type’ in case there’s a need to run cross-sectional analysis of things like weapons, costumes, or jewelry. It can also be used for quasi-experimentation, such as allowing for different options of wearables to compare performance.

## Turbo Area

Turbo Area is a framework that helps creators understand how many players enter each area and how long they spend in that area. This module provides valuable insights into player behavior and can be used to optimize game design and improve player engagement.

Turbo Area is enabled by default and uses Turbo Timers to track durations within areas. When you send AreaEnter or AreaExit events, the AnalyticsManager manages the state, including the current area name and additional area properties.

When a player enters a new area before exiting the previous one, the previous area timer is paused, ensuring that a player is only in one area at a time. Implementing Turbo Areas There are two options for implementing Turbo Area:

#### Using TurboAreaTrigger (Recommended)

Use the TurboAreaTrigger provided as part of the TurboAssets and set the appropriate props in the attached entity.

For an example, see the [Chop N Pop Graveyard Bash Analytics Tutorial](/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-analytics-tutorial/module-1-setup) .

#### Using Implied Areas

Call the sendAreaEnter event in TurboAnalytics from your existing game code and pass the relevant data:

```
// Your Game Code
import {Analytics} from 'TurboAnalytics'

Analytics()?.sendAreaEnter({
    player,
    actionArea: "awesome_lobby_area",
    actionAreaIsLobbySection: true
    actionAreaIsPlayerReadyZone: false
});
```

TurboAnalyticsManager can simplify methods like this using the exported payloads Note: Using Triggers is recommended over Implied Areas, as they more reliably capture the onAreaEnter and onAreaExit events separately, which ensures definitive closure of the action flow.

#### Turbo Area Best Practices

Turbo Area provides valuable insights into player behavior and can be used to optimize game design and improve player engagement. By understanding how players interact with different areas of the game, creators can make informed decisions about game development and improvement.

Areas should represent physical zones within the world. Be mindful of how many areas you carve out and their granularity. We recommend between 5-15 unique areas. When implementing Turbo Area, keep the following best practices in mind:

*   Use meaningful area names: Use meaningful area names that accurately describe the area being tracked.

*   Use consistent area properties: Use consistent area properties across all areas to ensure accurate tracking and analysis.

*   Test and validate: Test and validate your implementation to ensure that it is working correctly and providing accurate data.

By following these best practices and using the TurboAreaTrigger or implied areas, you can effectively implement Turbo Area and gain valuable insights into player activity within your game or world.

## Debugging Creator Analytics *Note: Make sure to remove all debug tooling and disable logging before publishing worlds containing Turbo Analytics to minimize the performance overhead of In-World Analytics.* #### Turbo Debug

You can find Turbo Debug in the Asset Library.

![Asset Library: Turbo Debug](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/477028223_651374554067166_4470856057306053992_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=0rEkFz3ii7EQ7kNvwGwz4Wh&_nc_oc=Adk3hRg8R8V3oeKPooF8fdhbR4HE0qJQHuI9_WD1_l3O_5G9hWLsF00xnZ_OG7jaQsI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=auaWYXY-W-77s8FNWjqcGA&oh=00_AfSh5bQmPWp-9UIgQNZ2Eog5axmcpSo5GgBCzqorlhCt-A&oe=689BAD52)

This asset works in combination with Turbo Analytics, and consists of tools that display events that are being recorded via In-World Analytics through in-world TextGizmo’s and in the Console.

#### Adding your own logging to Turbo Analytics

In TurboAnalytics.ts there is a boolean used to determine whether debug mode is enabled on Turbo Analytics:

```
export const TURBO_DEBUG =
  false; /** TODO (Creator): IMPORTANT!!! Set to False before Release **/
```

By default this is set to `false`.

Setting `TURBO_DEBUG` to `true` enables the `onDebugTurboPlayerEvent` function to be called for every event called from Turbo Analytics. By default this function does not do anything. You can modify this function to log debug information, as per your requirements. For example:

```
onDebugTurboPlayerEvent(_player: hz.Player, _eventData: EventData, _action: Action): void {
    console.log(`🚀 TURBO: Debugging Turbo Player Event: ${_player.name.get()}: ${Action[_action].toString()}`);
  }
```

## Custom Analytics Manager

The In-World Analytics framework is the recommended way to integrate In-World Analytics into your world. Once you have imported it, you can customize this Script to suit the needs of your world. Alternatively, you can also choose to write your own script to interface with In-World Analytics. For more information see [Capturing Custom In-World Analytics](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/custom-in-world-analytics) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 