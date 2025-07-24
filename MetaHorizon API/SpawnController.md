# SpawnController Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_spawncontroller)

Extends *[SpawnControllerBase](/horizon-worlds/reference/2.0.0/core_spawncontrollerbase)* Represents a controller used to spawn assets.

  

For information about usage, see [Introduction to Asset Spawning](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/asset-spawning/introduction-to-asset-spawning) .

## Signature

```
export declare class SpawnController extends SpawnControllerBase
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(asset, position, rotation, scale)**</td>
      <td>Creates a controller for spawning an asset.

* * *

Signature

```
constructor(asset: Asset, position: Vec3, rotation: Quaternion, scale: Vec3);
```

Parameters

asset: [Asset](/horizon-worlds/reference/2.0.0/core_asset) The asset to spawn.

position: [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) The position of the asset in the world.

rotation: [Quaternion](/horizon-worlds/reference/2.0.0/core_quaternion) The rotation of the asset in the world.

scale: [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) The scale of the asset in the world.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**asset**

\[readonly\]</td>
      <td>The asset that is currently being spawned.

Signature

```
readonly asset: Asset;
```</td>
    </tr>
  </tbody>
</table>