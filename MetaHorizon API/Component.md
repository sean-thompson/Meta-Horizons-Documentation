# Component Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_component)

Extends *[DisposableObject](/horizon-worlds/reference/2.0.0/core_disposableobject)* The core class for creating new types of components and attaching functionality to [entities](/horizon-worlds/reference/2.0.0/core_entity) in a world.

## Signature

```
export declare abstract class Component<TComponent = ComponentWithConstructor<Record<string, unknown>>, TSerializableState extends SerializableState = SerializableState> implements DisposableObject
```

## Examples

In the following example, the NpcItem class extends the Component class to define a new type of component. The new component type is then registered so new instances of the NpcItem can be created in the world.

```
import * as hz from 'horizon/core';

class NpcItem extends hz.Component<typeof NpcItem> {
  static propsDefinition = {};

  start() {}
}
hz.Component.register(NpcItem);
```

## Remarks

The `Component` class is an abstract class that you can extend to create new types of components that add properties and functionality to entities in your world. It provides properties and methods that manage the lifecycle of components, their relationship with attached entities, internal component data, and access to events including code block events.

  

When you create a new component in Desktop Editor, the editor generates a script that includes the following elements: [Component.propsDefinition](/horizon-worlds/reference/2.0.0/core_component#propsdefinition) \- Defines internal properties for the class, which are also added to the Properties panel in Desktop Editor. [Component.start()](/horizon-worlds/reference/2.0.0/core_component#start) \- The method that executes when the class initially loads. This is where you can add event listeners that need to run when the script starts running. [Component.register()](/horizon-worlds/reference/2.0.0/core_component#register) \- The method that registers the new component class as a component definition that can be used to generate instances of the component in your world.

  

For more information about using components, see the [Intro to Scripting](https://developers.meta.com/horizon-worlds/learn/documentation/tutorials/tutorial-worlds/intro-to-desktop-editor-and-typescript/module-2-intro-to-scripting) tutorial, and the [TypeScript Components, Properties, and Variables](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/typescript-components-properties-and-variables) guide.

## Properties

<table>
  <tbody>
    <tr>
      <td>**async**</td>
      <td>A set of asynchronous helper functions that are scoped to the component for automatic cleanup on dispose.

Signature

```
async: {
        setTimeout: (callback: TimerHandler, timeout?: number, ...args: unknown[]) => number;
        clearTimeout: (id: number) => void;
        setInterval: (callback: TimerHandler, timeout?: number, ...args: unknown[]) => number;
        clearInterval: (id: number) => void;
    };
```

Remarks `setTimeout` \- Sets a timer that executes a function or specified piece of code once the timer expires. `clearTimeout` \- Cancels a timeout previously established by calling `setTimeout()`. `setInterval` \- Repeatedly calls a function or executes a code snippet, with a fixed time delay between each call. `clearInterval` \- Cancels a timed-repeating action that was previously established by a call to `setInterval`.</td>
    </tr>
    <tr>
      <td>**entity**

\[readonly\]</td>
      <td>The entity the component is attached to.

Signature

```
readonly entity: Entity;
```</td>
    </tr>
    <tr>
      <td>**entityId**

\[readonly\]</td>
      <td>The ID of the entity the component is attached to.

Signature

```
readonly entityId: number;
```</td>
    </tr>
    <tr>
      <td>**props**

\[readonly\]</td>
      <td>The properties that modify the component.

Signature

```
readonly props: GetPropsFromComponentOrPropsDefinition<TComponent>;
```</td>
    </tr>
    <tr>
      <td>**propsDefinition**

static

  </td>
      <td>The set of properties that define the available input and default values of the component.

Signature

```
static propsDefinition: {};
```</td>
    </tr>
    <tr>
      <td>**world**

\[readonly\]</td>
      <td>The [World](/horizon-worlds/reference/2.0.0/core_world) instance that contains the component.

Signature

```
readonly world: World;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| connectCodeBlockEvent(target, event, callback) | Called when receiving the specified CodeBlockEvent instance from the Player or Entity object.SignatureconnectCodeBlockEvent<TEventArgs extends BuiltInVariableType[], TCallbackArgs extends TEventArgs>(target: Entity \| Player, event: CodeBlockEvent<TEventArgs>, callback: (...payload: TCallbackArgs) => void): EventSubscription;Parameterstarget: Entity \| PlayerThe entity or player to listen to.event: CodeBlockEvent<TEventArgs>The incoming CodeBlockEvent object.callback: (...payload: TCallbackArgs) => voidCalled when the event is received with any data as arguments.ReturnsEventSubscriptionExamplesThis example demonstrates how to receive a built-in CodeBlock event using the connectCodeBlockEvent method.// Import CodeBlockEvents to access Built-in Events. import { Component, CodeBlockEvents, Player } from 'horizon/core';  class BuiltInEventExample extends Component {   start() {     this.connectCodeBlockEvent(      this.entity,      CodeBlockEvents.OnIndexTriggerDown,      (player: Player) => {        // Perform an action when the Index Trigger is pressed.      }    );      this.connectCodeBlockEvent (        this.entity,        CodeBlockEvents.OnGrabEnd,        (player: Player) => {        // Perform another action when the Grab Action ends.      }    );  } }  Component.register(BuiltInEventExample);RemarksThis method is used to listen for a given code block event sent from the player or an entity. |
| connectLocalBroadcastEvent(event, listener) | Adds a listener to the specified local event. The listener is called when the event is received.SignatureconnectLocalBroadcastEvent<TPayload extends LocalEventData>(event: LocalEvent<TPayload>, listener: (payload: TPayload) => void): EventSubscription;Parametersevent: LocalEvent<TPayload>The local event to listen to.listener: (payload: TPayload) => voidCalled when the event is received with any data as arguments.ReturnsEventSubscription |
| connectLocalEvent(target, event, callback) | Adds a listener to the local event on the given entity. The listener is called when the event is received.SignatureconnectLocalEvent<TPayload extends LocalEventData>(target: Entity \| Player, event: LocalEvent<TPayload>, callback: (payload: TPayload) => void): EventSubscription;Parameterstarget: Entity \| PlayerThe entity to listen to.event: LocalEvent<TPayload>The local event.callback: (payload: TPayload) => voidCalled when the event is received with any data as arguments.ReturnsEventSubscription |
| connectNetworkBroadcastEvent(event, callback) | Adds a listener to the specified network event. The listener is called when the event is received from the network.SignatureconnectNetworkBroadcastEvent<TPayload extends NetworkEventData>(event: NetworkEvent<TPayload>, callback: (payload: TPayload) => void): EventSubscription;Parametersevent: NetworkEvent<TPayload>The network event to listen to.callback: (payload: TPayload) => voidCalled when the event is received with any data as arguments.ReturnsEventSubscription |
| connectNetworkEvent(target, event, callback) | Adds a listener to the specified network event on the given entity. The listener is called when the event is received from network.SignatureconnectNetworkEvent<TPayload extends NetworkEventData>(target: Entity \| Player, event: NetworkEvent<TPayload>, callback: (payload: TPayload) => void): EventSubscription;Parameterstarget: Entity \| PlayerThe entity or player to listen to.event: NetworkEvent<TPayload>The network event.callback: (payload: TPayload) => voidCalled when the event is received with any data as arguments.ReturnsEventSubscription |
| dispose() | Called when the component is cleaned up.Signaturedispose(): void;ReturnsvoidRemarksSubscriptions registered using , , , and are cleaned up automatically. |
| getComponents(type) static | Returns a list of all script component instances of the specified type in the world. Only returns script component instances if they're executing in the same context (i.e. On the server or on a particular client). This method should not be used in prestart() as other script component instances may not yet be instantiated.Signaturestatic getComponents<T extends Component<unknown, SerializableState> = Component>(type: new () => T): T[];Parameterstype: new () => TThe specified type of Component.ReturnsT[]A list of all active instances of the specified component type in the current execution context (i.e., on the server or on a particular client). |
| preStart() | Performs initialization tasks before the method is called.SignaturepreStart(): void;ReturnsvoidRemarksThis method runs in these scenarios as follows:World start: preStart runs for all components before the start method of any component is called. Asset spawn: preStart runs before any start methods are called for any components that are spawning. Ownership transfer: preStart is called directly before the start method is called. |
| receiveOwnership(_serializableState, _oldOwner, _newOwner) | Called when the script's ownership is being transferred to a new player. This method allows the new owner to receive the serializable state from the previous owner during ownership transfer.SignaturereceiveOwnership(_serializableState: TSerializableState \| null, _oldOwner: Player, _newOwner: Player): void;Parameters_serializableState: TSerializableState \| nullThe serializable state from prior owner, or null if that state is invalid._oldOwner: PlayerThe prior owner._newOwner: PlayerThe current owner.ReturnsvoidExamplestype State = {ammo: number}; class WeaponWithAmmo extends Component<typeof WeaponWithAmmo, State> {   static propsDefinition = {     initialAmmo: {type: PropTypes.Number, default: 20},   };   private ammo: number = 0;   start() {     this.ammo = this.props.initialAmmo;   }   receiveOwnership(state: State \| null, fromPlayer: Player, toPlayer: Player) {     this.ammo = state?.ammo ?? this.ammo;   }   transferOwnership(fromPlayer: Player, toPlayer: Player): State {     return {ammo: this.ammo};   } }RemarksWhen changing entity ownership to a new player, you must transfer the state of the entity as well or the state will be lost. You can use the Component.transferOwnership() and Component.receiveOwnership() methods to transfer an entity's state to a new owner. For more information, see Maintaining local state on ownership change.If ownership for a parent entity changes, the ownership change doesn't automatically apply to any child entities.You must handle the edge case when the local state isn't transferred, such as the previous owner disconnecting from Horizon during a power or connectivity outage. In these cases, there's no guarantee that the entity's local state is transferred.The maximum size of state information that can be transferred is capped at 63kB. Transfers that are larger generate an error. |
| register(componentClass, componentName) static | Registers a component class as a component definition that is used to instantiate components of the given type, which also allows them to be attached to entities.Signaturestatic register<TComponentPropsDefinition>(componentClass: // this needs to be typed with the interface type so we know it can be instantiated (is not abstract)     ComponentWithConstructor<TComponentPropsDefinition> & typeof Component<ComponentWithConstructor<TComponentPropsDefinition>>, componentName?: string): void;ParameterscomponentClass: ComponentWithConstructor<TComponentPropsDefinition> & typeof Component<ComponentWithConstructor<TComponentPropsDefinition>>The component class to register.componentName: string(Optional) The name of component to display in the UI.ReturnsvoidExamplesIn this example, the NpcItem class is registered as a component definition.hz.Component.register(NpcItem);RemarksComponent registry is required when you create new classes that extend the abstract Component class. |
| registerDisposeOperation(operation) | Called to register a single operation. The operation runs automatically when the component is disposed unless it is manually run or canceled before the component is disposed.SignatureregisterDisposeOperation(operation: DisposeOperation): DisposeOperationRegistration;Parametersoperation: DisposeOperationA function called to perform a single dispose operation.ReturnsDisposeOperationRegistrationA registration object that can be used to manually run or cancel the operation before dispose. |
| sendCodeBlockEvent(target, event, args) | Sends a code block event to the specified player or entity. These events are networked automatically, and sent and handled asynchronously.SignaturesendCodeBlockEvent<TPayload extends BuiltInVariableType[]>(target: Entity \| Player, event: CodeBlockEvent<TPayload>, ...args: TPayload): void;Parameterstarget: Entity \| PlayerThe entity or player that receives the event.event: CodeBlockEvent<TPayload>The CodeBlockEvent that represents the event.args: TPayloadThe data to send with the event.Returnsvoid |
| sendLocalBroadcastEvent(event, data) | Sends a local event to all listeners.If a local event is sent, it is sent immediately. This function does not return until delivery completes.SignaturesendLocalBroadcastEvent<TPayload extends LocalEventData, TData extends TPayload>(event: LocalEvent<TPayload>, data: TData): void;Parametersevent: LocalEvent<TPayload>The local event to send.data: TDataReturnsvoid |
| sendLocalEvent(target, event, data) | Sends a local event to a specific entity from the owner of the entity.SignaturesendLocalEvent<TPayload extends LocalEventData, TData extends TPayload>(target: Entity \| Player, event: LocalEvent<TPayload>, data: TData): void;Parameterstarget: Entity \| PlayerThe entity that receives the event.event: LocalEvent<TPayload>The local event to send.data: TDataReturnsvoidRemarksThe event is sent immediately and this function does not return until delivery completes. |
| sendNetworkBroadcastEvent(event, data, players) | Broadcasts a network event. The event is only handled if the host listens to the event.SignaturesendNetworkBroadcastEvent<TPayload extends NetworkEventData>(event: NetworkEvent<TPayload>, data: TPayload, players?: Array<Player>): void;Parametersevent: NetworkEvent<TPayload>The network event to broadcast.data: TPayloadThe data to send with the event. the maximum amount data supported after serialization is 63kB.players: Array<Player>(Optional) The list of players devices to send the event to. If you do not specify this parameter, the event is sent to all devices owned by the player. You should only use this parameter if you are familiar with how it works.Returnsvoid |
| sendNetworkEvent(target, event, data, players) | Sends a network event to the player that owns the given entity.SignaturesendNetworkEvent<TPayload extends NetworkEventData>(target: Entity \| Player, event: NetworkEvent<TPayload>, data: TPayload, players?: Array<Player>): void;Parameterstarget: Entity \| PlayerThe player or entity that recieves the event.event: NetworkEvent<TPayload>The network event.data: TPayloadThe data to send with the event. the maximum amount data after serialization is 63kB.players: Array<Player>(Optional) The list of player devices to send the event to. If you don't specify this parameter, the event is sent to all devices owned by the player. You should only use specify this parameter if you understand it well.ReturnsvoidRemarksThe event is only handled if is called on the same entity on the owner client. |
| start() abstract | Called when the component starts running. This is where you can add event listeners that need to run when the script starts running.Signatureabstract start(): void;Returnsvoid |
| transferOwnership(_oldOwner, _newOwner) | Called when transferring the script's ownership to a new player. During the transer, this method can condense the previous owner's state into a serializable format and pass it to the new owner.SignaturetransferOwnership(_oldOwner: Player, _newOwner: Player): TSerializableState;Parameters_oldOwner: PlayerThe original owner._newOwner: PlayerThe new owner.ReturnsTSerializableStateThe serializable state to transfer to the new owner.Examplestype State = {ammo: number}; class WeaponWithAmmo extends Component<typeof WeaponWithAmmo, State> {   static propsDefinition = {     initialAmmo: {type: PropTypes.Number, default: 20},   };   private ammo: number = 0;   start() {     this.ammo = this.props.initialAmmo;   }   receiveOwnership(state: State \| null, fromPlayer: Player, toPlayer: Player) {     this.ammo = state?.ammo ?? this.ammo;   }   transferOwnership(fromPlayer: Player, toPlayer: Player): State {     return {ammo: this.ammo};   } }RemarksWhen changing entity ownership to a new player, you must transfer the state of the entity as well or the state will be lost. You can use the Component.transferOwnership() and Component.receiveOwnership() methods to transfer an entity's state to a new owner. For more information, see Maintaining local state on ownership change.If ownership for a parent entity changes, the ownership change doesn't automatically apply to any child entities.You must handle the edge case when the local state isn't transferred, such as the previous owner disconnecting from Horizon during a power or connectivity outage. In these cases, there's no guarantee that the entity's local state is transferred.The maximum size of state information that can be transferred is capped at 63kB. Transfers that are larger generate an error. |