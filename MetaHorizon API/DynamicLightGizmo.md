# DynamicLightGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_dynamiclightgizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a dynamic lighting gizmo in the world, which provides lighting that's calculated in real-time.

## Signature

```
export declare class DynamicLightGizmo extends Entity
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**enabled**</td>
      <td>Indicates whether the entity has a dynamic light effect on it. true to enable dynamic lighting; otherwise, false.

Signature

```
enabled: HorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**falloffDistance**</td>
      <td>The light falloff distance. 0 for the least distance and 100 for the greatest distance.

Signature

```
falloffDistance: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**intensity**</td>
      <td>The light intensity. 0 for least intense and 10 for most intense.

Signature

```
intensity: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**spread**</td>
      <td>The light spread. 0 for the least light spread (none) and 100 for the greatest light spread.

Signature

```
spread: HorizonProperty<number>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| toString() | Creates a human-readable representation of the DynamicLightGizmo.SignaturetoString(): string;ReturnsstringA string representation of the DynamicLightGizmo. |