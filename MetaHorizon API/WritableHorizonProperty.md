# WritableHorizonProperty Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_writablehorizonproperty)

Represents a writable property.

## Signature

```
export interface WritableHorizonProperty<T, U = never>
```

## Remarks

You cannot set the property value directly; you must use the `set` method. Using `set` typically results in a bridge call and might result in lower performance. Therefore, we recommend caching these values when possible. For more information, see [CPU and TypeScript optimization and best practices](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/cpu-and-typescript-optimization-best-practices) .

## Methods

<table>
  <tbody>
    <tr>
      <td>**set(value, values)**</td>
      <td>Sets the value(s) of the property

Signature

```
set(value: T, ...values: [U?]): void;
```

Parameters

value: T

the new property value

values: \[U?\]

the new property values

Returns

void</td>
    </tr>
  </tbody>
</table>