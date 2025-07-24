# Trigger zone gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/use-the-trigger-zone)

The trigger zone [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) is used to trigger an event when you enter or exit a specified area.

## Use the trigger zone gizmo

*   From the Build list, select **Gizmos**.
    

*   Select **Trigger zone** icon.
    

*   Under **Hierarchy**, right-click **Trigger** and select **Rename**, then rename the trigger zone to something that describes its purpose. **Note**: Renaming the trigger zone is optional, but it can help you keep track of what the zone is for.

*   While the trigger zone is selected, you can edit its parameters in the **Properties** panel.

## Things to remember

*   Each trigger can be activated by either players or objects, but not both. If **Triggered By** is set to **Players**, any player in the world will be able to activate the Trigger.

*   If **Triggered By** is set to **Objects Named...**, the **Triggered by Objects Named** field must also be filled out. This field can currently only take one name, and any object with that name will be able to activate the trigger.

*   Note that objects may only have one name (or one word as a name), but multiple objects can have the same name. The size of the trigger area can be adjusted by using the handles, just like the rest of the shapes.

## Use the gizmo with TypeScript

Through TypeScript, you can monitor and take action when a Trigger Zone gizmo deployed in your world has been entered or exited by a player. In your TypeScript, you can create listeners for the following CodeBlockEvents, which are specific to trigger zones.

*   `onPlayerEnterTrigger`

*   `onPlayerExitTrigger`

CodeBlockEvents are a set of events emitted from the platform for key runtime functionality, such as events based on gizmo activities.

*   For more information on CodeBlockEvents, see [CodeBlock Events](/horizon-worlds/learn/documentation/typescript/events/codeblock-events) .

*   For API docs on CodeBlockEvents, see [CodeBlockEvents](https://horizon.meta.com/resources/scripting-api/core.codeblockevents.md/) .

The following script can be attached to a Trigger Zone entity that you have deployed in your world:

```
import * as hz from 'horizon/core';

class TriggerMe extends hz.Component<typeof TriggerMe> {

  start() {
    // this listener for the CodeBlockEvent onPlayerEnterTrigger is fired
    // when a player enters the trigger.
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerEnterTrigger, (enteredby:hz.Player)=>{
      this.world.ui.showPopupForEveryone("You dare enter the Trigger of Doom, " + enteredby.name.get() + "?!?!", 3)
    });

    // this listener for the CodeBlockEvent onPlayerExitTrigger is fired
    // when a player exits the trigger.
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerExitTrigger, (exitedBy:hz.Player)=>{
      this.world.ui.showPopupForEveryone("See you, " + exitedBy.name.get() + ".", 2)
    });

  }
}
hz.Component.register(TriggerMe);
```

The above script defines to event listeners ( `this.connectCodeBlockEvent` ), one for each CodeBlockEvent for the trigger. Since this script is attached to the trigger zone entity, these listeners are triggered based on the entrance and exit of the `enteredby` player to the trigger zone.

In the `onPlayerEnterTrigger` listener, a popup is displayed for everyone in the world with a message.

In the `onPlayerExitTrigger` listener, a new popup is displayed for everyone in the world with a different message.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 