# FollowCameraMode Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/camera_followcameramode)

Extends *[ICameraMode](/horizon-worlds/reference/2.0.0/camera_icameramode)* Manipulates runtime properties of cameras in Follow mode.

## Signature

```
export declare class FollowCameraMode implements ICameraMode
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**activationDelay**</td>
      <td>Camera auto-turning activation delay after camera has been manually turned.

Signature

```
activationDelay: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**cameraTurnSpeed**</td>
      <td>Speed at which the camera turns to return behind the player avatar.

Signature

```
cameraTurnSpeed: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**continuousRotation**</td>
      <td>Enables continuous rotation of the camera to return behind the player avatar once rotation had started and isn't interrupted.

Signature

```
continuousRotation: HorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**distance**</td>
      <td>Camera rotation radius around the target.

Signature

```
distance: HorizonProperty<number>;
```</td>
    </tr>
    <tr>
      <td>**horizonLevelling**</td>
      <td>Enables levelling the camera to the horizon.

Signature

```
horizonLevelling: HorizonProperty<boolean>;
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