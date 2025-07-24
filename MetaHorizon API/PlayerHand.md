# PlayerHand Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playerhand)

Extends *[PlayerBodyPart](/horizon-worlds/reference/2.0.0/core_playerbodypart)* A player's hand.

## Signature

```
export declare class PlayerHand extends PlayerBodyPart
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(player, handedness)**</td>
      <td>Contructs a new `PlayerHand`.

* * *

Signature

```
constructor(player: Player, handedness: Handedness);
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player associated with the hand.

handedness: [Handedness](/horizon-worlds/reference/2.0.0/core_handedness) The player's handedness.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**handedness**

\[readonly\]</td>
      <td>The player handedness.

Signature

```
protected readonly handedness: Handedness;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**playHaptics(duration, strength, sharpness)**</td>
      <td>Plays haptic feedback on the specified hand.

Signature

```
playHaptics(duration: number, strength: HapticStrength, sharpness: HapticSharpness): void;
```

Parameters

duration: number

The duration of the feedback in MS.

strength: [HapticStrength](/horizon-worlds/reference/2.0.0/core_hapticstrength) The strength of feedback to play.

sharpness: [HapticSharpness](/horizon-worlds/reference/2.0.0/core_hapticsharpness) The sharpness of the feedback.

Returns

void</td>
    </tr>
  </tbody>
</table>