# TrailGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_trailgizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a trail effect in the world.

## Signature

```
export declare class TrailGizmo extends Entity
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**length**</td>
      <td>The length of the trail, in meters.

Signature

```
length: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**width**</td>
      <td>The width of the trail, in meters.

Signature

```
width: HorizonProperty<number>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**play()**</td>
      <td>Plays the trail effect.

Signature

```
play(): void;
```

Returns

void</td>
    </tr>
    <tr>
      <td>**stop()**</td>
      <td>Stops the trail effect.

Signature

```
stop(): void;
```

Returns

void</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the entity.

Signature

```
toString(): string;
```

Returns

string

A string representation of the entity.</td>
    </tr>
  </tbody>
</table>