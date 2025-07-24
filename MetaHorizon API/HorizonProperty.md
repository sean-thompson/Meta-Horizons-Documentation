# HorizonProperty Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_horizonproperty)

Extends *BaseHorizonProperty<T>* Represents a property in Meta Horizon Worlds.

## Signature

```
export declare class HorizonProperty<T> extends BaseHorizonProperty<T>
```

## Remarks

For properties of reference types that perform copy and clone operations ( [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) , 

[Quaternion](/horizon-worlds/reference/2.0.0/core_quaternion)

, [Color](/horizon-worlds/reference/2.0.0/core_color) ), use the [HorizonReferenceProperty](/horizon-worlds/reference/2.0.0/core_horizonreferenceproperty) class.

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(getter, setter)**</td>
      <td>Creates a HorizonProperty instance.

* * *

Signature

```
constructor(getter: () => T, setter: (value: T) => void);
```

Parameters

getter: () => T

The function that returns the property value.

setter: (value: T) => void

The function that sets the property value.</td>
    </tr>
  </tbody>
</table>