# PlayerInputStateChangeCallback type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playerinputstatechangecallback)

A callback that signals state changes when player input is pressed.

## Signature

```
export declare type PlayerInputStateChangeCallback = (action: PlayerInputAction, pressed: boolean) => void;
```

## References [PlayerInputAction](/horizon-worlds/reference/2.0.0/core_playerinputaction) ## Remarks

Use [PlayerInput.registerCallback()](/horizon-worlds/reference/2.0.0/core_playerinput#registercallback) to register this callback.

  

action - The input action that triggered the callback.

  

pressed - true if the input was pressed; false if it was released.