# SpawnPointGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_spawnpointgizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* A Spawn Point gizmo, which you can use to teleport players to a location in a world using a fade-out/fade-in transition.

## Signature

```
export declare class SpawnPointGizmo extends Entity
```

## Remarks

For more information about using the Spawn Point gizmo, see [Spawn Points](https://developers.meta.com/horizon-worlds/learn/documentation/tutorials/multiplayer-lobby-tutorial/module-5-entering-the-match) guide.

## Properties

<table>
  <tbody>
    <tr>
      <td>**gravity**</td>
      <td>The gravity for players spawned using this gizmo.

Signature

```
gravity: HorizonProperty<number>;
```

Remarks

Range = (0, 9.81)</td>
    </tr>
    <tr>
      <td>**speed**</td>
      <td>The speed for players spawned using this gizmo.

Signature

```
speed: HorizonProperty<number>;
```

Remarks

Range = (0, 45)</td>
    </tr>
  </tbody>
</table>

## Methods

| teleportPlayer(player) | Teleports a player to the spawn point.SignatureteleportPlayer(player: Player): void;Parametersplayer: PlayerThe player to teleport.Returnsvoid |
| toString() | Creates a human-readable representation of the SpawnPointGizmo.SignaturetoString(): string;ReturnsstringA string representation of the SpawnPointGizmo. |