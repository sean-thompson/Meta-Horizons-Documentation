# IUI Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_iui)

Basic UI functions for displaying popups and tooltips.

## Signature

```
export interface IUI
```

## Remarks

For an example, see the [Lobby tutorial](https://developers.meta.com/horizon-worlds/learn/documentation/tutorials/multiplayer-lobby-tutorial/module-4-starting-the-game#display-a-countdown-timer) .

## Methods

<table>
  <tbody>
    <tr>
      <td>**dismissTooltip(player, playSound)**</td>
      <td>Dismisses any active tooltip for the target player

Signature

```
dismissTooltip(player: Player, playSound?: boolean): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) the player that has their tooltip dismissed

playSound: boolean *(Optional)* determines if a default "close sound" should play when the tooltip is closed

Returns

void</td>
    </tr>
    <tr>
      <td>**showPopupForEveryone(text, displayTime, options)**</td>
      <td>Shows a popup modal to all players.

Signature

```
showPopupForEveryone(text: string | i18n_utils.LocalizableText, displayTime: number, options?: Partial<PopupOptions>): void;
```

Parameters

text: string | i18n_utils.LocalizableText

The text to display in the popup.

displayTime: number

The duration, in seconds, to display the popup.

options: Partial< [PopupOptions](/horizon-worlds/reference/2.0.0/core_popupoptions) > *(Optional)* The configuration, such as color or position, for the popup.

Returns

void</td>
    </tr>
    <tr>
      <td>**showPopupForPlayer(player, text, displayTime, options)**</td>
      <td>Shows a popup modal to a player.

Signature

```
showPopupForPlayer(player: Player, text: string | i18n_utils.LocalizableText, displayTime: number, options?: Partial<PopupOptions>): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player to whom the popup is to displayed.

text: string | i18n_utils.LocalizableText

The text to display in the popup.

displayTime: number

The duration, in seconds, to display the popup.

options: Partial< [PopupOptions](/horizon-worlds/reference/2.0.0/core_popupoptions) > *(Optional)* The configuration, such as color or position, for the popup.

Returns

void</td>
    </tr>
    <tr>
      <td>**showTooltipForPlayer(player, tooltipAnchorLocation, tooltipText, options)**</td>
      <td>Shows a tooltip modal to a specific player

Signature

```
showTooltipForPlayer(player: Player, tooltipAnchorLocation: TooltipAnchorLocation, tooltipText: string | i18n_utils.LocalizableText, options?: Partial<TooltipOptions>): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) the player this tooltip displays for

tooltipAnchorLocation: [TooltipAnchorLocation](/horizon-worlds/reference/2.0.0/core_tooltipanchorlocation) the anchor point that is used to determine the tooltip display location

tooltipText: string | i18n_utils.LocalizableText

the message the tooltip displays

options: Partial< [TooltipOptions](/horizon-worlds/reference/2.0.0/core_tooltipoptions) > *(Optional)* configuration for the tooltip (display line, play sounds, attachment entity, etc)

Returns

void</td>
    </tr>
  </tbody>
</table>