# ImageStyle type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_imagestyle)

Represents the styles of an [Image](/horizon-worlds/reference/2.0.0/ui_image_2) component in a UI panel.

## Signature

```
export declare type ImageStyle = ViewStyle & {
    resizeMode?: 'cover' | 'contain' | 'stretch' | 'center' | 'repeat';
    tintColor?: Bindable<ColorValue>;
    tintOperation?: 'replace' | 'multiply';
};
```

## References [ViewStyle](/horizon-worlds/reference/2.0.0/ui_viewstyle) , 

[Bindable](/horizon-worlds/reference/2.0.0/ui_bindable)

, [ColorValue](/horizon-worlds/reference/2.0.0/ui_colorvalue) ## Remarks

For descriptions of the available styles, see [Custom UI Styles](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/api-reference-for-custom-ui#imagestyle) .