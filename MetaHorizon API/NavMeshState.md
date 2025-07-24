# NavMeshState Enum

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/navmesh_navmeshstate)

The possible state values for the [NavMeshInstanceInfo](/horizon-worlds/reference/2.0.0/navmesh_navmeshinstanceinfo) type.

## Signature

```
export declare enum NavMeshState
```

## Enumeration Members

| Member | Value | Description |
| --- | --- | --- |
| Baking | "Baking" | The navigation mesh is being rebuilt. |
| Loading | "Loading" | Details are being loaded for this navigation mesh. |
| Ready | "Ready" | The instance is initialized and ready to use. |
| Uninitialized | "Uninitialized" | The instance hasn't been initialized yet. |