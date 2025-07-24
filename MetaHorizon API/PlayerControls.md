# PlayerControls Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playercontrols)

Provides static methods to bind to, and query data about custom player input bindings.

## Signature

```
export declare class PlayerControls
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**onFocusedInteractionInputEnded**

static

  

\[readonly\]</td>
      <td>This event broadcasts on the last frame of input when the player ends a touch gesture or mouse click while in [Focused Interaction mode](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) .

Signature

```
static readonly onFocusedInteractionInputEnded: LocalEvent<{
        interactionInfo: InteractionInfo[];
    }>;
```

Remarks

For more information, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .</td>
    </tr>
    <tr>
      <td>**onFocusedInteractionInputMoved**

static

  

\[readonly\]</td>
      <td>This event broadcasts while the player is in [Focused Interaction mode](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) while using touch gestures or mouse clicks. The event fires on all frames of the input except for the first and last frames which instead fire the [PlayerControls.onFocusedInteractionInputStarted](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputstarted) and [PlayerControls.onFocusedInteractionInputEnded](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputended) events respectively.

Signature

```
static readonly onFocusedInteractionInputMoved: LocalEvent<{
        interactionInfo: InteractionInfo[];
    }>;
```

Remarks

For more information, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .</td>
    </tr>
    <tr>
      <td>**onFocusedInteractionInputStarted**

static

  

\[readonly\]</td>
      <td>This event fires on the first frame of input when the player starts a touch gesture or mouse click while in [Focused Interaction mode](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) .

Signature

```
static readonly onFocusedInteractionInputStarted: LocalEvent<{
        interactionInfo: InteractionInfo[];
    }>;
```

Remarks

You can also receive input data from the [PlayerControls.onFocusedInteractionInputMoved](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputmoved) and [PlayerControls.onFocusedInteractionInputEnded](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputended) events during Focused Interaction mode.

  

For more information, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .</td>
    </tr>
    <tr>
      <td>**onHolsteredItemsUpdated**

static

  

\[readonly\]</td>
      <td>This event fires when an item is holstered or unholstered. The purpose of this event is to populate a list of holstered items in a UI panel in order to allow the player to switch between them.

Signature

```
static readonly onHolsteredItemsUpdated: LocalEvent<{
        player: Player;
        items: Entity[];
        grabbedItem: Entity;
    }>;
```

Remarks

The grabbedItem also appears in the items list so this will need to be filtered out when iterating the list of items to display in the UI.</td>
    </tr>
  </tbody>
</table>

## Methods

| connectLocalInput(input, icon, disposableObject, options) static | Connects to input events for the local player.Signaturestatic connectLocalInput(input: PlayerInputAction, icon: ButtonIcon, disposableObject: DisposableObject, options?: PlayerControlsConnectOptions): PlayerInput;Parametersinput: PlayerInputActionThe action to respond to.icon: ButtonIconThe icon to use for the button, on platforms that display on-screen buttons for actions.disposableObject: DisposableObjectThe DisposableObject that controls the lifetime of the connectionoptions: PlayerControlsConnectOptions(Optional) Connection options, see PlayerControlsConnectOptions for defaults.ReturnsPlayerInputA PlayerInput instance that can be used to poll the status of the input, or register a state change callback.RemarksThis function fails if called on the server. On platforms that display on-screen buttons for actions (such as mobile), displays a button with the specified icon. |
| disableSystemControls(tapAnywhereDisabled) static | Disables the on-screen system controls for the local player.Signaturestatic disableSystemControls(tapAnywhereDisabled?: boolean): void;ParameterstapAnywhereDisabled: boolean(Optional) True to disable on-screen system controls; false to enable them. The default value is false.ReturnsvoidRemarksThis function fails if called on the server. |
| enableSystemControls() static | Enables the on-screen system controls for the local player.Signaturestatic enableSystemControls(): void;ReturnsvoidRemarksThis function fails if called on the server. |
| equipHolsteredItem(index) static | Equips the item at the selected holster index if there is oneSignaturestatic equipHolsteredItem(index: number): void;Parametersindex: numberReturnsvoid |
| equipNextHolsteredItem() static | Equips the next holstered item if there is oneSignaturestatic equipNextHolsteredItem(): void;Returnsvoid |
| equipPreviousHolsteredItem() static | Equips the previous holstered item if there is oneSignaturestatic equipPreviousHolsteredItem(): void;Returnsvoid |
| getPlatformKeyNames(action) static | Returns a list of names that represent the physical buttons or keys bound to the specified action.Signaturestatic getPlatformKeyNames(action: PlayerInputAction): Array<string>;Parametersaction: PlayerInputActionThe action to get the key names for.ReturnsArray<string>An array of key names.RemarksThis function fails if called on the server. |
| isInputActionSupported(action) static | Indicates whether the action is supported on the current platform.Signaturestatic isInputActionSupported(action: PlayerInputAction): boolean;Parametersaction: PlayerInputActionThe action to query.Returnsbooleantrue if the action is supported on the current platform; otherwise, false.RemarksThis function fails if called on the server. Connecting to an unsupported input is allowed, but the input won't activate and its axis value will remain at 0. |
| triggerContextualMultiHolsterAction() static | Triggers a contextual based multi-holstering action if one is available. This function is designed to mirror the behaviour of the system holstering button, and will open the system holstering UI if there is more than one item holstered.Signaturestatic triggerContextualMultiHolsterAction(): void;Returnsvoid |
| triggerDropAction() static | Triggers the player action to drop the currently held itemSignaturestatic triggerDropAction(): void;Returnsvoid |
| triggerInputActionDown(inputAction) static | Triggers the down event for an input action for the local player.Signaturestatic triggerInputActionDown(inputAction: PlayerInputAction): void;ParametersinputAction: PlayerInputActionThe action to trigger / activate.ReturnsvoidRemarksThis function fails if called on the server. On platforms that display on-screen buttons for actions (such as mobile), triggers the specified action. |
| triggerInputActionUp(inputAction) static | Triggers the up event for an input action for the local player.Signaturestatic triggerInputActionUp(inputAction: PlayerInputAction): void;ParametersinputAction: PlayerInputActionThe action to trigger / activate.ReturnsvoidRemarksThis function fails if called on the server. On platforms that display on-screen buttons for actions (such as mobile), triggers the specified action. |