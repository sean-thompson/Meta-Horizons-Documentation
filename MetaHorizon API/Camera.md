# Camera Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/camera_camera)

Manages the view, position, and features of the in-game camera.

## Signature

```
export declare class Camera
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**cameraRoll**</td>
      <td>The camera roll angle.

Signature

```
cameraRoll: HorizonProperty<number>;
```

Remarks

You can change this value over time using .</td>
    </tr>
    <tr>
      <td>**collisionEnabled**</td>
      <td>Indicates whether camera collision is enabled.

Signature

```
collisionEnabled: HorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**currentMode**</td>
      <td>The type of camera that is active.

Signature

```
currentMode: ReadableHorizonProperty<CameraMode>;
```

Remarks

For native cameras, this property indicates whether the camera is in first or third person mode.</td>
    </tr>
    <tr>
      <td>**forward**</td>
      <td>Gets the forward direction of the camera.

Signature

```
forward: ReadableHorizonProperty<Vec3>;
```

Examples

```
if (LocalCamera !== null) {
  LocalCamera.forward.get()
}
```</td>
    </tr>
    <tr>
      <td>**isForceLookAtcamera**</td>
      <td>Is current active camera force looking at something.

Signature

```
isForceLookAtcamera: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**lookAtPosition**</td>
      <td>Gets the world space position that first intersects the center of the camera view, ignoring the avatar of the local player.

Signature

```
lookAtPosition: ReadableHorizonProperty<Vec3>;
```

Examples

```
if (LocalCamera !== null) {
  var lookAtPosition = LocalCamera.lookAtPosition.get();
}
```</td>
    </tr>
    <tr>
      <td>**perspectiveSwitchingEnabled**</td>
      <td>Indicates whether the player is allowed to toggle between first and third person modes.

Signature

```
perspectiveSwitchingEnabled: HorizonProperty<boolean>;
```

Examples

```
if (LocalCamera !== null) {
  LocalCamera.position.get()
}
```

Remarks

This property does not affect a script's ability to forcibly enable 1st or 3rd person mode with or . This property has as no effect in VR, where first person is always enabled.</td>
    </tr>
    <tr>
      <td>**position**</td>
      <td>Gets the position of the camera.

Signature

```
position: ReadableHorizonProperty<Vec3>;
```

Examples

```
if (LocalCamera !== null) {
  LocalCamera.position.get()
}
```</td>
    </tr>
    <tr>
      <td>**rotation**</td>
      <td>Gets the rotation of the camera.

Signature

```
rotation: ReadableHorizonProperty<Quaternion>;
```

Examples

```
if (LocalCamera !== null) {
  LocalCamera.rotation.get()
}
```</td>
    </tr>
    <tr>
      <td>**up**</td>
      <td>Gets the up direction of the camera.

Signature

```
up: ReadableHorizonProperty<Vec3>;
```

Examples

```
if (LocalCamera !== null) {
  LocalCamera.up.get()
}
```</td>
    </tr>
  </tbody>
</table>

## Methods

| convertWorldToScreenPoint(worldPos) | Converts a world position to a screen position on mobile and desktop. X: 0.0, Y: 0.0 represents the top left of the screen X: 0.5, Y: 0.5 represents the center of the screen X: 1.0, Y: 1.0 represents the bottom right of the screen Z represents the distance to the object, negative will be behind the cameraSignatureconvertWorldToScreenPoint(worldPos: Vec3): Vec3;ParametersworldPos: Vec3the world position to convertReturnsVec3A Vec3 representing the screen position |
| forceLookAt(target, options) | Forces the camera to look at a target or position. Supported camera modes: - AttachCamera - OrbitCamera - FollowCameraSignatureforceLookAt(target: Player \| Entity \| Vec3, options?: ForceLookAtOptions): void;Parameterstarget: Player \| Entity \| Vec3the target to look atoptions: ForceLookAtOptions(Optional) options for the transition to and from the forced look atReturnsvoid |
| getCameraModeObjectAs(classType) | Get the current camera mode object as a specific type.SignaturegetCameraModeObjectAs<TRuntimeCameraMode extends ICameraMode>(classType: new () => TRuntimeCameraMode): TRuntimeCameraMode \| null;ParametersclassType: new () => TRuntimeCameraModeThe type of camera mode object to get, must extend ICameraMode.ReturnsTRuntimeCameraMode \| nullThe camera mode object as the specified type, or null if the camera mode object is not of the specified type.ExamplesGet the current camera mode object as OrbitCameraMode:LocalCamera.getCameraModeObjectAs(OrbitCameraMode); |
| overrideCameraFarClipPlane(farClipPlane, options) | Set the far clip plane of the camera.SignatureoverrideCameraFarClipPlane(farClipPlane: number, options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;ParametersfarClipPlane: numberThe new far clip plane value to transition towards.options: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous far clip plane should transition to the new one. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesAdjust the camera far clip plane to 50 over a period of 1 second.localCamera.overrideCameraFarClipPlane(50.0, {duration: 1.0);RemarksPrevents the native camera from adjusting the far clip plane automatically, until Camera.resetCameraFarClipPlane() is called. |
| overrideCameraFOV(fov, options) | Set the field of view of the camera.SignatureoverrideCameraFOV(fov: number, options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersfov: numberThe new field of view value to transition towards.options: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous field of view should transition to the new one. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesAdjust the camera field of view to 50 over a period of 1 second.localCamera.overrideCameraFOV(50.0, {duration: 1.0);RemarksPrevents the native camera from adjusting the field of view automatically, until Camera.resetCameraFOV() is called. For example, the third person camera zooms in a little while you sprint. |
| resetCameraFarClipPlane(options) | Clears any far clip plane override, resetting it to the default native camera value.SignatureresetCameraFarClipPlane(options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the far clip plane should transition to the default far clip plane. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesReset the far clip plane over a period of 1 second.localCamera.resetCameraFarClipPlane({duration: 1.0); |
| resetCameraFOV(options) | Clears any field of view override, resetting it to the default native camera value.SignatureresetCameraFOV(options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous field of view should transition to the new field of view. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesReset the field of view over a period of 1 second.localCamera.resetCameraFOV({duration: 1.0);RemarksPrevents the native camera from adjusting the field of view automatically until Camera.resetCameraFOV() is called. For example, the third person camera zooms in a little while the player sprints. |
| setCameraModeAttach(target, options) | Enables attach mode for a camera, which automatically follows a target entity's position and rotation.SignaturesetCameraModeAttach(target: CameraTarget, options?: AttachCameraOptions & CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parameterstarget: CameraTargetThe entity for the tracking camera to follow.options: AttachCameraOptions & CameraTransitionOptions(Optional) If not set, the camera instantly matches the target's position and rotation.ReturnsPromise<CameraTransitionEndReason>ExamplesPlace the camera at a fixed position relative to the player, over a period of 1 second.localCamera.setCameraModeAttach(player, {positionOffset = position, duration: 1.0});RemarksIf the target entity is destroyed, camera tracking stops with the camera remaining where it was before losing the target. This method has no effect in VR, where only first person cameras are permitted. |
| setCameraModeFirstPerson(options) | Enables the standard first-person game camera, which uses a camera view from the eyes of the player avatar.SignaturesetCameraModeFirstPerson(options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous camera should transition to this new camera. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesEnable the first person camera after a delay of 1 second.localCamera.setCameraModeFirstPerson({delay: 1.0});RemarksDisables any previously set camera. Ignores the current value of Camera.perspectiveSwitchingEnabled. Has no effect in VR, where first person is always enabled. |
| setCameraModeFixed(options) | Sets the current camera to a fixed world position and rotation.SignaturesetCameraModeFixed(options?: FixedCameraOptions & CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: FixedCameraOptions & CameraTransitionOptions(Optional) If not set, the camera remains fixed in place from it's current position and orientation.ReturnsPromise<CameraTransitionEndReason>ExamplesExample 1Move the camera to a new position over a period of 1 second, maintaining its current orientation.localCamera.setFixedCameraPosition({position: pos}, {duration: 1.0});Example 2Keep the camera where it currently is, but point it straight downwards instantly.localCamera.setFixedCameraPosition({lookAt: getCameraPos() + new Vec3(0,-1,0)}); |
| setCameraModeFollow(options) | Enables the follow camera, which follows and auto-turns to be behind the local player avatar.SignaturesetCameraModeFollow(options?: FollowCameraOptions & CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: FollowCameraOptions & CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous camera should transition to this new camera. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesEnable the follow camera after a delay of 1 second.localCamera.setCameraModeFollow({delay: 1.0});RemarksDisables any previously set camera. Ignores the current value of . and has no effect in VR where only first person is allowed. |
| setCameraModeOrbit(options) | Enables the orbit camera, which follows the local player avatar.SignaturesetCameraModeOrbit(options?: OrbitCameraOptions & CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: OrbitCameraOptions & CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous camera should transition to this new camera. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesEnable the orbit camera after a delay of 1 second.localCamera.setCameraModeOrbit({delay: 1.0});RemarksDisables any previously set camera. Ignores the current value of . and has no effect in VR where only first person is allowed. |
| setCameraModePan(options) | Enables the pan camera, which follows the local player avatar at a fixed vector offset.SignaturesetCameraModePan(options?: PanCameraOptions & CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: PanCameraOptions & CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous camera should transition to this new camera. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesEnable the pan camera after a delay of 1 second.localCamera.setCameraModePan({delay: 1.0});RemarksDisables any previously set camera. Ignores the current value of . and has no effect in VR where only first person is allowed. |
| setCameraModeThirdPerson(options) | Enables the standard third-person game camera, which follows the local player avatar.SignaturesetCameraModeThirdPerson(options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;Parametersoptions: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous camera should transition to this new camera. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesEnable the third person over a period of 1 second.localCamera.setCameraModeThirdPerson({duration: 1.0});RemarksDisables any previously set camera, ignores the current value of Camera.perspectiveSwitchingEnabled, and has no effect in VR where only first person is allowed. |
| setCameraRollWithOptions(rollAngle, options) | Adjusts the current camera roll over time.SignaturesetCameraRollWithOptions(rollAngle: number, options?: CameraTransitionOptions): Promise<CameraTransitionEndReason>;ParametersrollAngle: numberThe roll rotation, in degrees, to set on the the current camera.options: CameraTransitionOptions(Optional) Optional CameraTransitionOptions that define how the previous roll should transition to the new roll. If not set, the transition is instant.ReturnsPromise<CameraTransitionEndReason>ExamplesRoll the camera by 10 degrees left over 1 second.localCamera.setCameraRoll(-10, {duration: 1.0}); |
| stopForceLookAt(options) | Stop a force look at if any is active. If options is not provided, an instant transition will be used.SignaturestopForceLookAt(options?: StopLookAtOptions): void;Parametersoptions: StopLookAtOptions(Optional)Returnsvoid |