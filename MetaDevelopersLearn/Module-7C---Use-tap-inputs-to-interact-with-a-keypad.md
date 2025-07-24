# Module 7C - Use tap inputs to interact with a keypad

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/developing-for-web-and-mobile-players-tutorial/module-7c-use-tap-inputs-to-interact-with-a-keypad)

At this point, we can rotate the objects to acquire the code numbers. Now, we must support entering the code into the keypad.

We use Focused Interaction API again, in conjunction with raycasts, to find out which button the player pressed.

Find the keypad object in the world. In the Hierarchy panel, you can see that RoomB_Keypad also contains:

*   A Trigger Zone gizmo to interact with it, which should allow the player to enter Focus mode (as we did with the clues)

*   All numeric buttons

*   A Raycast gizmo

![Screenshot of the Keypad node displayed in the Hierarchy panel and in the main viewport of the desktop editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489890462_692135409991080_9185380006179677715_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=-VriIz9eu74Q7kNvwGR7H2a&_nc_oc=Adk5pUMgxTZJ9jUYvetvVV5k4AjoYXEfDOR62q5VkrKfo3XrmCOBJa4InJMDu4yuQFA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CZzKHqM_oRIoRDmv1LDKBQ&oh=00_AfTeIr_z4Eju-J4uuW2zqKHDK7muvT1B4-d41v_ih_dP0A&oe=689B9A71)

We break the logic to manage keypad interactions into two scripts:

| Script | Description |
| --- | --- |
| RoomB_Keypad | - Manages the raycast- Notifies the buttons that they have been pressed- Verifies if the entered code is correct |
| RoomB_KeypadButton | - Receives event that it has been pressed- Communicates to the keypad the number that was pressed. |

## Define Keypad events

Open the sysEvents script and check that the OnButtonPressed event is defined. We use this event to communicate from the buttons to the keypad.

```
// Room B - Keypad events
OnButtonPressed: new hz.NetworkEvent<{number: number}>("OnButtonPressed"),
```

## KeypadButton script

Let’s start with the RoomB_KeypadButton script.

We must implement the button for VR players, which means detecting when a player physically presses the button by listening for the OnPlayerCollision event. Locate the following TODO in the file:

```
// TODO: Listen for collisions with the player to press the button. Applicable for VR players physically pressing the button
```

Replace the above with the following:

```
this.connectCodeBlockEvent(
  this.entity,
  hz.CodeBlockEvents.OnPlayerCollision,
  () => {
    this.HandleButtonPress(keypad);
  },
);
```

The above calls the HandleButtonPress function, which manages moving the button and notifying the keypad.

Now we implement the keypress logic for web and mobile players. These players do not physically press the button. Instead, the keypad uses a raycast and sends the OnEntityTapped event to the pressed button. So, we listen to this event and call the same function as used for VR.

Locate the following TODO:

```
// TODO: Listen for `OnEntityTapped` events to press the button. Applicable for Web and Mobile players using Focused Interaction to press the button
```

Replace the above with:

```
this.connectNetworkEvent(this.entity, sysEvents.OnEntityTapped, () => {
  this.HandleButtonPress(keypad);
});
```

We can now press the buttons in VR, web and mobile.

However, the keypad still does not receive the specific number that has been pressed. We must send the OnButtonPressed event to the keypad with the button number as a parameter.

Locate the following TODO inside the HandleButtonPress function:

```
// TODO: Notify the keypad that a button has been pressed
```

Replace the above with this line:

```
this.sendNetworkEvent(keypad, sysEvents.OnButtonPressed, {
  number: this.props.number,
});
```

We’re done with the keypad buttons!

Your RoomB_KeypadButton script should look like this now:

```
import * as hz from 'horizon/core';
import { sysEvents } from 'sysEvents';

class RoomB_KeypadButton extends hz.Component<typeof RoomB_KeypadButton> {
  static propsDefinition = {
    keypad: { type: hz.PropTypes.Entity },
    number: { type: hz.PropTypes.Number },
  };


  private startPos = hz.Vec3.zero;
  private pushedPos = hz.Vec3.zero;
  private isPushed = false;


  start() {
    const keypad: hz.Entity \| undefined = this.props.keypad;
    if (keypad === undefined) return;


    this.startPos = this.entity.position.get();
    this.pushedPos = this.startPos.add(this.entity.forward.get().mul(-0.02));
    this.isPushed = false;


    // Listen for collisions with the player to press the button. Applicable for VR players physically pressing the button
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerCollision, () => {
      this.HandleButtonPress(keypad);
    });


    // Listen for `OnEntityTapped` events to press the button. Applicable for Web and Mobile players using Focused Interaction to press the button
    this.connectNetworkEvent(this.entity, sysEvents.OnEntityTapped, () => {
      this.HandleButtonPress(keypad);
    });
  }


  private HandleButtonPress(keypad: hz.Entity) {
    if (this.isPushed) return;


      this.isPushed = true;
      this.entity.position.set(this.pushedPos);
      // Notify the keypad that a button has been pressed
      this.sendNetworkEvent(keypad, sysEvents.OnButtonPressed, { number: this.props.number });
      // Reset the button after a small delay
      this.async.setTimeout(() => this.ResetButton(), 300);
  }


  private ResetButton() {
    this.entity.position.set(this.startPos);
    this.isPushed = false;
  }
}
hz.Component.register(RoomB_KeypadButton);
```

## RoomB_Keypad script

Let’s continue with the keypad. As we did clues, we must implement entering Focus mode when a player interacts with the object and manage exiting Focus mode.

#### Enter Focus mode:

Open the RoomB_Keypad script. Locate the following TODO:

```
// TODO: Enter Focused Interaction mode when a player interacts with the object
```

Replace the above with the following code:

```
this.connectCodeBlockEvent(
  this.entity,
  hz.CodeBlockEvents.OnPlayerEnterTrigger,
  (player: hz.Player) => {
    if (
      this.activePlayer === this.world.getServerPlayer() &&
      player.deviceType.get() !== hz.PlayerDeviceType.VR
    ) {
      this.activePlayer = player;
      this.sendNetworkEvent(player, sysEvents.OnStartFocusMode, {
        exampleController: this.entity,
        cameraPosition: cameraPos,
        cameraRotation: cameraRot,
      });
      this.sendNetworkEvent(player, sysEvents.OnSetCameraFOV, {
        newFOV: this.props.cameraFov,
      });
    }
  },
);
``` **Note**: We’re also changing the camera field of view in this interaction. We want to position the camera very close to the keypad to avoid the view obstruction, and we increase the field of view to be able to see the whole keypad.

#### Exit Focus mode:

Next, we listen for when a player leaves Focus mode to reset the camera field of view and the active player.

Locate the following TODO:

```
// TODO: Reset status after a player exits Focused Interaction mode
```

Replace the above with this code:

```
this.connectNetworkEvent(this.entity, sysEvents.OnExitFocusMode, data => {
  if (this.activePlayer === data.player) {
    this.activePlayer = this.world.getServerPlayer();
    this.sendNetworkEvent(data.player, sysEvents.OnResetCameraFOV, {});
  }
});
```

#### Process Focus mode inputs:

We can now interact with the keypad to enter Focus mode, but we are not processing the input yet.

*   We must listen to the OnFocusedInteractionInputEnded event to check where the user has clicked.

*   We use a raycast to see which object has been clicked.

*   We send the OnEntityTapped event to that entity.

Locate the following TODO:

```
// TODO: Tracking Focused Interaction inputs to check if a button was tapped
```

Replace the above with this code:

```
this.connectNetworkEvent(this.entity, sysEvents.OnFocusedInteractionInputEnded, (data) => {
  const interaction = data.interactionInfo;
  if (interaction !== undefined && interaction.interactionIndex === 0 && this.raycastGizmo) {
    const hit: hz.RaycastHit \| null = this.raycastGizmo.raycast(interaction.worldRayOrigin, interaction.worldRayDirection);
    if (hit && hit.targetType === hz.RaycastTargetType.Entity && hit.target) {
      this.sendNetworkEvent(hit.target, sysEvents.OnEntityTapped, null);
    }
  }
});
```

If the user has selected a keypad button, it processes the OnEntityTapped event and sends the OnButtonPressed event back to the keypad, including the number that has been pressed.

We listen to this event and check if the entered four-digit code is correct. If so, we notify the Puzzle Manager that the puzzle has been completed successfully.

Locate the next TODO in the RoomB_Keypad script:

```
// TODO: When `OnButtonPressed` is received, update `currentCode`, check if the code is correct. If it is, notify the Puzzle Manager to finish the puzzle and exit Focused Interaction mode
```

Replace the above with the following code:

```
this.connectNetworkEvent(this.entity, sysEvents.OnButtonPressed, (data) => {
  if (!this.enabled \|\| this.guessedCode) return;

  ++this.digitCount;
  this.currentCode += data.number + " ";
  this.UpdateDigitsText(this.currentCode);

  if (this.digitCount === this.maxDigitCount) {
    this.guessedCode = this.CheckCode();
  if (this.guessedCode) {
      this.props.digitsText?.color.set(hz.Color.green);
      // Notify the Puzzle Manager that the puzzle is finished
      if (this.props.puzzleManager) this.sendNetworkEvent(this.props.puzzleManager, sysEvents.OnFinishPuzzle, {});
    } else {
      this.props.digitsText?.color.set(hz.Color.red);
      this.enabled = false;
      this.async.setTimeout(() => this.ResetKeypad(), 1500);
    }
  }
});
```

## Checkpoint

You’re done making the RoomB_Keypad script! It should look like the following:

```
import * as hz from 'horizon/core';
import { sysEvents } from 'sysEvents';


class RoomB_Keypad extends hz.Component<typeof RoomB_Keypad> {
  static propsDefinition = {
    digitsText: {type: hz.PropTypes.Entity},
    correctCode: {type: hz.PropTypes.String},
    puzzleManager: {type: hz.PropTypes.Entity},
    tappingRaycast: {type: hz.PropTypes.Entity},
    relativeCameraPosition: {type: hz.PropTypes.Vec3},
    cameraRotation: {type: hz.PropTypes.Vec3},
    cameraFov: {type: hz.PropTypes.Number},
  };


  private digitCount = 0;
  private maxDigitCount = 4;
  private currentCode = "";
  private guessedCode = false;
  private enabled = true;
  private originalDigitsTextColor!: hz.Color;


  private activePlayer!: hz.Player;
  private raycastGizmo!: hz.RaycastGizmo \| null;


  start() {
    this.activePlayer = this.world.getServerPlayer();
    const cameraPos = hz.Vec3.add(this.entity.position.get(), this.props.relativeCameraPosition);
    const cameraRot = hz.Quaternion.fromEuler(this.props.cameraRotation);


    if (this.props.digitsText) {
      this.originalDigitsTextColor = this.props.digitsText.color.get();
    }


    if (this.props.tappingRaycast) {
      this.raycastGizmo = this.props.tappingRaycast.as(hz.RaycastGizmo);
    }


    // Enter Focused Interaction mode when a player interacts with the object
    this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnPlayerEnterTrigger, (player: hz.Player) => {
      if (this.activePlayer === this.world.getServerPlayer() && player.deviceType.get() !== hz.PlayerDeviceType.VR) {
        this.activePlayer = player;
        this.sendNetworkEvent(player, sysEvents.OnStartFocusMode, {exampleController: this.entity, cameraPosition: cameraPos, cameraRotation: cameraRot});
        this.sendNetworkEvent(player, sysEvents.OnSetCameraFOV, {newFOV: this.props.cameraFov});
      }
    });


    // Reset status after a player exits Focused Interaction mode
    this.connectNetworkEvent(this.entity, sysEvents.OnExitFocusMode, (data) => {
      if (this.activePlayer === data.player) {
        this.activePlayer = this.world.getServerPlayer();
        this.sendNetworkEvent(data.player, sysEvents.OnResetCameraFOV, {});
      }
    });


    // Tracking Focused Interaction inputs to check if a button was tapped
    this.connectNetworkEvent(this.entity, sysEvents.OnFocusedInteractionInputEnded, (data) => {
      const interaction = data.interactionInfo;
      if (interaction !== undefined && interaction.interactionIndex === 0 && this.raycastGizmo) {
        const hit: hz.RaycastHit \| null = this.raycastGizmo.raycast(interaction.worldRayOrigin, interaction.worldRayDirection);
        if (hit && hit.targetType === hz.RaycastTargetType.Entity && hit.target) {
          this.sendNetworkEvent(hit.target, sysEvents.OnEntityTapped, null);
        }
      }
    });


    // When `OnButtonPressed` is received, update `currentCode`, check if the code is correct. If it is, notify the Puzzle Manager to finish the puzzle and exit Focused Interaction mode
    this.connectNetworkEvent(this.entity, sysEvents.OnButtonPressed, (data) => {
      if (!this.enabled \|\| this.guessedCode) return;


      ++this.digitCount;
      this.currentCode += data.number + " ";
      this.UpdateDigitsText(this.currentCode);


      if (this.digitCount === this.maxDigitCount) {
        this.guessedCode = this.CheckCode();


        if (this.guessedCode) {
          this.props.digitsText?.color.set(hz.Color.green);
          // Notify the Puzzle Manager that the puzzle is finished
          if (this.props.puzzleManager) this.sendNetworkEvent(this.props.puzzleManager, sysEvents.OnFinishPuzzle, {});
        } else {
          this.props.digitsText?.color.set(hz.Color.red);
          this.enabled = false;
          this.async.setTimeout(() => this.ResetKeypad(), 1500);
        }
      }
    });
  }


  private ResetKeypad() {
    this.digitCount = 0;
    this.currentCode = "";
    this.UpdateDigitsText(this.currentCode);
    this.props.digitsText?.color.set(this.originalDigitsTextColor);
    this.enabled = true;
  }


  private UpdateDigitsText(newDigitsText: string) {
    this.props.digitsText?.as(hz.TextGizmo)?.text.set("<align=left>" + newDigitsText);
  }


  private CheckCode(): boolean {
    return this.currentCode.replace(/ /g, "") === this.props.correctCode.replace(/ /g, "");
  }
}
hz.Component.register(RoomB_Keypad);
```

You finished implementing a keypad that can be used by web, mobile and VR players!

#### Test:

At this point, you should be able to enter the Secret Code puzzle room, turn over all objects, and then use the raycast on the keypad to enter the secret code. After that, the door opens, and you can complete the puzzle.

In this module, you:

*   Created a Focused Interaction Manager

*   Learned how to use the Focused Interaction API

*   Used the Focused Interaction API and the Camera API to rotate objects and interact with a keypad, making both mechanics fun for all platforms.

## Additional Documentation and APIs

#### Additional documentation:

*   [2D UI for Web and Mobile](/horizon-worlds/learn/documentation/create-for-web-and-mobile/references-and-guides/2d-ui-for-web-and-mobile)
    

*   [Safe Placement of UI Controls](/horizon-worlds/learn/documentation/create-for-web-and-mobile/designing-worlds-for-mobile-and-web/safe-placement-of-ui-controls/)
    

#### API docs:

*   [RaycastGizmo](https://horizon.meta.com/resources/scripting-api/core.raycastgizmo.md/?api_version=2.0.0)

*   [TextGizmo](https://horizon.meta.com/resources/scripting-api/core.textgizmo.md/?api_version=2.0.0)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 