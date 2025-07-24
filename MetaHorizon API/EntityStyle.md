# EntityStyle Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_entitystyle)

Represents a style for a Custom model entity that can change its style.

## Signature

```
export interface EntityStyle
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**brightness**</td>
      <td>Brightness in the range of 0 - 100; where 0 is black, 1 is no adjustment, and 100 is very bright; defaults to 1.

Signature

```
brightness: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**tintColor**</td>
      <td>Color in the RGB range of 0 - 1; defaults to 1, 1, 1 (no tint color).

Signature

```
tintColor: HorizonProperty<Color>;
```</td>
    </tr>
    <tr>
      <td>**tintStrength**</td>
      <td>Tint strength in the range of 0 - 1; where 0 is no tint and 1 is fully tinted; defaults to 0.

Signature

```
tintStrength: HorizonProperty<number>;
```</td>
    </tr>
  </tbody>
</table>