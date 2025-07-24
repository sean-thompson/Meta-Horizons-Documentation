# Copyable Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_copyable)

The Copyable interface provides 'copy' and 'clone' methods for copying data from an existing reference.

## Signature

```
export interface Copyable<T>
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**clone()**</td>
      <td>Creates a new reference with the source reference data copied to the new reference.

Signature

```
clone(): T;
```

Returns

T</td>
    </tr>
    <tr>
      <td>**copy(val)**</td>
      <td>Copies data from another reference.

Signature

```
copy(val: T): void;
```

Parameters

val: T

The value to copy data from.

Returns

void</td>
    </tr>
  </tbody>
</table>