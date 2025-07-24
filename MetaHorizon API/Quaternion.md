# Quaternion Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_quaternion)

Extends 

*[Comparable](/horizon-worlds/reference/2.0.0/core_comparable)

< [Quaternion](/horizon-worlds/reference/2.0.0/core_quaternion) >*

Represents a quaternion (a four-element vector defining the orientation of a 3D point in space).

## Signature

```
export declare class Quaternion implements Comparable<Quaternion>
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(x, y, z, w)**</td>
      <td>Creates a quaternion.

* * *

Signature

```
constructor(x: number, y: number, z: number, w: number);
```

Parameters

x: number

The x component of the quaternion.

y: number

The y component of the quaternion.

z: number

The z component of the quaternion.

w: number

The w component of the quaternion.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**fromAxisAngle**

static

  </td>
      <td>Creates a quaternion from an axis angle.

Signature

```
static fromAxisAngle: (axis: Vec3, angle: number) => Quaternion;
```</td>
    </tr>
    <tr>
      <td>**i**

static

  

\[readonly\]</td>
      <td>Creates a quaternion representing a rotation around the X-axis. Axis is not normalized.

Signature

```
static get i(): Quaternion;
```</td>
    </tr>
    <tr>
      <td>**j**

static

  

\[readonly\]</td>
      <td>Creates a quaternion representing a rotation around the Y-axis. The axis is not normalized.

Signature

```
static get j(): Quaternion;
```</td>
    </tr>
    <tr>
      <td>**k**

static

  

\[readonly\]</td>
      <td>Creates a quaternion representing a rotation around the Z-axis. The axis is not normalized.

Signature

```
static get k(): Quaternion;
```</td>
    </tr>
    <tr>
      <td>**mulVec3**

static

  </td>
      <td>Creates a copy of a 3D vector and then rotates the copy by a quaternion.

Signature

```
static mulVec3: (quat: Quaternion, vec: Vec3) => Vec3;
```</td>
    </tr>
    <tr>
      <td>**one**

static

  

\[readonly\]</td>
      <td>Creates a unit quaternion \[0,0,0,1\].

Signature

```
static get one(): Quaternion;
```</td>
    </tr>
    <tr>
      <td>**toEuler**</td>
      <td>Converts the quaternion to an Euler angle in degrees.

Signature

```
toEuler: (order?: EulerOrder) => Vec3;
```</td>
    </tr>
    <tr>
      <td>**w**</td>
      <td>The w component of the quaternion.

Signature

```
w: number;
```</td>
    </tr>
    <tr>
      <td>**x**</td>
      <td>The x component of the quaternion.

Signature

```
x: number;
```</td>
    </tr>
    <tr>
      <td>**y**</td>
      <td>The y component of the quaternion.

Signature

```
y: number;
```</td>
    </tr>
    <tr>
      <td>**z**</td>
      <td>The z component of the quaternion.

Signature

```
z: number;
```</td>
    </tr>
    <tr>
      <td>**zero**

static

  

\[readonly\]</td>
      <td>Creates a zero element quaternion.

Signature

```
static get zero(): Quaternion;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| angle() | Gets the angle, in radians, of rotation represented by the quaternion.Signatureangle(): number;ReturnsnumberThe angle in radians. |
| axis() | Gets the axis of the rotation represented by the quaternion.Signatureaxis(): Vec3;ReturnsVec3The vector that represents the axis. |
| clone() | Creates a copy of the quaternion.Signatureclone(): Quaternion;ReturnsQuaternionThe new quaternion. |
| conjugate() | Creates a quaternion that is the conjugation of a quaternion.Signaturestatic conjugate(quat: Quaternion, outQuat?: Quaternion): Quaternion;Parametersquat: QuaternionThe quaternion to conjugate.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionThe new quaternion. |
| conjugate(quat, outQuat) static | Creates a quaternion that is the conjugation of a quaternion.Signaturestatic conjugate(quat: Quaternion, outQuat?: Quaternion): Quaternion;Parametersquat: QuaternionThe quaternion to conjugate.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionThe new quaternion. |
| conjugateInPlace() | Updates the current quaternion with its conjugated values.SignatureconjugateInPlace(): this;ReturnsthisThe updated quaterion. |
| copy(quat) | Updates the values of the quaternion with the values of another quaterium.Signaturecopy(quat: Quaternion): this;Parametersquat: QuaternionThe quaternion to copy.ReturnsthisThe updated quaternion. |
| equals(quat) | Determines whether two quaternions are equal. A quaternion is equal to another quaternion if its components are equal or if the negation of its components are equal.Signaturestatic equals(quatA: Quaternion, quatB: Quaternion): boolean;ParametersquatA: QuaternionThe first quaternion to compare.quatB: QuaternionThe second quaternion to compare.Returnsbooleantrue if the quaternions are equal; otherwise, false. |
| equals(quatA, quatB) static | Determines whether two quaternions are equal. A quaternion is equal to another quaternion if its components are equal or if the negation of its components are equal.Signaturestatic equals(quatA: Quaternion, quatB: Quaternion): boolean;ParametersquatA: QuaternionThe first quaternion to compare.quatB: QuaternionThe second quaternion to compare.Returnsbooleantrue if the quaternions are equal; otherwise, false. |
| equalsApprox(quat, epsilon) | Compares the approximate equality between two quaternions. A quaternion is equal to another quaternion if its components are equal or if the negation of its components are equal.Signaturestatic equalsApprox(quatA: Quaternion, quatB: Quaternion, epsilon?: number): boolean;ParametersquatA: QuaternionThe first quaternion to compare.quatB: QuaternionThe second quaternion to compare.epsilon: number(Optional) The maxium difference in values to consider approximately equal.Returnsbooleantrue if the quaternions are approximately equal; otherwise, false. |
| equalsApprox(quatA, quatB, epsilon) static | Compares the approximate equality between two quaternions. A quaternion is equal to another quaternion if its components are equal or if the negation of its components are equal.Signaturestatic equalsApprox(quatA: Quaternion, quatB: Quaternion, epsilon?: number): boolean;ParametersquatA: QuaternionThe first quaternion to compare.quatB: QuaternionThe second quaternion to compare.epsilon: number(Optional) The maxium difference in values to consider approximately equal.Returnsbooleantrue if the quaternions are approximately equal; otherwise, false. |
| fromEuler(euler, order) static | Creates a quaternion from a Euler angle.Signaturestatic fromEuler(euler: Vec3, order?: EulerOrder): Quaternion;Parameterseuler: Vec3The Euler angle in degrees.order: EulerOrder(Optional) The order of the Euler angle. The default order is XYZ.ReturnsQuaternion |
| fromVec3(vec) static | Creates a quaternion from a 3D vector, where w is 0.Signaturestatic fromVec3(vec: Vec3): Quaternion;Parametersvec: Vec3The 3D vector to create the quaternion from.ReturnsQuaternionThe new quaternion. |
| inverse() | Gets a new quaternion that is the inverse of the specified quaternion.Signaturestatic inverse(quat: Quaternion): Quaternion;Parametersquat: QuaternionThe specified quaternion.ReturnsQuaternionThe new quaternion. |
| inverse(quat) static | Gets a new quaternion that is the inverse of the specified quaternion.Signaturestatic inverse(quat: Quaternion): Quaternion;Parametersquat: QuaternionThe specified quaternion.ReturnsQuaternionThe new quaternion. |
| inverseInPlace() | Updates the current quaternion with its inverse values.SignatureinverseInPlace(): this;ReturnsthisThe updated quaternion. |
| lookRotation(forward, up, outQuat) static | Creates a quaternion using forward and up 3D vectors.Signaturestatic lookRotation(forward: Vec3, up?: Vec3, outQuat?: Quaternion): Quaternion;Parametersforward: Vec3The forward direction of rotation; must be orthogonal to up.up: Vec3(Optional) The up direction of rotation; must be orthogonal to forward. The default value is Vec3.up.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If not supplied, a new quaternion is created and returned.ReturnsQuaternionThe quaternion aimed at the provided 3D vectors. |
| mul(quat) | Gets a quaternion that is the product of two quaternions.Signaturestatic mul(quatA: Quaternion, quatB: Quaternion, outQuat?: Quaternion): Quaternion;ParametersquatA: QuaternionThe first quaternion to multiply.quatB: QuaternionThe second uaternion to multiply.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionA new quaternion. |
| mul(quatA, quatB, outQuat) static | Gets a quaternion that is the product of two quaternions.Signaturestatic mul(quatA: Quaternion, quatB: Quaternion, outQuat?: Quaternion): Quaternion;ParametersquatA: QuaternionThe first quaternion to multiply.quatB: QuaternionThe second uaternion to multiply.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionA new quaternion. |
| mulInPlace(quat) | Updates the current quaternion by multiplying it by another quaternion.SignaturemulInPlace(quat: Quaternion): this;Parametersquat: QuaternionThe quaternion to use as the multiplier.ReturnsthisThe current quaternion. |
| normalize() | Gets a new quaternion that is the normalized version of the specified quaternion.Signaturestatic normalize(quat: Quaternion, outQuat?: Quaternion): Quaternion;Parametersquat: QuaternionThe specified quaternion.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionThe new normalized quaternion. |
| normalize(quat, outQuat) static | Gets a new quaternion that is the normalized version of the specified quaternion.Signaturestatic normalize(quat: Quaternion, outQuat?: Quaternion): Quaternion;Parametersquat: QuaternionThe specified quaternion.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionThe new normalized quaternion. |
| normalizeInPlace() | Updates the current quaterion with its normalized values.SignaturenormalizeInPlace(): this;ReturnsthisThe updated quaternion |
| slerp(left, right, amount, outQuat) static | Peforms slerp (spherical linear interpolation) between two quaternions.Signaturestatic slerp(left: Quaternion, right: Quaternion, amount: number, outQuat?: Quaternion): Quaternion;Parametersleft: QuaternionThe leftmost quaternion.right: QuaternionThe rightmost quaternion.amount: numberDefines the gradient to use for interpolation, clamped 0 to 1.outQuat: Quaternion(Optional) The quaternion to perform the operation on. If this isn't supplied, a new quaternion is created and returned.ReturnsQuaternionA new interpolated quaternion. |
| toString() | Gets a human-readable represention of the quaternion.SignaturetoString(): string;Returnsstringa string representation of the quaternion. |