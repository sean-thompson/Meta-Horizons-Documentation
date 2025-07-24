# FocusedInteractionOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_focusedinteractionoptions)

The options for the [Player.enterFocusedInteractionMode()](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) method.

## Signature

```
export declare type FocusedInteractionOptions = {
    disableFocusExitButton?: boolean | null;
    interactionStringId?: string | null;
};
```

## Remarks

This type defines the `options` parameter of the [Player.enterFocusedInteractionMode()](/horizon-worlds/reference/2.0.0/core_player#enterfocusedinteractionmode) method. The [DefaultFocusedInteractionEnableOptions](/horizon-worlds/reference/2.0.0/core_defaultfocusedinteractionenableoptions) variable contains the default values. `disableFocusExitButton` \- True to disable the Exit button during Focused Interaction mode. The default value is `false`.

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)