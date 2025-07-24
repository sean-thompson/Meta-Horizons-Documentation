# CameraTransitionOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/camera_cameratransitionoptions)

The options for transitioning between cameras.

## Signature

```
export declare type CameraTransitionOptions = {
    delay?: number;
    duration?: number;
    easing?: Easing;
};
```

## References [Easing](/horizon-worlds/reference/2.0.0/camera_easing) ## Remarks

Type Parameters:

  

delay - The time, in seconds, to wait until the transition begins. Defaults to 0.

  

duration - The time, in seconds, to transition from the previous camera to the new local camera. If not set, the transition is instant.

  

Easing - The style in which the transition from the previous to the new camera occurs over time. Defaults to Linear.