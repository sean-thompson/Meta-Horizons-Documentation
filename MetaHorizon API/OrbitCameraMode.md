# OrbitCameraMode Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/camera_orbitcameramode)

Extends *[ICameraMode](/horizon-worlds/reference/2.0.0/camera_icameramode)* Manipulates runtime properties of cameras in orbit mode, where camera view follows the player avatar without being fixed behind the player.

## Signature

```
export declare class OrbitCameraMode implements ICameraMode
```

## Remarks

The [Camera.setCameraModeOrbit()](/horizon-worlds/reference/2.0.0/camera_camera#setcameramodeorbit) method enables orbit mode. For more information on setting camera modes at runtime, see the [Camera](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/camera) guide.

## Properties

<table>
  <tbody>
    <tr>
      <td>**distance**</td>
      <td>Camera rotation radius around the target.

Signature

```
distance: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**rotationSpeed**</td>
      <td>Controls how quickly the camera rotates to the desired rotation. If not set, the camera is always snapped to it instantly.

Signature

```
rotationSpeed: HorizonProperty<number | null>;
```</td>
    </tr>
    <tr>
      <td>**translationSpeed**</td>
      <td>Controls how quickly the camera moves to the desired position. If not set, the camera is always snapped to it instantly.

Signature

```
translationSpeed: HorizonProperty<number | null>;
```</td>
    </tr>
    <tr>
      <td>**verticalOffset**</td>
      <td>Vertical offset up from the target position. Camera rotates around the offsetted point

Signature

```
verticalOffset: HorizonProperty<number>;
```</td>
    </tr>
  </tbody>
</table>