# PlayerBodyPart Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playerbodypart)

Represents a player body part.

## Signature

```
export declare class PlayerBodyPart
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(player, type)**</td>
      <td>Creates a `PlayerBodyPart`.

* * *

Signature

```
constructor(player: Player, type: PlayerBodyPartType);
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player that owns the body part.

type: [PlayerBodyPartType](/horizon-worlds/reference/2.0.0/core_playerbodyparttype) The type of the body part.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**forward**</td>
      <td>The forward direction of the body part.

Signature

```
forward: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**localPosition**</td>
      <td>The position of the body part relative to the player's torso.

Signature

```
localPosition: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**localRotation**</td>
      <td>The local rotation of the body part relative to the player's torso.

Signature

```
localRotation: ReadableHorizonProperty<Quaternion>;
```</td>
    </tr>
    <tr>
      <td>**player**

\[readonly\]</td>
      <td>The player that owns the body part.

Signature

```
protected readonly player: Player;
```</td>
    </tr>
    <tr>
      <td>**position**</td>
      <td>The position of the body part relative to the player.

Signature

```
position: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**rotation**</td>
      <td>The rotation of the body part relative to the player's body.

Signature

```
rotation: ReadableHorizonProperty<Quaternion>;
```</td>
    </tr>
    <tr>
      <td>**type**

\[readonly\]</td>
      <td>The type of the body part.

Signature

```
protected readonly type: PlayerBodyPartType;
```</td>
    </tr>
    <tr>
      <td>**up**</td>
      <td>The up direction of the body part.

Signature

```
up: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| getPosition(space) | Gets the world or the local position of the body part.SignaturegetPosition(space: Space): Vec3;Parametersspace: SpaceIndicates whether to get the world or local position of the body part.ReturnsVec3The position of the body part in this space. |
| getRotation(space) | Gets the rotation or the local rotation of the body part.SignaturegetRotation(space: Space): Quaternion;Parametersspace: SpaceIndicates whether to get the world or local rotation of the body part.ReturnsQuaternionThe rotation of the body part in this space. |