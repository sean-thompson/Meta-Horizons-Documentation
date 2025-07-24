# GrabbableEntity Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_grabbableentity)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents an entity that a player can grab.

## Signature

```
export declare class GrabbableEntity extends Entity
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**forceHold(player, hand, allowRelease)**</td>
      <td>Forces the player to hold the entity and attach it to a hand they control.

Signature

```
forceHold(player: Player, hand: Handedness, allowRelease: boolean): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player that grabs the entity.

hand: [Handedness](/horizon-worlds/reference/2.0.0/core_handedness) The player's hand that is grabbing the entity.

allowRelease: boolean

true if the player can release the entity when they are holding it; otherwise, fals.

Returns

void</td>
    </tr>
    <tr>
      <td>**forceRelease()**</td>
      <td>Forces the player to release the entity.

Signature

```
forceRelease(): void;
```

Returns

void</td>
    </tr>
    <tr>
      <td>**setWhoCanGrab(players)**</td>
      <td>Specifies the players that can grab the entity.

Signature

```
setWhoCanGrab(players: Array<Player>): void;
```

Parameters

players: Array< [Player](/horizon-worlds/reference/2.0.0/core_player) >

An array of players that can grab the entity.

Returns

void</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the GrabbableEntity.

Signature

```
toString(): string;
```

Returns

string

A string representation of the GrabbableEntity.</td>
    </tr>
  </tbody>
</table>