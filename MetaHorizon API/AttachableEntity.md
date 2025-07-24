# AttachableEntity Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_attachableentity)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents an entity that can be attached to other entities.

## Signature

```
export declare class AttachableEntity extends Entity
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**socketAttachmentPosition**</td>
      <td>The socket attachment position offset applied to the `AttachableEntity` when using Anchor attachment mode.

Signature

```
socketAttachmentPosition: HorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**socketAttachmentRotation**</td>
      <td>The socket attachment rotation offset applied to the `AttachableEntity` when using Anchor attachment mode.

Signature

```
socketAttachmentRotation: HorizonProperty<Quaternion>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**attachToPlayer(player, anchor)**</td>
      <td>Attaches the entity to a player.

Signature

```
attachToPlayer(player: Player, anchor: AttachablePlayerAnchor): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player to attach the entity to.

anchor: [AttachablePlayerAnchor](/horizon-worlds/reference/2.0.0/core_attachableplayeranchor) The attachment point to use.

Returns

void</td>
    </tr>
    <tr>
      <td>**detach()**</td>
      <td>Releases an attachment to a player.

Signature

```
detach(): void;
```

Returns

void</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the object.

Signature

```
toString(): string;
```

Returns

string

A string representation of the object</td>
    </tr>
  </tbody>
</table>
