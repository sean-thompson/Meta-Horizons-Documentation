# TriggerGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_triggergizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a Trigger gizmo in the world, which triggers an event when a player enters or exits a given area.

## Signature

```
export declare class TriggerGizmo extends Entity
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**enabled**</td>
      <td>Indicates whether the Trigger gizmo is enabled.

Signature

```
enabled: WritableHorizonProperty<boolean>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**getWhoCanTrigger()**</td>
      <td>Gets all the players that can trigger the Trigger gizmo.

Signature

```
getWhoCanTrigger(): Array<Player>;
```

Returns

Array< [Player](/horizon-worlds/reference/2.0.0/core_player) >

An array of players that can trigger the gizmo.

Remarks

If the trigger is set to `Objects`, it returns an empty array.

  

If the trigger is set to `Players`, it returns all players (default) or the players specified by a [TriggerGizmo.setWhoCanTrigger()](/horizon-worlds/reference/2.0.0/core_triggergizmo#setwhocantrigger) call.</td>
    </tr>
    <tr>
      <td>**setWhoCanTrigger(players)**</td>
      <td>Specifies the players that can trigger the Trigger gizmo.

Signature

```
setWhoCanTrigger(players: 'anyone' | Array<Player>): void;
```

Parameters

players: 'anyone' | Array< [Player](/horizon-worlds/reference/2.0.0/core_player) >

An array of players that can trigger the gizmo, or `anyone` (default).

Returns

void

Examples

```
trigger.setWhoCanTrigger('anyone'); // anyone can trigger
trigger.setWhoCanTrigger([]); // no one can trigger
trigger.setWhoCanTrigger([player1, player2]); // only those 2 players can trigger
```</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the `TriggerGizmo` object.

Signature

```
toString(): string;
```

Returns

string

A string representation `TriggerGizmo` object.</td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)