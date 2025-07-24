# FixedCameraOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/camera_fixedcameraoptions)

The available options to apply when activating a fixed camera.

## Signature

```
export declare type FixedCameraOptions = {
    position?: Vec3;
    rotation?: Quaternion;
};
```

## Remarks

Type Parameters:

  

position - (Vec3) The position in world space to set the camera to. If not set, the camera will maintain it's current position.

  

rotation - The rotation for the camera to face. If not set, the camera maintains its current rotation.