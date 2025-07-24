# Transform Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_transform)

A transform for an entity, which represents the position, rotation, and scale of the entity in a world.

## Signature

```
export declare class Transform
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(entity)**</td>
      <td>Constructs a new instance of the `Transform` class.

* * *

Signature

```
constructor(entity: Entity);
```

Parameters

entity: [Entity](/horizon-worlds/reference/2.0.0/core_entity) The entity to transform.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**localPosition**</td>
      <td>The local position of the entity relative to its parent.

Signature

```
localPosition: HorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**localRotation**</td>
      <td>Represents the rotation component of the entity relative to its parent.

Signature

```
localRotation: HorizonProperty<Quaternion>;
```</td>
    </tr>
    <tr>
      <td>**localScale**</td>
      <td>Represents the local scale of the entity relative to its parent.

Signature

```
localScale: HorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**position**</td>
      <td>The position of the entity in the world.

Signature

```
position: HorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**rotation**</td>
      <td>The rotation component of the entity.

Signature

```
rotation: HorizonProperty<Quaternion>;
```</td>
    </tr>
    <tr>
      <td>**scale**</td>
      <td>The scale of the entity in the world in the world.

Signature

```
scale: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
  </tbody>
</table>