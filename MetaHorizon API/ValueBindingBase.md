# ValueBindingBase Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_valuebindingbase)

The base class for value-based bindings, including [Binding](/horizon-worlds/reference/2.0.0/ui_binding) and DerivedBinding. These bindings are represented as string keys in the data model, and their values are updated in the redux store. These bindings support both global values and player-specific values.

## Signature

```
export declare abstract class ValueBindingBase<T>
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**_isInitialized**</td>
      <td>Signature

```
protected _isInitialized: boolean;
```</td>
    </tr>
  </tbody>
</table>