# AssetBundleGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/unity_asset_bundles_assetbundlegizmo)

Extends *Entity* Represents a Unity AssetBundle, which is an archive of design assets that Unity can load at runtime.

## Signature

```
export declare class AssetBundleGizmo extends Entity
```

## Remarks

For more information about AssetBundles, see the [Horizon developer guides](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/assets/unity-assetbundles/horizon-unity-assetbundles-overview) and the [Unity developer guides](https://docs.unity3d.com/Manual/AssetBundlesIntro.html) (external).

## Methods

<table>
  <tbody>
    <tr>
      <td>**getPrefabNames()**</td>
      <td>Get the names of all prefabs in the AssetBundle instance.

Signature

```
getPrefabNames(): string[];
```

Returns

string\[\]

The names of the prefabs in the AssetBundle instance.</td>
    </tr>
    <tr>
      <td>**getReference(name, throwIfNotExist)**</td>
      <td>Gets an AssetBundleInstanceReference for an exposed GameObject in the loaded prefab. These need to be specified at export time in the HorizonUnityAssetReferences MonoBehaviour.

Signature

```
getReference(name: string, throwIfNotExist: boolean): AssetBundleInstanceReference;
```

Parameters

name: string

The name of the GameObject.

throwIfNotExist: boolean

Indicates whether to throw an exception if the GameObject does not exist.

Returns [AssetBundleInstanceReference](/horizon-worlds/reference/2.0.0/unity_asset_bundles_assetbundleinstancereference) A reference to the GameObject.

Exceptions

  

Thrown if throwIfNotExist is true and the GameObject does not exist.

  

  </td>
    </tr>
    <tr>
      <td>**getRoot()**</td>
      <td>Gets an AssetBundleInstanceReference for the main GameObject.

Signature

```
getRoot(): AssetBundleInstanceReference;
```

Returns [AssetBundleInstanceReference](/horizon-worlds/reference/2.0.0/unity_asset_bundles_assetbundleinstancereference) A reference to the main GameObject.</td>
    </tr>
    <tr>
      <td>**isLoaded()**</td>
      <td>Determines whether a prefab is instantiated and the root reference is ready.

Signature

```
isLoaded(): boolean;
```

Returns

boolean

true if a prefab is instantiated and the root reference is ready, false otherwise.</td>
    </tr>
    <tr>
      <td>**loadPrefab(name)**</td>
      <td>Loads a prefab from a Unity AssetBundle.

Signature

```
loadPrefab(name: string): void;
```

Parameters

name: string

The name of the prefab to load. The method retrieves the prefab names in the AssetBundle.

Returns

void

Examples

Dynamically load a prefab:

```
this.entity.as(AssetBundleGizmo).loadPrefab("Prefab01");
```

Remarks

A prefab is a type of preconfigured Unity GameObject that includes its dependent objects and can be stored as a reusable asset.

  

To unload a prefab, see .</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Returns the class type and ID of the AssetBundleGizmo.

Signature

```
toString(): string;
```

Returns

string

The class type and ID of the AssetBundleGizmo.</td>
    </tr>
    <tr>
      <td>**unloadPrefab()**</td>
      <td>Unloads the in the AssetBundleGizmo.

Signature

```
unloadPrefab(): void;
```

Returns

void

Remarks

A prefab is a type of preconfigured Unity GameObject that includes its dependent objects and can be stored as a reusable asset.</td>
    </tr>
  </tbody>
</table>