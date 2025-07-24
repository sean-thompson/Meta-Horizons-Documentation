# DynamicListProps type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_dynamiclistprops)

Represents the props of a [DynamicList()](/horizon-worlds/reference/2.0.0/ui_dynamiclist) component in a UI panel.

## Signature

```
export declare type DynamicListProps<T> = {
    data: Binding<T[]>;
    renderItem: (item: T, index?: number) => UINode;
    style?: ViewStyle;
};
```

## References [Binding](/horizon-worlds/reference/2.0.0/ui_binding) , 

[UINode](/horizon-worlds/reference/2.0.0/ui_uinode)

, 

[ViewStyle](/horizon-worlds/reference/2.0.0/ui_viewstyle)