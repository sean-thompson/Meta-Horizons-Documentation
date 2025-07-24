# MeshEntity Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_meshentity)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* An [Entity](/horizon-worlds/reference/2.0.0/core_entity) that uses a custom model.

## Signature

```
export declare class MeshEntity extends Entity
```

## Remarks

A custom model is built outside of Meta Horizon Worlds with a 3D modeling tool exported as an .fbx file, and then consumed in the asset library by the asset pipeline.

## Properties

<table>
  <tbody>
    <tr>
      <td>**style**</td>
      <td>The style of the `MeshEntity`.

Signature

```
style: EntityStyle;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**setMaterial(materialAsset, options)**</td>
      <td>Sets the material on a MeshEntity (custom model entity) to a material asset.

Signature

```
setMaterial(materialAsset: MaterialAsset, options?: SetMaterialOptions): Promise<void>;
```

Parameters

materialAsset: [MaterialAsset](/horizon-worlds/reference/2.0.0/core_materialasset) A material asset from the asset library.

options: [SetMaterialOptions](/horizon-worlds/reference/2.0.0/core_setmaterialoptions) *(Optional)*

Returns

Promise<void>

A promise that resolves when the material has been successfully updated.

Examples

```
class Button extends Component<typeof Button> {
  static propsDefinition = {
    material: {type: PropTypes.Asset},
    materialSlot: {type: PropTypes.Number | Proptypes.String},
    targetEntity: {type: PropTypes.Entity},
  };

  start() {
    this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnPlayerEnterTrigger, () => this.onButtonPress());
  }

  onButtonPress() {
    const options = {materialSlot: this.props.materialSlot};
    this.props.targetEntity.as(MeshEntity)!.setMaterial(this.props.material, options);
  }
}
```</td>
    </tr>
    <tr>
      <td>**setMesh(mesh, options)**</td>
      <td>Changes the mesh and optionally material of a MeshEntity (custom model entity).

Signature

```
setMesh(mesh: Asset, options: SetMeshOptions): Promise<void>;
```

Parameters

mesh: [Asset](/horizon-worlds/reference/2.0.0/core_asset) The new custom model asset to use in the world. You must use a custom model asset that was consumed as a custom model in the asset pipeline. You cannot use a custom model asset that is saved as an asset within Meta Horizon Worlds.

options: [SetMeshOptions](/horizon-worlds/reference/2.0.0/core_setmeshoptions) true if players can decide to use the new material that comes with the new custom model; false to use the current material.

Returns

Promise<void>

A promise that resolves when the mesh (and material) has been successfully swapped.

Examples

```
import { Component, PropTypes, Entity, AudioGizmo, CodeBlockEvents, Asset } from '@early_access_api/v1';
import { MeshEntity, TextureAsset } from '@early_access_api/v1';

class TargetEntity extends Component<{}> {
   static propsDefinition = {};

   start() {
       this.connectLocalEvent(this.entity, buttonPressedEvent, (data: {mesh: Asset}) => {
       this.entity.as(MeshEntity).setMesh(data.mesh, {updateMaterial: false});
    });
  }
}

type ButtonProps = {
  mesh: Asset,
  targetEntity: Entity,
};

class Button extends Component<ButtonProps> {
  static propsDefinition = {
    mesh: {type: PropTypes.Asset},
    targetEntity: {type: PropTypes.Entity},
  };

  start() {
    this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnPlayerEnterTrigger, () => this.onClick());
  }

  onClick() {
    this.sendLocalEvent(this.props.targetEntity, buttonPressedEvent, {mesh: this.props.mesh.as(Asset)});
  }
}

Component.register(Button);
```

Remarks

You should only apply this API to a custom model entity. Otherwise, this call does not take effect.</td>
    </tr>
    <tr>
      <td>**setTexture(texture, options)**</td>
      <td>Changes the texture of a `MeshEntity` (custom model entity) for the specified players.

Signature

```
setTexture(texture: TextureAsset, options?: SetTextureOptions): Promise<void>;
```

Parameters

texture: [TextureAsset](/horizon-worlds/reference/2.0.0/core_textureasset) The asset containing the texture to apply. The asset must be a texture asset that has been consumed as a texture in the asset pipeline.

options: [SetTextureOptions](/horizon-worlds/reference/2.0.0/core_settextureoptions) *(Optional)*

 Indicates the players to apply the texture for.

Returns

Promise<void>

A promise that resolves when the texture is successfully applied.

Examples

```
import { Component, PropTypes, Entity, AudioGizmo, CodeBlockEvents, Asset } from '@early_access_api/v1';
import { MeshEntity, TextureAsset } from '@early_access_api/2p';

class Button extends Component<typeof Button> {
  static propsDefinition = {
    texture: {type: PropTypes.Asset},
    panel: {type: PropTypes.Entity},
    sound: {type: PropTypes.Entity},
  };

  start() {
    this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnPlayerEnterTrigger, () => this.onClick());
  }

  onClick() {
    this.props.sound.as(AudioGizmo).play();
    this.props.panel.as(MeshEntity).setTexture(this.props.texture.as(TextureAsset));
  }
}

Component.register(Button);
```

Remarks

This API should only be applied to a custom model entity that uses a texture based material. Additionally, non-interactive (Motion property set to None) entities may not update textures if the material shader is GI lit. Otherwise, this call does not take effect and throws an error at runtime.</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Gets a human readable representation of the `MeshEntity`.

Signature

```
toString(): string;
```

Returns

string

A string representation of the `MeshEntity`.</td>
    </tr>
  </tbody>
</table>