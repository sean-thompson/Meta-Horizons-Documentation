# Grabbing for Scripted Avatar NPCs

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/grabbing-for-scripted-avatar-npcs)

As needed, you can have the Scripted Avatar NPCs grab items for use. For example, your NPC can grab a weapon and start shooting if the player makes a threatening move. **API docs**:

*   [AgentGrabbableInteraction](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.agentgrabbableinteraction.md/?api_version=2.0.0)

*   [AgentGrabActionResult](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.agentgrabactionresult.md/?api_version=2.0.0)

## Configure Grabbable Entities

Entities that the Scripted Avatar NPC can grab must be configured to be grabbable as part of their properties.

*   Select the entity.

*   In the Properties panel, specify the following properties: 
    
    ![Set properties to make an entity grabbable](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/487300512_686408190563802_1452896021331852883_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=Oy_zWl2HFlsQ7kNvwHfi1eR&_nc_oc=AdnqN5n72VlUU5MFsOhfcrMH-AZb_v1o9buK4StS5puZjzCr4evvWTmlPDzUe66-uyU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=v6obHuN78aJVJ775LW41fA&oh=00_AfSZpjRJ9ojPIX-qyZqyXFebNjqSmCWOl7DV9qggT-2HaA&oe=689BB658) 

| Property | Description |
| --- | --- |
| Collidable | Set to true. |
| Collision Layer | Set to Everything. |
| Motion | Set to Interactive. The Interaction property appears. |
| Interaction | Set to Grabbable or Both. |

## NPC Grabbing

In the following example, a Scripted Avatar NPC is surrounded by a trigger zone. When the trigger zone is breached by a player, the NPC grabs the gun. When the player leaves the trigger zone, the gun is dropped.

![Trigger Zone with Scripted Avatar NPC and Grabbable Entity](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/469079038_603532522184703_8574428875098342118_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=eZ2SZ46kxH4Q7kNvwFujq2W&_nc_oc=AdnfcpcYoiP8NBTunuvKVXc3vTwWB0idkfLjTNeLMSaPy0HrrPWQVpZcxdQ1zMGCfSE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=v6obHuN78aJVJ775LW41fA&oh=00_AfTjWvK756R0qVZ8j2kDZClf8xbpTa_XEbDIwDSHaYN8mA&oe=689BA02F)

```
import * as hz from 'horizon/core';
import { AgentGrabActionResult, AvatarAIAgent } from 'horizon/avatar_ai_agent';

class testScriptedNPCGrab extends hz.Component<typeof testScriptedNPCGrab> {
  static propsDefinition = {
    npc: { type: hz.PropTypes.Entity },
    weapon: { type: hz.PropTypes.Entity },
  };

  start() {
    if (!this.props.weapon) {
      console.error("No weapon defined!");
      return;
    };
    let myWeapon: hz.Entity = this.props.weapon;

    if (this.props.npc) {
      let npcGizmo = this.props.npc.as(AvatarAIAgent);
      this.connectCodeBlockEvent(
        this.entity,
        hz.CodeBlockEvents.OnPlayerEnterTrigger,
        (player) => {
          npcGizmo.grabbableInteraction.grab(hz.Handedness.Right, myWeapon).then((grabResult) => {
              switch (grabResult) {
                case AgentGrabActionResult.Success:
                  console.log("Grabbin' my gun!")
                  break;
                case AgentGrabActionResult.AlreadyHolding:
                  console.log("Already got it.");
                  break;
                case AgentGrabActionResult.NotAllowed:
                  console.log("Hey, how come I can't grab muh gun?");
                  break;
                case AgentGrabActionResult.InvalidEntity:
                  console.error("Invalid entry error grabbing gun");
                  break;
              };
            });
          });

      this.connectCodeBlockEvent(
        this.entity,
        hz.CodeBlockEvents.OnPlayerExitTrigger,
        (player) => {
            npcGizmo.grabbableInteraction.drop(hz.Handedness.Right);
            console.log("Ok, let's talk then.");
          })
    } else {
      console.error("No NPC defined!")
      return;
    };

  };
};
hz.Component.register(testScriptedNPCGrab);
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 