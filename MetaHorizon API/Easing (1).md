# Easing Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_easing)

A set of easing functions for configuring [timing animations](/horizon-worlds/reference/2.0.0/ui_timinganimationconfig) . Easing functions provide physical motion animations.

## Signature

```
export declare class Easing
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**back**

static

  

\[readonly\]</td>
      <td>A back easing.

Signature

```
static get back(): Easing;
```</td>
    </tr>
    <tr>
      <td>**bounce**

static

  

\[readonly\]</td>
      <td>An easing that provides a bouncing animation.

Signature

```
static get bounce(): Easing;
```</td>
    </tr>
    <tr>
      <td>**circle**

static

  

\[readonly\]</td>
      <td>A circular easing.

Signature

```
static get circle(): Easing;
```</td>
    </tr>
    <tr>
      <td>**cubic**

static

  

\[readonly\]</td>
      <td>A cubic easing.

Signature

```
static get cubic(): Easing;
```</td>
    </tr>
    <tr>
      <td>**ease**

static

  

\[readonly\]</td>
      <td>An easing that starts slow, accelerates quickly, and then gradually slows down until stopping.

Signature

```
static get ease(): Easing;
```</td>
    </tr>
    <tr>
      <td>**exp**

static

  

\[readonly\]</td>
      <td>An exponential easing.

Signature

```
static get exp(): Easing;
```</td>
    </tr>
    <tr>
      <td>**linear**

static

  

\[readonly\]</td>
      <td>A linear easing.

Signature

```
static get linear(): Easing;
```</td>
    </tr>
    <tr>
      <td>**quad**

static

  

\[readonly\]</td>
      <td>A quadratic easing.

Signature

```
static get quad(): Easing;
```</td>
    </tr>
    <tr>
      <td>**sin**

static

  

\[readonly\]</td>
      <td>A sin easing.

Signature

```
static get sin(): Easing;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| bezier(x1, y1, x2, y2) static | Returns an easing that uses a cubic bezier curve.Signaturestatic bezier(x1: number, y1: number, x2: number, y2: number): Easing;Parametersx1: numberThe x coordinate of the first control point of the curve.y1: numberThe y coordinate of the first control point of the curve.x2: numberThe x coordinate of the second control point of the curve.y2: numberThe y coordinate of the second control point of the curve.ReturnsEasing |
| elastic(bounciness) static | Returns and elastic easing.Signaturestatic elastic(bounciness: number): Easing;Parametersbounciness: numberReturnsEasingThe updated easing. |
| in(easing) static | Returns an easing that runs forwards.Signaturestatic in(easing: Easing): Easing;Parameterseasing: EasingThe easing to update.ReturnsEasingThe updated easing. |
| inOut(easing) static | Returns an easing that runs forwards and then backwards.Signaturestatic inOut(easing: Easing): Easing;Parameterseasing: EasingThe easing to update.ReturnsEasingThe updated easing. |
| out(easing) static | Returns an easing that runs backwards.Signaturestatic out(easing: Easing): Easing;Parameterseasing: EasingThe easing to update.ReturnsEasingThe updated easing. |
| poly(n) static | Returns a power easing.Signaturestatic poly(n: number): Easing;Parametersn: numberReturnsEasingThe updated easing. |