# UIComponent Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_uicomponent)

Extends *Component<TComponent, TState>* The base class for a UI panel, and the scripting component to attach to a [UI Gizmo](/horizon-worlds/reference/2.0.0/ui_uigizmo) . It inherits the methods and properties from its parent Component class, with some UI-specialized additions.

## Signature

```
export declare abstract class UIComponent<TComponent = ComponentWithConstructor<Record<string, unknown>>, TState extends SerializableState = SerializableState> extends Component<TComponent, TState>
```

## Examples

```
class Welcome extends UIComponent {
 initializeUI() {
   return Text({text: 'Welcome to my World'});
 }
}
```

## Remarks

For information about usage, see the [Custom UI Examples](https://developers.meta.com/horizon-worlds/learn/documentation/tutorials/tutorial-worlds/custom-ui-examples-tutorial/station-0-setup) tutorial and [Custom UI guides](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/video-create-performant-custom-uis-in-horizon-worlds) .

## Properties

<table>
  <tbody>
    <tr>
      <td>**panelHeight**

\[readonly\]</td>
      <td>The height of the panel, in pixels. You can't change the value after the panel is initialized.

Signature

```
protected readonly panelHeight: number;
```

Remarks

Default value: 500.</td>
    </tr>
    <tr>
      <td>**panelWidth**

\[readonly\]</td>
      <td>The width of the UI panel, in pixels. You can't change the value after the panel is initialized.

Signature

```
protected readonly panelWidth: number;
```

Remarks

Default value: 500.</td>
    </tr>
  </tbody>
</table>

## Methods

| initializeUI() abstract | Defines the UI and sets up necessary event subscriptions. This method is called before the UIComponent.start() method when the component is started.Signatureabstract initializeUI(): UINode;ReturnsUINodeRemarksThis method must return a valid UINode. |
| start() | A default start implementation for classes that inherit from UIComponent.Signaturestart(): void;Returnsvoid |