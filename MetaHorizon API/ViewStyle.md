# ViewStyle type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_viewstyle)

Represents the styles of a [View()](/horizon-worlds/reference/2.0.0/ui_view) component on a UI panel. For descriptions of the available styles, see [Custom UI Styles](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/api-reference-for-custom-ui#viewstyle) .

## Signature

```
export declare type ViewStyle = LayoutStyle & BorderStyle & ShadowStyle & TransformStyle & {
    backgroundColor?: Bindable<ColorValue>;
    backgroundClip?: 'border-box' | 'padding-box';
    opacity?: Bindable<number>;
    gradientColorA?: Bindable<ColorValue>;
    gradientColorB?: Bindable<ColorValue>;
    gradientXa?: number | string;
    gradientYa?: number | string;
    gradientXb?: number | string;
    gradientYb?: number | string;
    gradientAngle?: string;
};
```

## References [LayoutStyle](/horizon-worlds/reference/2.0.0/ui_layoutstyle) , 

[BorderStyle](/horizon-worlds/reference/2.0.0/ui_borderstyle)

, [ShadowStyle](/horizon-worlds/reference/2.0.0/ui_shadowstyle) , 

[TransformStyle](/horizon-worlds/reference/2.0.0/ui_transformstyle)

, [Bindable](/horizon-worlds/reference/2.0.0/ui_bindable) , 

[ColorValue](/horizon-worlds/reference/2.0.0/ui_colorvalue)

## Remarks

The [UIComponent](/horizon-worlds/reference/2.0.0/ui_uicomponent) class is the base class for controlling custom UI panels in a world. See [Create a custom UI panel](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/creating-a-custom-ui-panel) for guides about using the API.