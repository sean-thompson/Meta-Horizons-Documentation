# ConditionalProps type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_conditionalprops)

Represents the props of a UINode.if() node (for conditional rendering).

## Signature

```
export declare type ConditionalProps = {
    condition: Bindable<boolean>;
    true?: UIChildren;
    false?: UIChildren;
};
```

## References [Bindable](/horizon-worlds/reference/2.0.0/ui_bindable) , 

[UIChildren](/horizon-worlds/reference/2.0.0/ui_uichildren)