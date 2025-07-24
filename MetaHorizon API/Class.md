# Class Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_class)

An interface representing a class.

## Signature

```
export interface Class<TConstructorParameters extends any[] = any[], TClassInstance = unknown>
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**(new)(args)**</td>
      <td>Creates a new instance of the class.

Signature

```
new (...args: TConstructorParameters): TClassInstance;
```

Parameters

args: TConstructorParameters

The arguments for creating the instance.

Returns

TClassInstance

The new class instance.</td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)