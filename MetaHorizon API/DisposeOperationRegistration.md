# DisposeOperationRegistration Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_disposeoperationregistration)

The object returned from a call to [DisposableObject.registerDisposeOperation()](/horizon-worlds/reference/2.0.0/core_disposableobject#registerdisposeoperation) . This object can be used to run the operation manually before dispose time, or to cancel the operation entirely.

## Signature

```
export interface DisposeOperationRegistration
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**cancel**</td>
      <td>Cancels the dispose operation so that it is never runs.

Signature

```
cancel: () => void;
```</td>
    </tr>
    <tr>
      <td>**run**</td>
      <td>Manually run the dispose operation before the [DisposableObject](/horizon-worlds/reference/2.0.0/core_disposableobject) is disposed. Dispose operations are only run once--a call to run guarantees the operation will not run at dispose time.

Signature

```
run: () => void;
```</td>
    </tr>
  </tbody>
</table>