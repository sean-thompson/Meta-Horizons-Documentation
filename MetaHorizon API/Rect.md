# Rect Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_rect)

Represents a 2D rectangle

## Signature

```
export declare class Rect
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(x, y, width, height)**</td>
      <td>Creates a Rectangle.

* * *

Signature

```
constructor(x: number, y: number, width: number, height: number);
```

Parameters

x: number

The starting point of the rectangle along the X axis.

y: number

The starting point of the rectangle along the Y axis

width: number

The width of the rectangle.

height: number

The height of the rectangle.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**height**</td>
      <td>The height of the rectangle

Signature

```
height: number;
```</td>
    </tr>
    <tr>
      <td>**width**</td>
      <td>The width of the rectangle

Signature

```
width: number;
```</td>
    </tr>
    <tr>
      <td>**x**</td>
      <td>The starting point of the rectangle along the X axis.

Signature

```
x: number;
```</td>
    </tr>
    <tr>
      <td>**y**</td>
      <td>The starting point of the rectangle along the Y axis

Signature

```
y: number;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| clone() | Clones a Rectangle's values into a mutable Rect.Signatureclone(): Rect;ReturnsRectA mutable Rect with the same x,y,width,height values. |
| copy(rect) | Copies the specified Rect (x, y, width, height) into this.Signaturecopy(rect: Rect): this;Parametersrect: RectThe Rectangle to copy from.ReturnsthisA reference to this after the values have been copied. |
| scaleBy(width, height) | Scales the Rectangle by the provided dimensions.SignaturescaleBy(width: number, height: number): this;Parameterswidth: numberthe width to scale this rectangular byheight: numberthe height to scale this rectangular byReturnsthis |
| toString() | Gets a string representation of the x, y, width and height values for the Rectangle.SignaturetoString(): string;ReturnsstringThe string representation of the Rectangle. |