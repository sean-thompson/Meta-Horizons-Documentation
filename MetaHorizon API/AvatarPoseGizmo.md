# AvatarPoseGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_avatarposegizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Controls player interaction with the Avatar Pose gizmo, which allows players to enter an avatar pose on an entity. The gizmo is typically used to enter a player into a sitting pose on a specific entity.

## Signature

```
export declare class AvatarPoseGizmo extends Entity
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**exitAllowed**</td>
      <td>Indicates whether to allow players to exit the Avatar Pose gizmo. True allows players to exit the gizmo; false does not. The default value is `true`.

Signature

```
exitAllowed: HorizonProperty<boolean>;
```

Examples

In this example, the exitAllowed property is set false, preventing players from exiting the avatar pose.

```
this.entity.as(AvatarPoseGizmo).exitAllowed.set(false);
```</td>
    </tr>
    <tr>
      <td>**player**</td>
      <td>The player to add to the Avatar Pose gizmo.

Signature

```
player: HorizonProperty<Player | null>;
```

Examples

In this example, a player is added to the Avatar Pose gizmo, which will teleport the player to the gizmo.

```
this.entity.as(AvatarPoseGizmo).player.set(player);
```

Remarks

When a player is added to the gizmo, they teleport to the gizmo and then the avatar pose is applied to them. If another player is already on the gizmo when this property is set, they will be removed. Setting this property to null just removes any existing player from the gizmo.</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**canPlayerUse(player)**</td>
      <td>Indicates whether the given player can use the avatar pose on the entity.

Signature

```
canPlayerUse(player: Player): boolean;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player to check permissions for.

Returns

boolean `true` if the player has permission to use the avatar pose on the entity, `false` otherwise.

Examples

In this example, the canPlayerUse is used to check if a certain player can use the Avatar Pose entity. As a result, this API returns true or false.

```
this.entity.as(AvatarPoseGizmo).canPlayerUse(player);
```</td>
    </tr>
    <tr>
      <td>**resetCanUseForPlayers()**</td>
      <td>Removes all players from the list set by the [AvatarPoseGizmo.setCanUseForPlayers()](/horizon-worlds/reference/2.0.0/core_avatarposegizmo#setcanuseforplayers) method, either allowing or blocking all players from using the avatar pose on the entity depending on the mode.

Signature

```
resetCanUseForPlayers(): void;
```

Returns

void

Examples

In this example, the mode for setCanUseForPlayers is set to block all players in the list from using the avatar pose on the entity. As a result, the call to resetCanUseForPlayers blocks all players from using the avatar pose on the entity.

```
this.entity.as(AvatarPoseGizmo).setCanUseForPlayers([player1, player2], AvatarPoseUseMode.DisallowUse);
this.entity.as(AvatarPoseGizmo).resetCanUseForPlayers();
```

Remarks

If the `mode` parameter of the [AvatarPoseGizmo.setCanUseForPlayers()](/horizon-worlds/reference/2.0.0/core_avatarposegizmo#setcanuseforplayers) method is set to `AvatarPoseUseMode.DisallowUse`, then calling the `resetCanUseForPlayers` method blocks all players from using the avatar pose on the entity. If the parameter is set to `AvatarPoseUseMode.AllowUse`, `resetCanUseForPlayers` allows all players to use the avatar pose on the entity.</td>
    </tr>
    <tr>
      <td>**setCanUseForPlayers(players, mode)**</td>
      <td>Sets the players that are allowed to use the avatar pose on the entity, and the players that are blocked from using the pose.

Signature

```
setCanUseForPlayers(players: Array<Player>, mode: AvatarPoseUseMode): void;
```

Parameters

players: Array< [Player](/horizon-worlds/reference/2.0.0/core_player) >

The list of players to allow or block from using the avatar pose. The `mode` parameter determines how the list is operates.

mode: [AvatarPoseUseMode](/horizon-worlds/reference/2.0.0/core_avatarposeusemode) Indicates whether to allow players in the list to use the avatar pose and block the remaining mplayers, or block players in the list and allow the remaining players.

Returns
[LocalCamera.md](LocalCamera.md)
void[LocalCamera.md](LocalCamera.md)

Examples

In this example, the mode is set to block two specified players from using the avatar pose.
[LocalCamera.md](LocalCamera.md)
```[AssetPoolGizmo.md](AssetPoolGizmo.md)
this.entity.as(AvatarPoseGizmo).setCanUseForPlayers([player1, player2], AvatarPoseUseMode.DisallowUse);
```

Remarks

This method sets the list that determines the players that have permission to use the avatar pose on the entity associated with the Avatar Pose gizmo.

  

The `mode` parameter determines how the list operates. You can set the mode to either allow players in the list and block the remaining players, or block players in the list and allow the remaining players.

  

Calling this method replaces any existing permissions set by the list. Passing an empty array to this method blocks all players from using the avatar pose.</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the `AvatarPoseGizmo` object.

Signature

```
toString(): string;
```

Returns

string

A string representation of the `AvatarPoseGizmo` object.</td>
    </tr>
  </tbody>
</table>
