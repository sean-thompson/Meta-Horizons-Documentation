# TouchState type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/mobile_gestures_touchstate)

State of a touch

## Signature

```
export declare type TouchState = {
    phase: TouchPhase;
    start: TouchInfo;
    previous: TouchInfo;
    current: TouchInfo;
    screenDelta: Vec3;
    screenTraveled: number;
};
```

## References [TouchPhase](/horizon-worlds/reference/2.0.0/mobile_gestures_touchphase) , 

[TouchInfo](/horizon-worlds/reference/2.0.0/mobile_gestures_touchinfo)