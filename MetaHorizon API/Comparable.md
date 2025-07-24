# Comparable Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_comparable)

The Comparable interface defines a set of methods for comparing values of the same type, including [equals()](/horizon-worlds/reference/2.0.0/core_comparable#equals) and [equalsApprox()](/horizon-worlds/reference/2.0.0/core_comparable#equalsapprox) methods.

## Signature

```
export interface Comparable<T>
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**equals(val)**</td>
      <td>Indicates whether the two values are equal. True if the values are equal; false otherwise.

Signature

```
equals(val: T): boolean;
```

Parameters

val: T

The value to compare to the current value.

Returns

boolean</td>
    </tr>
    <tr>
      <td>**equalsApprox(val, epsilon)**</td>
      <td>Indicates two values are within epsilon of each other. True if the values are within epsilon, false otherwise.

Signature

```
equalsApprox(val: T, epsilon?: number): boolean;
```

Parameters

val: T

The value to compare to the current value.

epsilon: number *(Optional)* The difference between the two values when they are equal.

Returns

boolean</td>
    </tr>
  </tbody>
</table>