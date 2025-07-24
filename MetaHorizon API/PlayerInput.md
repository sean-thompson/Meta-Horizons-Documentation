# PlayerInput Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playerinput)

A customizable player input that is bound to an [input action](/horizon-worlds/reference/2.0.0/core_playerinputaction) on a player's input device, such as a VR controller, gamepad, or on-screen button.

## Signature

```
export declare class PlayerInput
```

## Remarks

You can create a `PlayerInput` instance by calling the [PlayerControls.connectLocalInput()](/horizon-worlds/reference/2.0.0/core_playercontrols#connectlocalinput) method.

  

For more information about binding player input, see the [Custom Input API](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/custom-input-api) guide.

## Properties

<table>
  <tbody>
    <tr>
      <td>**action**</td>
      <td>The action this input is bound to. For analog inputs, a pressed state corresponds to an axis value greater than 0.5 or lesser than -0.5.

Signature

```
action: ReadableHorizonProperty<PlayerInputAction>;
```</td>
    </tr>
    <tr>
      <td>**axisValue**</td>
      <td>Gets the axis value, between -1 and 1. If the input is digital, 0 or 1 is returned.

Signature

```
axisValue: ReadableHorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**connected**</td>
      <td>Indicates whether the input is currently connected and active.

Signature

```
connected: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**held**</td>
      <td>Indicates whether the input is being held active. For analog inputs, a pressed state corresponds to an axis value greater than 0.5 or lesser than -0.5.

Signature

```
held: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**pressed**</td>
      <td>Indicates whether the input was pressed this frame.

Signature

```
pressed: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**released**</td>
      <td>Indicates whether the input was released this frame.

Signature

```
released: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| disconnect() | Disconnects the input. On platforms that display on-screen buttons for actions, the button will be removed. Any callbacks registered to this instance will stop being called.Signaturedisconnect(): void;Returnsvoid |
| registerCallback(callback) | Registers a callback that is called when the input is pressed or released. For analog inputs, a pressed state corresponds to an axis value greater than 0.5 or lesser than -0.5.SignatureregisterCallback(callback: PlayerInputStateChangeCallback): void;Parameterscallback: PlayerInputStateChangeCallbackThe callback that is called when the pressed state changes.Returnsvoid |
| unregisterCallback() | Unregisters the currently registered callback, if any.SignatureunregisterCallback(): void;Returnsvoid |

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)