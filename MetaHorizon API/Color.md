# Color Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_color)

Extends 

*[Comparable](/horizon-worlds/reference/2.0.0/core_comparable)

< [Color](/horizon-worlds/reference/2.0.0/core_color) >*

Represents an RGB color.

## Signature

```
export declare class Color implements Comparable<Color>
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(r, g, b)**</td>
      <td>Creates an RGB color object.

* * *

Signature

```
constructor(r: number, g: number, b: number);
```

Parameters

r: number

The red component of the RGB color as a float from 0 to 1.

g: number

The green component of the RGB color as a float from 0 to 1.

b: number

The blue component of the RGB color as a float from 0 to 1.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**b**</td>
      <td>The blue component of the RGB color.

Signature

```
b: number;
```</td>
    </tr>
    <tr>
      <td>**black**

static

  

\[readonly\]</td>
      <td>Creates a black RGB color.

Signature

```
static get black(): Color;
```</td>
    </tr>
    <tr>
      <td>**blue**

static

  

\[readonly\]</td>
      <td>Creates a blue RGB color.

Signature

```
static get blue(): Color;
```</td>
    </tr>
    <tr>
      <td>**g**</td>
      <td>The green component of the RGB color.

Signature

```
g: number;
```</td>
    </tr>
    <tr>
      <td>**green**

static

  

\[readonly\]</td>
      <td>Creates a green RGB color.

Signature

```
static get green(): Color;
```</td>
    </tr>
    <tr>
      <td>**r**</td>
      <td>The red component of the RGB color.

Signature

```
r: number;
```</td>
    </tr>
    <tr>
      <td>**red**

static

  

\[readonly\]</td>
      <td>Creates a red RGB color.

Signature

```
static get red(): Color;
```</td>
    </tr>
    <tr>
      <td>**white**

static

  

\[readonly\]</td>
      <td>Creates a white RGB color.

Signature

```
static get white(): Color;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| add(color) | Adds two RGB colors, returning a new RGB color.Signaturestatic add(colorA: Color, colorB: Color, outColor?: Color): Color;ParameterscolorA: ColorThe first RGB color to add.colorB: ColorThe second color to add.outColor: Color(Optional) The RGB color as a result of the operation. If not supplied, a new RGB color is created and returned.ReturnsColorA new RGB color, if outColor is not supplied. |
| add(colorA, colorB, outColor) static | Adds two RGB colors, returning a new RGB color.Signaturestatic add(colorA: Color, colorB: Color, outColor?: Color): Color;ParameterscolorA: ColorThe first RGB color to add.colorB: ColorThe second color to add.outColor: Color(Optional) The RGB color as a result of the operation. If not supplied, a new RGB color is created and returned.ReturnsColorA new RGB color, if outColor is not supplied. |
| addInPlace(color) | Adds an RGB color to the current RGB color, modifying the original color in place.SignatureaddInPlace(color: Color): this;Parameterscolor: ColorThe RGB color to add.Returnsthis |
| clone() | Clones the current RGB color's values into a mutable RGB color object.Signatureclone(): Color;ReturnsColora mutable RGB color with the same r, g, b values. |
| componentMul(color) | Creates an RGB color by multiplying each component of the current RGB color with the input RGB color's component.SignaturecomponentMul(color: Color): Color;Parameterscolor: ColorThe RGB color to multiply.ReturnsColorA new RGB color. |
| componentMulInPlace(color) | Multiplies the current RGB color's components by the specified RGB color's components, modifying the original RGB color in place.SignaturecomponentMulInPlace(color: Color): this;Parameterscolor: ColorThe RGB color to multiply by.Returnsthis |
| copy(color) | Sets the current RGB color to the specified RGB color.Signaturecopy(color: Color): this;Parameterscolor: ColorThe specified RGB color.Returnsthis |
| div(scalar) | Performs scalar division on an RGB color, returning a new RGB color.Signaturestatic div(color: Color, scalar: number, outColor?: Color): Color;Parameterscolor: ColorThe RGB color to scale.scalar: numberThe value to scale the RGB color by.outColor: Color(Optional) The new color as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsColorA new RGB color. |
| div(color, scalar, outColor) static | Performs scalar division on an RGB color, returning a new RGB color.Signaturestatic div(color: Color, scalar: number, outColor?: Color): Color;Parameterscolor: ColorThe RGB color to scale.scalar: numberThe value to scale the RGB color by.outColor: Color(Optional) The new color as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsColorA new RGB color. |
| divInPlace(scalar) | Divides an RGB color's components by a scalar value, modifying the original RGB color in place.SignaturedivInPlace(scalar: number): this;Parametersscalar: numberThe value to scale the color by.Returnsthis |
| equals(color) | Determines whether two RGB colors are equal.Signaturestatic equals(colorA: Color, colorB: Color): boolean;ParameterscolorA: ColorThe first RGB color to compare.colorB: ColorThe second RGB color to compare.Returnsbooleantrue if the RGB colors are equal, false otherwise. |
| equals(colorA, colorB) static | Determines whether two RGB colors are equal.Signaturestatic equals(colorA: Color, colorB: Color): boolean;ParameterscolorA: ColorThe first RGB color to compare.colorB: ColorThe second RGB color to compare.Returnsbooleantrue if the RGB colors are equal, false otherwise. |
| equalsApprox(color, epsilon) | Determines whether two RGB colors are approximately equal.Signaturestatic equalsApprox(colorA: Color, colorB: Color, epsilon?: number): boolean;ParameterscolorA: ColorThe first RGB color to compare.colorB: ColorThe second RGB color to compare.epsilon: number(Optional) The maximum difference in value to be considered equal.Returnsbooleantrue if the two RGB colors are approximatel equal, false otherwise. |
| equalsApprox(colorA, colorB, epsilon) static | Determines whether two RGB colors are approximately equal.Signaturestatic equalsApprox(colorA: Color, colorB: Color, epsilon?: number): boolean;ParameterscolorA: ColorThe first RGB color to compare.colorB: ColorThe second RGB color to compare.epsilon: number(Optional) The maximum difference in value to be considered equal.Returnsbooleantrue if the two RGB colors are approximatel equal, false otherwise. |
| fromHex(hex) static | Converts a hex code string to a Color.Signaturestatic fromHex(hex: string): Color;Parametershex: stringA six-character hex code string prefixed with #, ie: "#ff0000".ReturnsColorA Color representing the hex value. |
| fromHSV(hsv) static | Creates a new RGB color from an HSV value.Signaturestatic fromHSV(hsv: Vec3): Color;Parametershsv: Vec3The HSV color value to convert to RGB.ReturnsColorA new RGB color. |
| mul(scalar) | Performs a scalar multiplication on an RGB color, returning a new RGB color.Signaturestatic mul(color: Color, scalar: number, outColor?: Color): Color;Parameterscolor: ColorThe RGB color to scale.scalar: numberThe value to scale the RGB color by.outColor: Color(Optional) The new color as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsColorA new RGB color. |
| mul(color, scalar, outColor) static | Performs a scalar multiplication on an RGB color, returning a new RGB color.Signaturestatic mul(color: Color, scalar: number, outColor?: Color): Color;Parameterscolor: ColorThe RGB color to scale.scalar: numberThe value to scale the RGB color by.outColor: Color(Optional) The new color as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsColorA new RGB color. |
| mulInPlace(scalar) | Performs a scalar multiplication on the current RGB color, modifying the original RGB color in place.SignaturemulInPlace(scalar: number): this;Parametersscalar: numberThe value to scale the color by.Returnsthis |
| sub(color) | Subtracts an RGB color from another RGB color, returning a new RGB color.Signaturestatic sub(colorA: Color, colorB: Color, outColor?: Color): Color;ParameterscolorA: ColorThe RGB color to subtract from.colorB: ColorThe RGB color to subtract.outColor: Color(Optional) The new color as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsColorA new RGB color, if outColor is not supplied. |
| sub(colorA, colorB, outColor) static | Subtracts an RGB color from another RGB color, returning a new RGB color.Signaturestatic sub(colorA: Color, colorB: Color, outColor?: Color): Color;ParameterscolorA: ColorThe RGB color to subtract from.colorB: ColorThe RGB color to subtract.outColor: Color(Optional) The new color as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsColorA new RGB color, if outColor is not supplied. |
| subInPlace(color) | Subtracts an RGB color from the current RGB color, modifying the original RGB color in place.SignaturesubInPlace(color: Color): this;Parameterscolor: ColorThe RGB color to subtract.Returnsthis |
| toHex() | Converts an RGB color to a Hex color code.SignaturetoHex(): #${string};Returns\#${string}\The hex color code of the color. |
| toHSV() | Converts an RGB color to an HSV (hue, saturation, value) 3D vector.SignaturetoHSV(): Vec3;ReturnsVec3A 3D vector, where x is the hue, y is the saturation, and z is the value of the color. |
| toString() | Gets a string listing the RGB color components.SignaturetoString(): string;ReturnsstringA list of the components. |
| toVec3() | Gets the values of the current RGB color object as a 3D vector.SignaturetoVec3(): Vec3;ReturnsVec3 |