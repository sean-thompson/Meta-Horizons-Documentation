# View() Function

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_view)

Creates a view component for a UI panel.

## Signature

```
export declare function View(props: Readonly<ViewProps>): UINode<ViewProps>;
```

## Parameters

props: Readonly< [ViewProps](/horizon-worlds/reference/2.0.0/ui_viewprops) >

The props that define the child components and style of the view.

## Returns [UINode](/horizon-worlds/reference/2.0.0/ui_uinode) <

[ViewProps](/horizon-worlds/reference/2.0.0/ui_viewprops)

>

A UINode representing the View component.

## Remarks

A view is a container for UI components and supports a parent-child relationship with other components. Views support multiple styles including flex layouts.

  

The [UIComponent](/horizon-worlds/reference/2.0.0/ui_uicomponent) class is the base class for controlling custom UI panels in a world. See [Create a custom UI panel](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/creating-a-custom-ui-panel) for guides about using the API.

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)