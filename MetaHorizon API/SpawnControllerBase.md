# SpawnControllerBase Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_spawncontrollerbase)

The base class for a [spawn controller](/horizon-worlds/reference/2.0.0/core_spawncontroller) .

  

For information about usage, see [Introduction to Asset Spawning](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/asset-spawning/introduction-to-asset-spawning) .

## Signature

```
export declare class SpawnControllerBase
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**_spawnId**</td>
      <td>The ID of the asset that is currently being spawned. This is a protected version of the property.

Signature

```
protected _spawnId: number;
```</td>
    </tr>
    <tr>
      <td>**currentState**

\[readonly\]</td>
      <td>The current spawn state of the spawn controller asset.

Signature

```
readonly currentState: ReadableHorizonProperty<SpawnState>;
```</td>
    </tr>
    <tr>
      <td>**rootEntities**

\[readonly\]</td>
      <td>A list of entities contained in a spawned asset.

Signature

```
readonly rootEntities: ReadableHorizonProperty<Entity[]>;
```</td>
    </tr>
    <tr>
      <td>**spawnError**

\[readonly\]</td>
      <td>An error associated with the spawn operation.

Signature

```
readonly spawnError: ReadableHorizonProperty<SpawnError>;
```</td>
    </tr>
    <tr>
      <td>**spawnId**

\[readonly\]</td>
      <td>The ID of the asset that is currently being spawned.

Signature

```
get spawnId(): number;
```</td>
    </tr>
    <tr>
      <td>**targetState**

\[readonly\]</td>
      <td>The spawn state the spawn controller asset is attempting to reach.

Signature

```
readonly targetState: ReadableHorizonProperty<SpawnState>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| dispose() | Unloads the asset data of a spawn controller, and performs cleanup on the spawn controller object.Signaturedispose(): Promise<unknown>;ReturnsPromise<unknown>A promise that indicates whether the dispose operation succeeded.RemarksThis method is equivalent to , except afterwards the spawn controller is no longer available for use and all of its methods throw errors. Call dispose in order to clean up resources that are no longer needed. |
| load() | Preloads the asset data for a spawn controller.Signatureload(): Promise<void>;ReturnsPromise<void>A promise that indicates whether the operation succeeded. |
| pause() | Pauses the spawning process for a spawn controller.Signaturepause(): Promise<void>;ReturnsPromise<void>A promise that indicates whether the operation succeeded. |
| spawn() | Loads asset data if it's not previously loaded and then spawns the asset.Signaturespawn(): Promise<void>;ReturnsPromise<void>A promise that indicates whether the operation succeeded. |
| unload() | Unloads the spawn controller asset data. If the spawn controller isn't needed after the data is unloaded, call .Signatureunload(): Promise<void>;ReturnsPromise<void>A promise that indicates whether the operation succeeded. |