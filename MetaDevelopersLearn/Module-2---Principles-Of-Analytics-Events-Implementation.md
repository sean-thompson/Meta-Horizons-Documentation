# Module 2 - Principles Of Analytics Events Implementation

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-analytics-tutorial/module-2-principles-of-implementation)

After adding the Turbo Analytics libraries to the world, you can start recording in-world event data from your own scripts.

For a list of the types of events you can send through the Analytics API review, see [Sending In-World Analytics Events](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/advanced/using-in-world-analytics) .

While you can send events directly to the Analytics Manager from any location in your codebase, you should decouple the Analytics Manager from your main game logic. The mechanism to decouple is to create broadcast events and to create listeners for them in the Analytics Manager.

When these events are broadcast from elsewhere in the code, the Analytics Manager handles the capture of each broadcast event and delivery of the corresponding Turbo event to the platform. This decoupling ensures that your in-world analytics listens passively to events in your game with minimal impact to the player’s experience or to your codebase. **Note**: You cannot send in-world analytics data to the platform from scripts executing in Local mode. Please verify that any Turbo events are sent from scripts executing in Default (server) mode.

## Using the Analytics Manager with existing broadcast events

In the Chop ‘N Pop example world, you can use some of the existing broadcast events in the world for tracking with in-world analytics, which minimizes the number of code changes.

The following example leverages the loot and bounty pickups to explore using broadcast events for Analytics events in Chop ‘N Pop Graveyard Bash.

When a player collects ammo for a gun, or a potion to refill health, this information can be recorded as a reward. In `LootItem.ts`, there is already a broadcast event:

```
this.sendNetworkBroadcastEvent(LootPickup, {
  player: player,
  loot: this.props.itemType,
});
```

The In-World Analytics reward event requires the following values to be passed:

*   `rewardsType`
    
     (string): The type of reward earned

*   `rewardsEarned`
    
     (number): The amount of that reward

There is a mismatch between the values that are sent with the broadcast event and those required for the Turbo reward event. The broadcast event is missing the amount of rewards!

In the Chop ‘N Pop Graveyard Bash example world, the amount of ammo or health given by a reward is stored as a configurable property in `PlayerManager.ts`:

```
ammoPerBox: { type: PropTypes.Number, default: 10 }, healthPerPotion: { type: PropTypes.Number, default: 1 },
```

When these props are stored in this class, they must be moved through the code by creating accessors or passing them as parameters in function calls for access by the Analytics Manager. This method may cause additional bugs.

Instead, it would be easier to store these in the `GameConstants.ts` file that you created, so that they can be imported by the game logic code and the analytics code independently. In the future, they can modified in a single, central location.

*   Change the `GameConstants.ts` file to include references to these values:
    
    ```
    export const GameConstants = {
     AMMO_PER_BOX: 10,
     HEALTH_PER_POTION: 1,
      };
    ```
    

*   If the default values in your world are different from the above, replace them with your values.

*   Replace the `handleLootPickup()` function in PlayerManager with the following, noting the references to the `GameConstants` constants by name:
    
    ```
    private handleLootPickup(data: {player: Player, loot : string}) {
     var playerData = this.gamePlayers.get(data.player);
     if (playerData) {
       if(data.loot === 'Ammo') {
         this.gamePlayers.addAmmo(data.player, GameConstants.AMMO_PER_BOX);
       } else if(data.loot === 'Potion') {
         this.gamePlayers.heal(data.player, GameConstants.HEALTH_PER_POTION, this.props.playerMaxHp);
       }
       this.updatePlayerHUD(playerData);
     }
      }
    ```
    

*   Remove the `ammoPerBox` and `healthPerPotion` props from the PlayerManager class. Verify that these properties (e.g. `this.props.ammoPerBox` ) are not used elsewhere in your script.

*   Test your world. Collect an ammo and a potion to verify that the world still works as expected.

Now that the values are available in a single accessible location, you can implement a listener for the reward event in the AnalyticsManager:

*   Open `TurboAnalytics.ts` and navigate to the `subscribeToEvents()` function.

*   Replace the `subscribeToEvents()` function with the following, which adds the listener and a call to the `onLootPickup()` function:

```
subscribeToEvents() {
  this.connectLocalBroadcastEvent(TurboDebug.events.onDebugTurboPlayerEvent, (data: {
    player: hz.Player;
    eventData: EventData;
    action: Action
  }) => {
    this.onDebugTurboPlayerEvent(data.player, data.eventData, data.action);
  });
  this.connectNetworkBroadcastEvent(Events.lootPickup, (data) => {
    this.onLootPickup(data);
  });
}

onLootPickup(data: { player: hz.Player, loot: string}){
  let rewardsEarned = 1;
  if (data.loot === 'Ammo') {
    rewardsEarned = GameConstants.AMMO_PER_BOX;
  } else if(data.loot === 'Potion') {
    rewardsEarned = GameConstants.HEALTH_PER_POTION;
  }
  this.sendRewardsEarned({player: data.player, rewardsType: data.loot, rewardsEarned});
}
```

When a player collects ammo or health in the world, the `Events.lootPickup` event is fired, and the `onLootPickup()` function is called, which uses the rewardsEarned analytics API to record the event to in-world analytics.

Test the world with the Console open and verify that the event is being recorded.

## Using the Analytics Manager with new broadcast events

If there is no existing broadcast event in the Analytics Manager that is suitable for listening for analytics purposes, you can add your own broadcast events and listeners.

In the following example from the Chop ‘N Pop Graveyard Bash example, weapon usage is tracked using a newly created event.

*   In the desktop editor, open `Events.ts` in your preferred script editor.

*   Add a new event on line 13 called `weaponEquipped`:
    
    ```
    export const Events = {
    
     gameReset: new NetworkEvent<{}>('gameReset'),
    
     // Weapon Events
     weaponEquipped: new NetworkEvent<{ player: Player, weaponKey: string, weaponType: string, isRightHand: boolean }>('weaponEquipped'),
    
     // Gun Events
     projectileHit: new NetworkEvent<{ hitPos: Vec3, hitNormal: Vec3, fromPlayer: Player, weapon: string}>('projectileHit'),
    
     ...
    ```
    

*   Open `Axe.ts` and modify the `OnGrabStart()` function by sending the `weaponEquipped` event at the end of the function:
    
    ```
    protected override OnGrabStart(isRightHand: boolean, player: Player) {
       this.entity.owner.set(player);
    
       if (isRightHand) {
         this.hand = HapticHand.Right;
       } else {
         this.hand = HapticHand.Left;
       }
    
       if (player.deviceType.get() != PlayerDeviceType.VR) {
         this.triggerSub = this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnIndexTriggerDown, (triggerPlayer) => {
             Throttler.try("AxeHit", () => {
               this.entity.owner.get().playAvatarGripPoseAnimationByName(AvatarGripPoseAnimationNames.Fire);
               this.sendNetworkBroadcastEvent(Events.monstersInRange, {entity: this.entity, range: this.props.threatRange})
             }, this.props.swingCooldown)
           });
           this.inRangeSub = this.connectNetworkEvent(this.entity, Events.monstersInRangeResponse, this.hitMonsters.bind(this));
         }
    
         // Send weaponEquipped event from the axe
         this.sendNetworkBroadcastEvent(Events.weaponEquipped, {player, weaponKey: "axe", weaponType: "melee", isRightHand});
     }
    ```
    

*   Open `GunCore.ts` and modify the `OnGrabStart()` function by sending the `weaponEquipped` event:
    
    ```
    OnGrabStart(isRight: boolean, player: Player) { this.reload();
    
         this.isHeld = true;
         this.entity.owner.set(player);
         this.props.projectileLauncher?.owner.set(player);
    
         this.triggerDownSubscription = this.connectCodeBlockEvent(
           this.entity,
           CodeBlockEvents.OnIndexTriggerDown,
           this.triggerDown.bind(this)
         );
    
         this.triggerReleasedSubscription = this.connectCodeBlockEvent(
           this.entity,
           CodeBlockEvents.OnIndexTriggerUp,
           this.triggerReleased.bind(this)
         );
    
         this.reloadSubscription = this.connectCodeBlockEvent(
           this.entity,
           CodeBlockEvents.OnButton1Down,
           this.reload.bind(this)
         );
    
         if (player.deviceType.get() === 'VR') {
           this.reloadSubscription = this.connectCodeBlockEvent(
             this.entity,
             CodeBlockEvents.OnButton2Down,
             this.reload.bind(this)
           );
         }
    
         this.playerHand = isRight ? HapticHand.Right : HapticHand.Left;
         HapticFeedback.playPattern(player, HapticType.pickup, this.playerHand, this);
         this.props.grabSFX?.as(AudioGizmo)?.play();
         this.updateAmmoDisplay();
    
         // Send weaponEquipped event from the gun
         this.sendNetworkBroadcastEvent(Events.weaponEquipped, {player, weaponKey: "gun", weaponType: "projectile", isRightHand: isRight});
    
     }
    ```
    

*   Open `TurboAnalytics.ts` and modify the `subscribeToEvents()` function so that it includes the listener for the `Events.weaponEquipped` broadcast event:
    
    ```
    subscribeToEvents() {
       this.connectLocalBroadcastEvent(TurboDebug.events.onDebugTurboPlayerEvent, (data: {
         player: hz.Player;
         eventData: EventData;
         action: Action
       }) => {
         this.onDebugTurboPlayerEvent(data.player, data.eventData, data.action);
       });
    
       this.connectNetworkBroadcastEvent(Events.lootPickup, (data) => {
         this.onLootPickup(data);
       });
    
       // Subscribe to the weaponEquipped event
       this.connectNetworkBroadcastEvent(Events.weaponEquipped, (data) => {
         this.sendWeaponEquip(data);
       });
     }
    ```
    

*   In this example, no new function is added. Instead, the new event contains the information required for the call to the analytics API.

## Using the Analytics API directly

The provided Analytics Manager is intended to accelerate your workflow. However, in some cases, you may prefer to work directly with the Analytics API. You can use the Analytics Manager as an example of how to interact directly with the API.

For example, if you want to send the weapon equipped call directly to the Analytics API, you could use the following function call:

```
Turbo.send(TurboEvents.OnWeaponEquip, data);
```

The above call records the data by calling the API directly ( `Turbo.send` ) to send the `OnWeaponEquip` event.

```
OnWeaponEquip: SinglePlayerTurboEvent<{
  weaponKey: string;
  weaponType?: string | undefined;
  isRightHand?: boolean | undefined;
}>;
```

For more information on the required parameters for each analytics event, see the Horizon Analytics TypeScript definitions file ( `horizon_analytics.d.ts` ) or in the [TurboEvents API reference](https://horizon.meta.com/resources/scripting-api/analytics.turboevents.md/) .

## Checkpoint

In this module, you explored three different implementation methods for capturing events to the Analytics API:

*   **Use Analytics Manager with existing events**: This method listens for the `lootPickup` event and sends a message to the Analytics API using values that have been consolidated into the `GameConstants.ts` script file.

*   **Use Analytics Manager with new events**: This method creates a new broadcast event and a listener for it. In the listener, an event is passed to the Analytics API for capture to in-world analytics.

*   **Using the Analytics API directly**: Although the Analytics Manager can be used to send analytics events, you can choose to send them directly instead.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 