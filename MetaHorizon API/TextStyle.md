# TextStyle type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_textstyle)

Represents the styles of a [Text](/horizon-worlds/reference/2.0.0/ui_text_2) component in a UI panel.

## Signature

```
export declare type TextStyle = ViewStyle & {
    color?: Bindable<ColorValue>;
    fontFamily?: FontFamily;
    fontSize?: Bindable<number>;
    fontWeight?: Bindable<'normal' | 'bold' | '100' | '200' | '300' | '400' | '500' | '600' | '700' | '800' | '900'>;
    letterSpacing?: number;
    lineHeight?: number;
    textAlign?: 'auto' | 'left' | 'right' | 'center';
    textAlignVertical?: 'auto' | 'top' | 'bottom' | 'center';
    textDecorationLine?: Bindable<'none' | 'underline' | 'line-through' | 'underline line-through'>;
    textShadowColor?: Bindable<ColorValue>;
    textShadowOffset?: [number, number];
    textShadowRadius?: number;
    whiteSpace?: 'normal' | 'pre-line' | 'pre-wrap';
};
```

## References [ViewStyle](/horizon-worlds/reference/2.0.0/ui_viewstyle) , 

[Bindable](/horizon-worlds/reference/2.0.0/ui_bindable)

, [ColorValue](/horizon-worlds/reference/2.0.0/ui_colorvalue) , 

[FontFamily](/horizon-worlds/reference/2.0.0/ui_fontfamily)

## Remarks

For descriptions of the available styles, see [Custom UI Styles](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/api-reference-for-custom-ui#textstyle) .