# AttachCameraMode Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/camera_attachcameramode)

Extends *[ICameraMode](/horizon-worlds/reference/2.0.0/camera_icameramode)* Manipulates runtime properties of cameras in attach mode. When attach mode is enabled for a camera, it follows a target entity's position and rotation.

## Signature

```
export declare class AttachCameraMode implements ICameraMode
```

## Remarks

The [Camera.setCameraModeAttach()](/horizon-worlds/reference/2.0.0/camera_camera#setcameramodeattach) method enables attach mode for a camera.

## Properties

<table>
  <tbody>
    <tr>
      <td>**positionOffset**</td>
      <td>Local offset from the target position. Target's frame of reference.

Signature

```
positionOffset: HorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**rotationOffset**</td>
      <td>Local rotation from the target rotation. Target's frame of reference.

Signature

```
rotationOffset: HorizonProperty<Quaternion>;
```</td>
    </tr>
    <tr>
      <td>**rotationSpeed**</td>
      <td>Controls how quickly the camera rotates to keep the target in view. If not set, the camera always points in the same direction the target is facing.

Signature

```
rotationSpeed: HorizonProperty<number | null>;
```</td>
    </tr>
    <tr>
      <td>**translationSpeed**</td>
      <td>Controls how quickly the camera moves with the target it's attached to. If not set, the camera is always snapped to the position offset from the target.

Signature

```
translationSpeed: HorizonProperty<number | null>;
```</td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)