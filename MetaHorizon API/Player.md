# Player Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_player)

Represents a player in the world. This is the primary class for managing an individual player's physical presence and game play in the world, including their avatar.

## Signature

```
export declare class Player
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(id)**</td>
      <td>Creates a player in the world.

* * *

Signature

```
constructor(id: number);
```

Parameters

id: number

The ID of the player.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**avatarScale**</td>
      <td>The scale of the player's avatar. Change this to scale the player up or down.

Signature

```
avatarScale: HorizonProperty<number>;
```

Examples

This example demonstrates how to modify the avatar scale of a player when it enters a trigger.

```
class AvatarScalingExample extends hz.Component<typeof AvatarScalingExample> {
  static propsDefinition = {
    newAvatarScale: { type: hz.PropTypes.Number },
  };

  start() {
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerEnterTrigger, (player) => {
      player.avatarScale.set(this.props.newAvatarScale);
    });
  }
}

hz.Component.register(AvatarScalingExample);
```

Remarks

Accepts values between 0.05 and 50.

  

The scaling happens with a one frame delay.</td>
    </tr>
    <tr>
      <td>**deviceType**</td>
      <td>Gets the type of device the player is using.

Signature

```
deviceType: ReadableHorizonProperty<PlayerDeviceType>;
```

Remarks

New device types may be added in the future, so you should handle this property with a switch statement.</td>
    </tr>
    <tr>
      <td>**focusedInteraction**</td>
      <td>The [FocusedInteraction](/horizon-worlds/reference/2.0.0/core_focusedinteraction) instance associated with the player.

Signature

```
focusedInteraction: FocusedInteraction;
```

Remarks

Focused Interaction mode replaces on-screen controls on web and mobile clients with touch and mouse input that includes direct input access.

  

For more information about Focused Interaction, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .</td>
    </tr>
    <tr>
      <td>**foot**</td>
      <td>The player's foot.

Signature

```
foot: PlayerBodyPart;
```</td>
    </tr>
    <tr>
      <td>**forward**</td>
      <td>The player's forward direction relative to the world origin.

Signature

```
forward: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**gravity**</td>
      <td>The player's gravity before simulation.

Signature

```
gravity: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**head**</td>
      <td>The player's head.

Signature

```
head: PlayerBodyPart;
```</td>
    </tr>
    <tr>
      <td>**id**

\[readonly\]</td>
      <td>The player's ID.

Signature

```
readonly id: number;
```</td>
    </tr>
    <tr>
      <td>**index**</td>
      <td>The index that identifies the player in the list of all players in the world instance.

Signature

```
index: ReadableHorizonProperty<number>;
```

Examples

This example demonstrates how to retrieve a `Player` object using a player index.

```
var playerIndex = player.index.get();
var playerFromIndex = this.world.getPlayerFromIndex(playerIndex);
```

Remarks

When joing a world, each player is assigned an index, which ranges from 0 (the first player) to `Max Players - 1`. Use the index value to keep track of players and get a `Player` object using the [World.getPlayerFromIndex()](/horizon-worlds/reference/2.0.0/core_world#getplayerfromindex) method.</td>
    </tr>
    <tr>
      <td>**isGrounded**</td>
      <td>Indicates whether the player is grounded (touching a floor). If a player is grounded then gravity has no effect on their velocity.

Signature

```
isGrounded: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**isInBuildMode**</td>
      <td>Indicates whether a player is in build mode.

Signature

```
isInBuildMode: ReadableHorizonProperty<boolean>;
```

Remarks

Build mode means the player is editing the world. The alternative, preview mode, is when they're playing the world.</td>
    </tr>
    <tr>
      <td>**jumpSpeed**</td>
      <td>The speed applied to a player when they jump, in meters per second. Setting this to 0 effectively disables a player's ability to jump.

Signature

```
jumpSpeed: HorizonProperty<number>;
```

Remarks

Default value is 4.3. jumpSpeed must be a value between 0 and 45. `jumpSpeed.set` can be called on any player from any context, but `jumpSpeed.get` will throw an error unless it's called from a local script attached to an object owned by the player in question.</td>
    </tr>
    <tr>
      <td>**leftHand**</td>
      <td>The player's left hand.

Signature

```
leftHand: PlayerHand;
```</td>
    </tr>
    <tr>
      <td>**locomotionSpeed**</td>
      <td>The speed at which the player moves, in meters per second.

Signature

```
locomotionSpeed: HorizonProperty<number>;
```

Remarks

Default value is 4.5. locomotionSpeed must be a value between 0 and 45. `locomotionSpeed.set` can be called on any player from any context, but `locomotionSpeed.get` will throw an error unless it's called from a local script attached to an object owned by the player in question.</td>
    </tr>
    <tr>
      <td>**name**</td>
      <td>The player's name displayed in the game.

Signature

```
name: ReadableHorizonProperty<string>;
```</td>
    </tr>
    <tr>
      <td>**position**</td>
      <td>The player's position relative to the world origin.

Signature

```
position: HorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**rightHand**</td>
      <td>The player's right hand.

Signature

```
rightHand: PlayerHand;
```</td>
    </tr>
    <tr>
      <td>**rootRotation**</td>
      <td>The root rotation of the player's avatar. This is different from the [Player.rotation](/horizon-worlds/reference/2.0.0/core_player#rotation) property, which retrieves the player's head rotation.

Signature

```
rootRotation: HorizonProperty<Quaternion>;
```

Examples

```
class ServerRotate extends hz.Component<typeof ServerRotate> {
  static propsDefinition = {
    lookAtProp : { type: hz.PropTypes.Entity },
  };
  start() {
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerEnterWorld, (player: hz.Player) => {
      serverPlayer = player;
      console.log("Starting interval Server");
      this.async.setInterval(() => {
        if(serverPlayer != undefined) {
          var rootRotation = serverPlayer.rootRotation.get();
          console.log("Server: " + rootRotation.toString());
        }
      }, 5000);
    });
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerEnterTrigger, (player: hz.Player) => {
      if(this.props.lookAtProp) {
        var lookVector = this.props.lookAtProp.position.get().sub(player.position.get());
        var newRotation = hz.Quaternion.lookRotation(lookVector.normalize());
        player.rootRotation.set(newRotation);
      }
    });
  }
}
```

Remarks

When setting, only the yaw component of the input rotation is used, keeping the character upright.</td>
    </tr>
    <tr>
      <td>**rotation**</td>
      <td>The player's facing/head rotation relative to the world origin. For the rotation of the player's entire avatar, see the [Player.rootRotation](/horizon-worlds/reference/2.0.0/core_player#rootrotation) property.

Signature

```
rotation: ReadableHorizonProperty<Quaternion>;
```

Examples

```
var headRotation = serverPlayer.rotation.get();
```</td>
    </tr>
    <tr>
      <td>**screenHeight**</td>
      <td>Gets the screen height of the screen surface the player is using.

Signature

```
screenHeight: ReadableHorizonProperty<number>;
```

Remarks

The returned value is the size of the renderable screen height in pixels, and is not guaranteed to match the actual player's device screen width.</td>
    </tr>
    <tr>
      <td>**screenSafeArea**</td>
      <td>Gets the safe area of the screen surface the player is using.

Signature

```
screenSafeArea: ReadableHorizonProperty<Rect>;
```

Remarks

The returned value is a screen space normalized rectangle, with values ranging from 0 to 1. To get actual safe area, scale it by screen width and height. i.e: 

`screenSafeArea.scaleBy(screenWidth, screenHeight)`</td>
    </tr>
    <tr>
      <td>**screenWidth**</td>
      <td>Gets the screen width of the screen surface the player is using.

Signature

```
screenWidth: ReadableHorizonProperty<number>;
```

Remarks

The returned value is the size of the renderable screen width in pixels, and is not guaranteed to match the actual player's device screen width.</td>
    </tr>
    <tr>
      <td>**sprintMultiplier**</td>
      <td>The multiplier applied to a player's locomotion speed when they are sprinting.

Signature

```
sprintMultiplier: HorizonProperty<number>;
```

Examples

This example demonstrates how to modify the player sprint multiplier while it is inside a trigger.

```
class SprintMultiplierExample extends hz.Component<typeof SprintMultiplierExample> {
  static propsDefinition = {
    modifiedSprintMultiplier: { type: hz.PropTypes.Number },
  };

  private defaultSprintMultiplier: number = 1.4;

  start() {
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerEnterTrigger, (player) => {
      player.sprintMultiplier.set(this.props.modifiedSprintMultiplier);
    });

    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerExitTrigger, (player) => {
      player.sprintMultiplier.set(this.defaultSprintMultiplier);
    });
  }
}

hz.Component.register(SprintMultiplierExample);
```

Remarks

The default value is 1.4. The `sprintMultiplier` property must be a value between 1 and 10. Setting this to 1 disables a player's ability to sprint. `sprintMultiplier.set` can be called on any player from any context, but `sprintMultiplier.get` will throw an error unless it's called from a local script attached to an object owned by the player in question.</td>
    </tr>
    <tr>
      <td>**torso**</td>
      <td>The player's torso.

Signature

```
torso: PlayerBodyPart;
```</td>
    </tr>
    <tr>
      <td>**up**</td>
      <td>The player's up direction relative to the world origin.

Signature

```
up: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**velocity**</td>
      <td>The player's velocity relative to the origin, in meters per second, due to physics and not locomotion input.

Signature

```
velocity: HorizonProperty<Vec3>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**addAvatarOverride(sku)**</td>
      <td>Overrides an avatar item on the player. Previous overrides are kept. Adds the new sku to the top of the existing list of overrides. Does not add if item is already in the list of overrides.

Signature

```
addAvatarOverride(sku: string): Promise<boolean>;
```

Parameters

sku: string

Item sku to add

Returns

Promise<boolean>

\- A promise that resolves to true if item is added successfully, false otherwise

Examples

```
playerA.addAvatarOverride(sku);
```</td>
    </tr>
    <tr>
      <td>**applyForce(force)**</td>
      <td>Applies a force vector to the player.

Signature

```
applyForce(force: Vec3): void;
```

Parameters

force: [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) The force vector applied to the player's body.

Returns

void</td>
    </tr>
    <tr>
      <td>**canApplyAvatarOverride(sku)**</td>
      <td>Checks if an override can be applied to a player with collisions automatically remediated.

Signature

```
canApplyAvatarOverride(sku: string): Promise<boolean>;
```

Parameters

sku: string

Item sku to override

Returns

Promise<boolean>

\- A promise that resolves to true if item can be overridden successfully, false otherwise

Examples

```
playerA.canApplyAvatarOverride(sku);
```</td>
    </tr>
    <tr>
      <td>**clearAimAssistTarget()**</td>
      <td>Disables Aim Assistance for a player by clearing the current target. This method must be called on a local player and doesn't affect VR players.

Signature

```
clearAimAssistTarget(): void;
```

Returns

void

Remarks

For information about using Aim Assist, see the [Aim Assist guide for web and mobile](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/aim-assist) .</td>
    </tr>
    <tr>
      <td>**clearAvatarGripPoseOverride()**</td>
      <td>Clears any override on an avatar grip pose, reverting it to the pose of the currently held grabbable.

Signature

```
clearAvatarGripPoseOverride(): void;
```

Returns

void

Remarks

For information on overriding an avatar grip pose, see .</td>
    </tr>
    <tr>
      <td>**clearAvatarOverrides()**</td>
      <td>Clears avatar item overrides on the player.

Signature

```
clearAvatarOverrides(): void;
```

Returns

void

Examples

```
playerA.clearAvatarOverrides();
```</td>
    </tr>
    <tr>
      <td>**configurePhysicalHands(collideWithDynamicObjects, collideWithStaticObjects)**</td>
      <td>Specifies whether physical hands can collide with objects.

Signature

```
configurePhysicalHands(collideWithDynamicObjects: boolean, collideWithStaticObjects: boolean): void;
```

Parameters

collideWithDynamicObjects: boolean

Indicates whether physical hands can collide with dynamic objects.

collideWithStaticObjects: boolean

Indicates whether physical hands can collide with static objects.

Returns

void</td>
    </tr>
    <tr>
      <td>**enterFocusedInteractionMode(options)**</td>
      <td>Enables [Focused Interaction](/horizon-worlds/reference/2.0.0/core_focusedinteraction) mode for the player.

Signature

```
enterFocusedInteractionMode(options?: Partial<FocusedInteractionOptions>): void;
```

Parameters

options: Partial< [FocusedInteractionOptions](/horizon-worlds/reference/2.0.0/core_focusedinteractionoptions) > *(Optional)* The options to customise the state of Focused Interaction mode. The [DefaultFocusedInteractionEnableOptions](/horizon-worlds/reference/2.0.0/core_defaultfocusedinteractionenableoptions) variable defines the default values.

Returns

void

Remarks

This method must be called on a local player and has no effect on VR players.

  

Focused Interaction mode replaces on-screen controls on web and mobile clients with touch and mouse input that includes direct input access.

  

The [Player.exitFocusedInteractionMode()](/horizon-worlds/reference/2.0.0/core_player#exitfocusedinteractionmode) method disables Focused Interaction mode.

  

When Focused Interaction mode is enabled, you can receive input data from the [PlayerControls.onFocusedInteractionInputStarted](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputstarted) , [PlayerControls.onFocusedInteractionInputMoved](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputmoved) , and [PlayerControls.onFocusedInteractionInputEnded](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputended) events.

  

For more information, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .</td>
    </tr>
    <tr>
      <td>**exitFocusedInteractionMode()**</td>
      <td>Disables [Focused Interaction](/horizon-worlds/reference/2.0.0/core_focusedinteraction) mode for the player.

Signature

```
exitFocusedInteractionMode(): void;
```

Returns

void

Remarks

This method must be called on a local player and has no effect on VR players. [Player.enterFocusedInteractionMode()](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) enables Focused Interaction mode.

  

When Focused Interaction mode is enabled, you can receive input data from the [PlayerControls.onFocusedInteractionInputStarted](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputstarted) , [PlayerControls.onFocusedInteractionInputMoved](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputmoved) , and [PlayerControls.onFocusedInteractionInputEnded](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputended) events.

  

For more information, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .</td>
    </tr>
    <tr>
      <td>**focusUI(selectable, options)**</td>
      <td>Focuses the player's camera on the given selectable entity in the world, such as a custom UI. This method only affects web and mobile clients.

Signature

```
focusUI(selectable: Entity, options?: FocusUIOptions): void;
```

Parameters

selectable: [Entity](/horizon-worlds/reference/2.0.0/core_entity) The selectable entity to focus on.

options: [FocusUIOptions](/horizon-worlds/reference/2.0.0/core_focusuioptions) *(Optional)*

 The options to apply to, such as settings for the camera view and animation transitions.

Returns

void

Remarks

You can use this method along with the method to manage the camera focus when creating a custom [UI component](/horizon-worlds/reference/2.0.0/ui_uicomponent) . For more information about creating custom UI components, see the [Custom UI panel](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/creating-a-custom-ui-panel) guide.</td>
    </tr>
    <tr>
      <td>**getAvatarOverrides()**</td>
      <td>Gets the avatar item overrides on the player.

Signature

```
getAvatarOverrides(): Array<string>;
```

Returns

Array<string>

\- An Array of Item skus

Examples

```
playerA.getAvatarOverrides();
```</td>
    </tr>
    <tr>
      <td>**hasCompletedAchievement(achievementScriptID)**</td>
      <td>Indicates whether a player has completed an achievement.

Signature

```
hasCompletedAchievement(achievementScriptID: string): boolean;
```

Parameters

achievementScriptID: string

The scriptID of the achievement. This can be accessed and set on the Achievements page in the VR creator UI.

Returns

boolean `true` if the player has the achievement, `false` otherwise.

Examples

var WonAGameAchievementScriptID = "wonAGame" var hasAchievement = player.hasCompletedAchievement(WonAGameAchievementScriptID)</td>
    </tr>
    <tr>
      <td>**playAvatarAnimation(animation, options)**</td>
      <td>Plays an animation asset on the player's avatar one time.

Signature

```
playAvatarAnimation(animation: Asset, options?: PlayAnimationOptions): void;
```

Parameters

animation: [Asset](/horizon-worlds/reference/2.0.0/core_asset) options: [PlayAnimationOptions](/horizon-worlds/reference/2.0.0/core_playanimationoptions) *(Optional)*

 The options that control how to play the animation.

Returns

void

Remarks

This method allows you to use custom animations for player avatars and access callbacks that allow your scripts to respond when the animation starts and stops.</td>
    </tr>
    <tr>
      <td>**playAvatarGripPoseAnimationByName(avatarGripPoseAnimationName, options)**</td>
      <td>Triggers an [AvatarGripPose](/horizon-worlds/reference/2.0.0/core_avatargrippose) animation by name, one time.

Signature

```
playAvatarGripPoseAnimationByName(avatarGripPoseAnimationName: string, options?: PlayAvatarGripPoseAnimationOptions): void;
```

Parameters

avatarGripPoseAnimationName: string

The avatar grip pose animation to play.

options: [PlayAvatarGripPoseAnimationOptions](/horizon-worlds/reference/2.0.0/core_playavatargripposeanimationoptions) *(Optional)*

 The optional parameters that influence how the animation is handled.

Returns

void

Examples

```
player.playAvatarGripPoseAnimationByName(AvatarGripPoseAnimationNames.Fire, {callback: (reason: hz.AnimationCallbackReasons) => {}});
```

Remarks

For more information about using this method, see the [Player Animations](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/player-animations) guide.</td>
    </tr>
    <tr>
      <td>**removeAvatarOverride(sku)**</td>
      <td>Removes an avatar item override on the player.

Signature

```
removeAvatarOverride(sku: string): boolean;
```

Parameters

sku: string

Item sku to remove

Returns

boolean

\- true if item is removed successfully, false otherwise. Will also return true if item was not in the list of overrides.

Examples

```
playerA.removeAvatarOverride(sku);
```</td>
    </tr>
    <tr>
      <td>**setAchievementComplete(achievementScriptID, complete)**</td>
      <td>Specifies whether the player's achievement is complete.

Signature

```
setAchievementComplete(achievementScriptID: string, complete: boolean): void;
```

Parameters

achievementScriptID: string

The scriptID of the achievement. This can be accessed/set on the Achievements page in the VR creator UI.

complete: boolean `true` sets the achievement to complete; `false` sets the achievement to incomplete.

Returns

void

Examples

```
var WonAGameAchievementScriptID = "wonAGame"
player.setAchievementComplete(WonAGameAchievementScriptID, true)
```</td>
    </tr>
    <tr>
      <td>**setAimAssistTarget(target, options)**</td>
      <td>Enables Aim Assistance on a target. This generates a force pulling the cursor towards a target when the aim cursor approaches it.

Signature

```
setAimAssistTarget(target: Player | Entity | Vec3, options?: AimAssistOptions): void;
```

Parameters

target: [Player](/horizon-worlds/reference/2.0.0/core_player) | [Entity](/horizon-worlds/reference/2.0.0/core_entity) | [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) The target that receives Aim Assistance.

options: [AimAssistOptions](/horizon-worlds/reference/2.0.0/core_aimassistoptions) *(Optional)*

 The options to use when applying Aim Assistance.

Returns

void

Remarks

This method must be called on a local player and has no effect on VR players.</td>
    </tr>
    <tr>
      <td>**setAvatarGripPoseOverride(avatarGripPose)**</td>
      <td>Overrides the existing HWXS avatar grip type, which is determined by the currently held grabbable.

Signature

```
setAvatarGripPoseOverride(avatarGripPose: AvatarGripPose): void;
```

Parameters

avatarGripPose: [AvatarGripPose](/horizon-worlds/reference/2.0.0/core_avatargrippose) The new pose to apply. This persists until cleared or another grip override is set. For information on clearing an override, see .

Returns

void</td>
    </tr>
    <tr>
      <td>**setAvatarOverrides(skus)**</td>
      <td>Overrides avatar items on the player. Previous overrides are overwritten. Overrides of a different style (Such as a Fantastical avatar) will replace the user's Stylized avatar fully. If there are multiple skus for the same slot (eg top), priority is given to the first one in the array. Create Avatar items in the [creator portal](https://horizon.meta.com/creator/avatars) Signature

```
setAvatarOverrides(skus: Array<string>): Promise<boolean>;
```

Parameters

skus: Array<string>

Array of Item skus to override

Returns

Promise<boolean>

\- A promise that resolves to true if items are added successfully, false otherwise

Examples

```
playerA.setAvatarOverrides([sku, anotherSku]);
```</td>
    </tr>
    <tr>
      <td>**setVoipSetting(setting)**</td>
      <td>Sets the VOIP setting for the player.

Signature

```
setVoipSetting(setting: VoipSetting): void;
```

Parameters

setting: [VoipSetting](/horizon-worlds/reference/2.0.0/core_voipsetting) The VOIP setting to use.

Returns

void</td>
    </tr>
    <tr>
      <td>**showInfoSlides(slides)**</td>
      <td>Shows info slides carousel for player.

Signature

```
showInfoSlides(slides: InfoSlide[]): void;
```

Parameters

slides: [InfoSlide](/horizon-worlds/reference/2.0.0/core_infoslide) \[\]

customized info slides that will be shown to the player

Returns

void</td>
    </tr>
    <tr>
      <td>**showInputActionMessage(inputAction, message, duration)**</td>
      <td>Initiates an attention-grabbing animation and displays a message above the on-screen button for a specified player input action. This is useful for button tooltips in timed action prompts and tutorials.

Signature

```
showInputActionMessage(inputAction: PlayerInputAction, message: i18n_utils.LocalizableText | string, duration?: number): void;
```

Parameters

inputAction: [PlayerInputAction](/horizon-worlds/reference/2.0.0/core_playerinputaction) action for which we should show the NUX animation and message

message: i18n_utils.LocalizableText | string

localizable message that should be shown above the action button

duration: number *(Optional)* duration in milliseconds for how long the message should be shown

Returns

void

Remarks

Mobile only.</td>
    </tr>
    <tr>
      <td>**showToastMessage(message, duration)**</td>
      <td>Shows the toast message at the top of the screen.

Signature

```
showToastMessage(message: i18n_utils.LocalizableText | string, duration?: number): void;
```

Parameters

message: i18n_utils.LocalizableText | string

localizable message that should be shown above the action button

duration: number *(Optional)* duration in milliseconds for how long the message should be shown

Returns

void</td>
    </tr>
    <tr>
      <td>**stopAvatarAnimation(options)**</td>
      <td>Stops any avatar animation asset that is playing.

Signature

```
stopAvatarAnimation(options?: StopAnimationOptions): void;
```

Parameters

options: [StopAnimationOptions](/horizon-worlds/reference/2.0.0/core_stopanimationoptions) *(Optional)*

 The options that control the animation.

Returns

void

Remarks

The [Player.stopAvatarAnimation()](/horizon-worlds/reference/2.0.0/core_player#stopavataranimation) method is used to play custom avatar animations.</td>
    </tr>
    <tr>
      <td>**throwHeldItem(options)**</td>
      <td>Attempts throws the item held in the specified hand.

Signature

```
throwHeldItem(options?: Partial<ThrowOptions>): void;
```

Parameters

options: Partial< [ThrowOptions](/horizon-worlds/reference/2.0.0/core_throwoptions) > *(Optional)* Options to adjust the throwing speed, yaw, pitch, and animation.

Returns

void</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the player.

Signature

```
toString(): string;
```

Returns

string

A string representation of the player.</td>
    </tr>
    <tr>
      <td>**unfocusUI()**</td>
      <td>Removes focus from any in-world UI the player's camera is currently [focused](/horizon-worlds/reference/2.0.0/core_player#focusui) on. This method only affects web and mobile clients.

Signature

```
unfocusUI(): void;
```

Returns

void

Remarks

You can use this method along with the [Player.focusUI()](/horizon-worlds/reference/2.0.0/core_player#focusui) method to manage the camera focus when creating a custom [UI component](/horizon-worlds/reference/2.0.0/ui_uicomponent) . For more information about creating custom UI components, see the [Custom UI panel](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/creating-a-custom-ui-panel) guide.</td>
    </tr>
  </tbody>
</table>