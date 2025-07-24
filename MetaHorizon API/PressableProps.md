# PressableProps type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_pressableprops)

Represents the props of a [pressable](/horizon-worlds/reference/2.0.0/ui_pressable) component on a UI panel.

## Signature

```
export declare type PressableProps = {
    children?: UIChildren;
    disabled?: Bindable<boolean>;
    onClick?: Callback;
    onEnter?: Callback;
    onExit?: Callback;
    onPress?: Callback;
    onRelease?: Callback;
    propagateClick?: boolean;
    style?: ViewStyle;
};
```

## References [UIChildren](/horizon-worlds/reference/2.0.0/ui_uichildren) , 

[Bindable](/horizon-worlds/reference/2.0.0/ui_bindable)

, [Callback](/horizon-worlds/reference/2.0.0/ui_callback) , 

[ViewStyle](/horizon-worlds/reference/2.0.0/ui_viewstyle)