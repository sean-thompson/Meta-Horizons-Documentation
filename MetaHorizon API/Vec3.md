# Vec3 Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_vec3)

Extends 

*[Comparable](/horizon-worlds/reference/2.0.0/core_comparable)

< [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) >*

Represents a 3D vector. This is the main class for creating and updating 3D points and directions in Meta Horizon Worlds.

## Signature

```
export declare class Vec3 implements Comparable<Vec3>
```

## Examples

In this example, an [entity](/horizon-worlds/reference/2.0.0/core_entity) is moved to a new location in a world by updating the properties of a `Vec3` object.

```
entity.position.set(new Vec3(10, 20, 52));
```

## Remarks

For information about rotating 3D vectors, see the [Quaternion](/horizon-worlds/reference/2.0.0/core_quaternion) class.

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(x, y, z)**</td>
      <td>Creates a 3D vector.

* * *

Signature

```
constructor(x: number, y: number, z: number);
```

Parameters

x: number

The magnitude of the 3D vector along the X axis.

y: number

The magnitude of the 3D vector along the Y axis.

z: number

The magnitude of the 3D vector along the Z axis.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**backward**

static

  

\[readonly\]</td>
      <td>A backward 3D vector: Vec3(0, 0, -1).

Signature

```
static get backward(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**down**

static

  

\[readonly\]</td>
      <td>A down 3D vector: Vec3(0, -1, 0).

Signature

```
static get down(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**forward**

static

  

\[readonly\]</td>
      <td>A forward 3D vector: Vec3(0, 0, 1).

Signature

```
static get forward(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**left**

static

  

\[readonly\]</td>
      <td>A left 3D vector: Vec3(-1, 0, 0).

Signature

```
static get left(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**one**

static

  

\[readonly\]</td>
      <td>A one 3D vector: Vec3(1, 1, 1).

Signature

```
static get one(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**right**

static

  

\[readonly\]</td>
      <td>A right 3D vector: Vec3(1, 0, 0).

Signature

```
static get right(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**up**

static

  

\[readonly\]</td>
      <td>An up 3D vector: Vec3(0, 1, 0).

Signature

```
static get up(): Vec3;
```</td>
    </tr>
    <tr>
      <td>**x**</td>
      <td>The magnitude of the 3D vector along the X axis.

Signature

```
x: number;
```</td>
    </tr>
    <tr>
      <td>**y**</td>
      <td>The magnitude of the 3D vector along the Y axis.

Signature

```
y: number;
```</td>
    </tr>
    <tr>
      <td>**z**</td>
      <td>The magnitude of the 3D vector along the Z axis.

Signature

```
z: number;
```</td>
    </tr>
    <tr>
      <td>**zero**

static

  

\[readonly\]</td>
      <td>A zero 3D vector: Vec3(0, 0, 0).

Signature

```
static get zero(): Vec3;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| add(vec) | Adds two 3D vectors and returns the result in a new or an existing 3D vector.Signaturestatic add(vecA: Vec3, vecB: Vec3, outVec?: Vec3): Vec3;ParametersvecA: Vec3The first 3D vector to add.vecB: Vec3The second 3D vector to add.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3The new 3D vector that is the sum, if outVec is not provided. |
| add(vecA, vecB, outVec) static | Adds two 3D vectors and returns the result in a new or an existing 3D vector.Signaturestatic add(vecA: Vec3, vecB: Vec3, outVec?: Vec3): Vec3;ParametersvecA: Vec3The first 3D vector to add.vecB: Vec3The second 3D vector to add.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3The new 3D vector that is the sum, if outVec is not provided. |
| addInPlace(vec) | Adds a 3D vector to the current 3D vector, modifying the original 3D vector.SignatureaddInPlace(vec: Vec3): this;Parametersvec: Vec3The 3D vector to add.Returnsthis |
| clone() | Clones a 3D vector's values into a mutable Vec3.Signatureclone(): Vec3;ReturnsVec3A mutable Vec3 with the same x,y,z values. |
| componentDiv(vec) | Divides the current 3D vector's components by another 3D vector's components and returns the results.SignaturecomponentDiv(vec: Vec3): Vec3;Parametersvec: Vec3The 3D vector to use as the divisor.ReturnsVec3A new 3D vector.RemarksThe division is performed as follows (a.x/b.x, a.y/b.y, a.z/b.z). |
| componentDivInPlace(vec) | Divides the current 3D Vector by another 3D vector, modifying the original 3D vector.SignaturecomponentDivInPlace(vec: Vec3): this;Parametersvec: Vec3The 3D vector to divide by.Returnsthis |
| componentMul(vec) | Creates a 3D vector by multiplying the current 3D vector's components by another 3D vector's components.SignaturecomponentMul(vec: Vec3): Vec3;Parametersvec: Vec3The additional 3D vector to multiply.ReturnsVec3A new 3D vector.RemarksThe vector components are multiplied as follows (a.x\*b.x, a.y\*b.y, a.z\*b.z). |
| componentMulInPlace(vec) | Muliplies the current 3D vector by another 3D vector, modifying the original 3D vector.SignaturecomponentMulInPlace(vec: Vec3): this;Parametersvec: Vec3The 3D vector to multiply.Returnsthis |
| copy(vec) | Creates a copy of the specified 3D vector with the same x, y, and z values.Signaturecopy(vec: Vec3): this;Parametersvec: Vec3The 3D vector to copy.ReturnsthisA new 3D vector. |
| cross(vec) | Gets the cross product of two 3D vectors and returns the result in a new or an existing 3D vector.Signaturestatic cross(vecA: Vec3, vecB: Vec3, outVec?: Vec3): Vec3;ParametersvecA: Vec3The left side 3D vector of the cross product.vecB: Vec3The right side 3D vector of the cross product.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| cross(vecA, vecB, outVec) static | Gets the cross product of two 3D vectors and returns the result in a new or an existing 3D vector.Signaturestatic cross(vecA: Vec3, vecB: Vec3, outVec?: Vec3): Vec3;ParametersvecA: Vec3The left side 3D vector of the cross product.vecB: Vec3The right side 3D vector of the cross product.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| crossInPlace(vec) | Gets the cross product of the current 3D vector and another 3D vector, and modifies the current vector with the result.SignaturecrossInPlace(vec: Vec3): this;Parametersvec: Vec3The additional 3D vector to compute the cross product with.Returnsthis |
| distance(vec) | Gets the distance between the current 3D vector and another 3D vector.Signaturedistance(vec: Vec3): number;Parametersvec: Vec3The 3D vector to compare.ReturnsnumberThe distance between the 3D vectors. |
| distanceSquared(vec) | Gets the squared distance between the current 3D vector and another 3D vector.SignaturedistanceSquared(vec: Vec3): number;Parametersvec: Vec3The 3D vector to compare.ReturnsnumberThe squared distance between the 3D vectors. |
| div(scalar) | Performs a scalar division on a 3D vector and returns the result in a new or an existing 3D vector.Signaturestatic div(vec: Vec3, scalar: number, outVec?: Vec3): Vec3;Parametersvec: Vec3The 3D vector to scale.scalar: numberThe value to scale the 3D vector by.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| div(vec, scalar, outVec) static | Performs a scalar division on a 3D vector and returns the result in a new or an existing 3D vector.Signaturestatic div(vec: Vec3, scalar: number, outVec?: Vec3): Vec3;Parametersvec: Vec3The 3D vector to scale.scalar: numberThe value to scale the 3D vector by.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| divInPlace(scalar) | Divides the current 3D vector by a scalar value, modifying the original 3D vector.SignaturedivInPlace(scalar: number): this;Parametersscalar: numberThe scalar value to divide by.Returnsthis |
| dot(vec) | Gets the dot product of the two 3D vectors.Signaturestatic dot(vecA: Vec3, vecB: Vec3): number;ParametersvecA: Vec3The first 3D vector of the dot product.vecB: Vec3The second 3D vector of the dot product.ReturnsnumberThe dot product of the 3D vectors. |
| dot(vecA, vecB) static | Gets the dot product of the two 3D vectors.Signaturestatic dot(vecA: Vec3, vecB: Vec3): number;ParametersvecA: Vec3The first 3D vector of the dot product.vecB: Vec3The second 3D vector of the dot product.ReturnsnumberThe dot product of the 3D vectors. |
| equals(vec) | Determines whether two 3D vectors are equal.Signaturestatic equals(vecA: Vec3, vecB: Vec3): boolean;ParametersvecA: Vec3The first 3D vector to compare.vecB: Vec3The second 3D vector to compare.Returnsbooleantrue if the 3D vectors are equal; false otherwise.Remarks3D vectors are equal if they have the same x, y, and z components.To determine whether the vectors are within a given range of each other, see the method. |
| equals(vecA, vecB) static | Determines whether two 3D vectors are equal.Signaturestatic equals(vecA: Vec3, vecB: Vec3): boolean;ParametersvecA: Vec3The first 3D vector to compare.vecB: Vec3The second 3D vector to compare.Returnsbooleantrue if the 3D vectors are equal; false otherwise.Remarks3D vectors are equal if they have the same x, y, and z components.To determine whether the vectors are within a given range of each other, see the method. |
| equalsApprox(vec, epsilon) | Determines whether two 3D vectors are relatively equal.Signaturestatic equalsApprox(vecA: Vec3, vecB: Vec3, epsilon?: number): boolean;ParametersvecA: Vec3The first 3D vector to compare.vecB: Vec3The second 3D vector to compare.epsilon: number(Optional) The maxium difference to consider equal.Returnsbooleantrue if the 3D vectors are relatively equal; false otherwise.RemarksThe vectors are relatively equal if the difference between their x, y, and z components doesn't exceed the value provided in the epsilon parameter.To determine whether the vectors are equal, see . |
| equalsApprox(vecA, vecB, epsilon) static | Determines whether two 3D vectors are relatively equal.Signaturestatic equalsApprox(vecA: Vec3, vecB: Vec3, epsilon?: number): boolean;ParametersvecA: Vec3The first 3D vector to compare.vecB: Vec3The second 3D vector to compare.epsilon: number(Optional) The maxium difference to consider equal.Returnsbooleantrue if the 3D vectors are relatively equal; false otherwise.RemarksThe vectors are relatively equal if the difference between their x, y, and z components doesn't exceed the value provided in the epsilon parameter.To determine whether the vectors are equal, see . |
| lerp(vecA, vecB, amount, outVec) static | Performs a lerp (linear interpolation) between two 3D vectors.Signaturestatic lerp(vecA: Vec3, vecB: Vec3, amount: number, outVec?: Vec3): Vec3;ParametersvecA: Vec3The first vec3 to lerp.vecB: Vec3The second vec3 to lerp.amount: numberThe gradient to use for interpolation (clamped 0 to 1)outVec: Vec3(Optional) The new 3D vector as a result of the operation. If not supplied, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not supplied. |
| magnitude() | Gets the magnitude of a 3D vector.Signaturemagnitude(): number;ReturnsnumberThe magnitude of the 3D vector.RemarksThe magnitude of a 3D vector is its length. |
| magnitudeSquared() | Gets the squared magnitude of a 3D vector.SignaturemagnitudeSquared(): number;Returnsnumber |
| mul(scalar) | Performs a scalar multiplication on a 3D vector and returns the result in a new or an existing 3D vector.Signaturestatic mul(vec: Vec3, scalar: number, outVec?: Vec3): Vec3;Parametersvec: Vec3The 3D vector to scale.scalar: numberThe value to scale the 3D vector by.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| mul(vec, scalar, outVec) static | Performs a scalar multiplication on a 3D vector and returns the result in a new or an existing 3D vector.Signaturestatic mul(vec: Vec3, scalar: number, outVec?: Vec3): Vec3;Parametersvec: Vec3The 3D vector to scale.scalar: numberThe value to scale the 3D vector by.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| mulInPlace(scalar) | Multiplies the current 3D vector by a scalar value, modifying the original 3D vector.SignaturemulInPlace(scalar: number): this;Parametersscalar: numberThe value to scale the 3D vector by.Returnsthis |
| normalize() | Normalizes a 3D vector (changes the magnitude to 1) and returns the result in a new or an existing 3D vector.Signaturestatic normalize(vec: Vec3, outVec?: Vec3): Vec3;Parametersvec: Vec3The 3D vector to normalize.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| normalize(vec, outVec) static | Normalizes a 3D vector (changes the magnitude to 1) and returns the result in a new or an existing 3D vector.Signaturestatic normalize(vec: Vec3, outVec?: Vec3): Vec3;Parametersvec: Vec3The 3D vector to normalize.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| normalizeInPlace() | Normalizes the 3D vector (changes its magnitude to 1).SignaturenormalizeInPlace(): this;Returnsthis |
| reflect(normal) | Reflects the current 3D vector off a surface defined by a normal and returns the result.Signaturereflect(normal: Vec3): Vec3;Parametersnormal: Vec3The normal vector that defines the reflecting surface. This value should be normalized.ReturnsVec3A new 3D vector that defines the reflection. |
| reflectInPlace(normal) | Reflects the current 3D vector off a surface defined by a normal and modifies the orginal vector with the result.SignaturereflectInPlace(normal: Vec3): this;Parametersnormal: Vec3The normal vector that defines the reflecting surface. This value should be normalized.Returnsthis |
| sub(vec) | Subtracts a 3D vector from another and returns the result in a new or an existing 3D vector.Signaturestatic sub(vecA: Vec3, vecB: Vec3, outVec?: Vec3): Vec3;ParametersvecA: Vec3The 3D vector to substract from.vecB: Vec3The 3D vector to subtract.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| sub(vecA, vecB, outVec) static | Subtracts a 3D vector from another and returns the result in a new or an existing 3D vector.Signaturestatic sub(vecA: Vec3, vecB: Vec3, outVec?: Vec3): Vec3;ParametersvecA: Vec3The 3D vector to substract from.vecB: Vec3The 3D vector to subtract.outVec: Vec3(Optional) The resulting 3D vector. If not provided, a new 3D vector is created and returned.ReturnsVec3A new 3D vector, if outVec is not provided. |
| subInPlace(vec) | Subtracts a 3D vector from the current 3D vector, modifying the original 3D vector.SignaturesubInPlace(vec: Vec3): this;Parametersvec: Vec3The 3D vector to subtract.Returnsthis |
| toString() | Gets a string representation of the x, y, and z values for the 3D vector.SignaturetoString(): string;ReturnsstringThe x, y, and z values. |