# PlayerControlsConnectOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playercontrolsconnectoptions)

The options to pass to [PlayerControls.connectLocalInput()](/horizon-worlds/reference/2.0.0/core_playercontrols#connectlocalinput) .

## Signature

```
export declare type PlayerControlsConnectOptions = {
    preferredButtonPlacement?: ButtonPlacement;
    customAssetIconId?: string;
};
```

## References [ButtonPlacement](/horizon-worlds/reference/2.0.0/core_buttonplacement) ## Remarks `preferredButtonPlacement` \- The button placement to use, if supported. Certain platforms might not support all placements. Attempting to place multiple buttons at the same location prioritizes the latest button enabled.