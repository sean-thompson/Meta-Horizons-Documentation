# FocusedInteraction Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_focusedinteraction)

Options for setting up and customizing visual feedback when players interact with the world in Focused Interaction mode on web and mobile clients.

## Signature

```
export declare class FocusedInteraction
```

## Remarks

Focused Interaction mode replaces on-screen controls on web and mobile clients with touch and mouse input that includes direct input access.

  

You can enable and disable Focused Interaction mode with the [Player.enterFocusedInteractionMode()](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) and [Player.exitFocusedInteractionMode()](/horizon-worlds/reference/2.0.0/core_player#exitfocusedinteractionmode) methods.

  

When Focused Interaction mode is enabled, you can subscribe to the [PlayerControls.onFocusedInteractionInputStarted](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputstarted) , 

[PlayerControls.onFocusedInteractionInputMoved](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputmoved)

, and [PlayerControls.onFocusedInteractionInputEnded](/horizon-worlds/reference/2.0.0/core_playercontrols#onfocusedinteractioninputended) events.

  

For more information, see the [Focused Interaction guide](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/how-to-use-focused-interaction) .

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(player)**</td>
      <td>Creates a new `FocusedInteraction` instance.

* * *

Signature

```
constructor(player: Player);
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player to assign to the focused interaction settings.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**player**

\[readonly\]</td>
      <td>The current player.

Signature

```
protected readonly player: Player;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| setTapOptions(isEnabled, tapOptions) | Toggle and customize the visual feedback to display when players use tap input during Focused Interaction mode.SignaturesetTapOptions(isEnabled: boolean, tapOptions?: Partial<FocusedInteractionTapOptions>): void;ParametersisEnabled: booleantrue to enable visual feedback for tap input; false to disable it.tapOptions: Partial<FocusedInteractionTapOptions>(Optional) The options to customize the tap visuals.Returnsvoid |
| setTrailOptions(isEnabled, trailOptions) | Toggle and customize visual feedback trails that are displayed when players use drag input during Focused Interaction mode.SignaturesetTrailOptions(isEnabled: boolean, trailOptions?: Partial<FocusedInteractionTrailOptions>): void;ParametersisEnabled: booleantrue to enable trails; false to disable them.trailOptions: Partial<FocusedInteractionTrailOptions>(Optional) Options to customize trail visuals.Returnsvoid |