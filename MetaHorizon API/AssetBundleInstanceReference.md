# AssetBundleInstanceReference Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/unity_asset_bundles_assetbundleinstancereference)

Represents a reference to a Unity AssetBundle.

## Signature

```
export declare class AssetBundleInstanceReference
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(entity, referenceName)**</td>
      <td>Creates an instance of AssetBundleInstanceReference.

* * *

Signature

```
constructor(entity: Entity, referenceName: string);
```

Parameters

entity: Entity

The parent entity.

referenceName: string

The name of the reference.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**style**</td>
      <td>Signature

```
style: IEntityStyle;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**getAnimationParameters()**</td>
      <td>Gets the parameters for an animation.

Signature

```
getAnimationParameters(): {
        [name: string]: string | string;
    };
```

Returns

{ \[name: string\]: string | string; }

The names and types of the animation parameters.</td>
    </tr>
    <tr>
      <td>**isLoaded()**</td>
      <td>Determines whether an AssetBundle is loaded.

Signature

```
isLoaded(): boolean;
```

Returns

boolean `true` if the AssetBundle is loaded, `false` otherwise.</td>
    </tr>
    <tr>
      <td>**resetAnimationParameterTrigger(name, localOnly)**</td>
      <td>Resets the value of the animation parameter with the given name.

Signature

```
resetAnimationParameterTrigger(name: string, localOnly?: boolean): void;
```

Parameters

name: string

The name of the animation parameter to reset.

localOnly: boolean

*(Optional)* `true` only resets the local animation; otherwise, resets the global animation.

Returns

void</td>
    </tr>
    <tr>
      <td>**setAnimationParameterBool(name, value, localOnly)**</td>
      <td>Sets the value of a boolean animation parameter.

Signature

```
setAnimationParameterBool(name: string, value: boolean, localOnly?: boolean): void;
```

Parameters

name: string

The name of the animation parameter to set.

value: boolean

The value for the animation parameter.

localOnly: boolean

*(Optional)* `true` only sets the value for the local animation; otherwise, sets the value for the global animation.

Returns

void</td>
    </tr>
    <tr>
      <td>**setAnimationParameterFloat(name, value, localOnly)**</td>
      <td>Sets the value of a float animation parameter.

Signature

```
setAnimationParameterFloat(name: string, value: number, localOnly?: boolean): void;
```

Parameters

name: string

The name of the animation parameter to set.

value: number

The value for the animation parameter.

localOnly: boolean

*(Optional)* `true` only sets the value for the local animation; otherwise, sets the value for the global animation.

Returns

void</td>
    </tr>
    <tr>
      <td>**setAnimationParameterInteger(name, value, localOnly)**</td>
      <td>Sets the value of an integer animation parameter.

Signature

```
setAnimationParameterInteger(name: string, value: number, localOnly?: boolean): void;
```

Parameters

name: string

The name of the animation parameter to set.

value: number

The value for the animation parameter.

localOnly: boolean

*(Optional)* `true` only sets the value for the local animation; otherwise, sets the value for the global animation.

Returns

void</td>
    </tr>
    <tr>
      <td>**setAnimationParameterTrigger(name, localOnly)**</td>
      <td>Activates an animation trigger.

Signature

```
setAnimationParameterTrigger(name: string, localOnly?: boolean): void;
```

Parameters

name: string

The name of the animation parameter to activate.

localOnly: boolean

*(Optional)* `true` only activates the local animation trigger; otherwise, activates the global animation trigger.

Returns

void</td>
    </tr>
    <tr>
      <td>**setMaterial(material, options)**</td>
      <td>Sets the material of a mesh.

Signature

```
setMaterial(material: string | MaterialAsset, options?: SetMaterialOptions): void;
```

Parameters

material: string | MaterialAsset

The material name or material asset to set.

options: [SetMaterialOptions](/horizon-worlds/reference/2.0.0/unity_asset_bundles_setmaterialoptions) *(Optional)*

 The slot index options for the material, which are used to specify the material to update when updating meshes with multiple materials.

Returns

void

Examples

```
class Button extends Component<typeof Button> {
  static propsDefinition = {
    material: {type: PropTypes.Asset},
    materialSlot: {type: PropTypes.Number},
    targetEntity: {type: PropTypes.Entity},
  };

  start() {
    this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnPlayerEnterTrigger, () => this.onButtonPress());
  }

  onButtonPress() {
    const options = { materialSlot: this.props.materialSlot };
    this.props.targetEntity
      .as(AssetBundleGizmo)!
      .getRoot()
      .setMaterial(this.props.material, options);
  }
}
```

Remarks

Material names reference materials registered in the SwappableMaterials list in Unity.</td>
    </tr>
    <tr>
      <td>**setMesh(meshName)**</td>
      <td>Swaps the mesh of an entity with another mesh registered in the SwappableMesh list in Unity.

Signature

```
setMesh(meshName: string): void;
```

Parameters

meshName: string

The name of the mesh to set.

Returns

void</td>
    </tr>
  </tbody>
</table>