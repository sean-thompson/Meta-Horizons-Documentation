# API Overview for Scripted Avatar NPCs

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/api-overview-for-scripted-avatar-npcs)

This section outlines the basics for using APIs to drive behavior in your Scripted Avatar NPCs. **Note**: The `avatar_ai_agent` API module is supported in the TypeScript API v2.0.0 and later. Earlier versions of the API are not supported. The examples provided use v2.0.0.

## Import

To access the AI agent API, import the following module in your script:

```
import { AvatarAIAgent } from "horizon/avatar_ai_agent";
``` **API docs**: [AvatarAIAgent](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.md/?api_version=2.0.0) ## Assign NPC entity

Your NPC entity must be assigned as an AvatarAIAgent. This example demonstrates how to assign the NPC entity if the script is attached to the NPC.

```
let myNPC: AvatarAIAgent = this.entity.as(AvatarAIAgent)
```

If the script is not attached to the NPC, then you must create a reference to it as a script property:

```
let npcGizmo = this.props.npc.as(AvatarAIAgent);
```

## Locomotion

The AvatarAIAgent module contains the `AgentLocomotion` class, which supports the following movement properties and methods. **Note**: Locomotion benefits from use of a navigation mesh and navigation profile, although they are not required. For more information, see [Build Navigation for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/build-navigation-for-scripted-avatar-npcs) . **API docs**: [AgentLocomotion class](/horizon-worlds/reference/2.0.0/avatar_ai_agent_agentlocomotion) ### Methods

| Method | Description |
| --- | --- |
| moveToPostion() | Move the NPC to a specified Vec3 position. |
| moveToPositions() | Move the NPC through a sequence of locations, specified as an array of Vec3 positions. |
| rotateTo() | Rotate the NPC to a specified Vec rotation. |
| stopMovement() | Stop any positional or rotational movement on the NPC. This function returns void. |
| jump() | Make the NPC jump. | **Example: moveToPosition()** The following basic example executes a `moveToPosition()` call and captures the `result`.

```
this.props.npc!
  .as(AvatarAIAgent)
  .locomotion.moveToPosition(hz.Vec3.zero);
  .then((result) => console.log("move to position result: " + result));
``` **Example: rotateTo()** The following basic example executes a `rotateTo()` call so the NPC does a 180 degree turn and captures the `result`.

```
const dir : hz.Vec3 = this.npc.agentPlayer.get()!.forward.get().mul(-1);
    this.props.npc!
      .as(AvatarAIAgent)
      .locomotion.rotateTo(dir)
      .then((result) => console.log("rotate to direction result: " + result));
``` **Example: jump()** The following basic example executes a `jump()` and captures the `result`.

```
this.props.npc!.locomotion.jump()
  .then(
    (result) => console.log("jump result: " + result);
  );
```

### Properties

| Property | Description |
| --- | --- |
| targetPosition.get() | Returns the current target Vec3 position of the agent. Undefined if it is not moving. |
| targetDirection.get() | Returns the current target Vec3 rotation of the agent. Undefined if it is not rotating to a target. |
| isMoving.get() | Returns true if the agent is in motion. |
| isGrounded.get() | Returns true if the agent is on the ground. |
| isJumping.get() | Returns true if the agent is currently jumping. | **Example**:

```
this.entity.as(AvatarAIAgent).locomotion.isJumping.get();
```

For more information, see [Build Navigation for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/build-navigation-for-scripted-avatar-npcs) .

## Spawning and Despawning

You can spawn and despawn your NPC during runtime. **Note**: Each NPC gizmo can be associated with only one instance of the NPC. **Note**: Spawning in new NPCs consumes additional resources. For more information, see “Best Practices” in [Getting Started with Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/getting-started-with-scripted-avatar-npcs) .

### spawnAgentPlayer()

The `spawnAgentPlayer()` method returns a promise based on its ability to execute the spawning:

```
npcGizmo.spawnAgentPlayer().then((spawnResult) => {
  switch (spawnResult) {
    case AgentSpawnResult.Success:
      console.log("Behold the wizard!");
      break;
    case AgentSpawnResult.AlreadySpawned:
      console.log("The wizard has been here all along!");
      break;
    case AgentSpawnResult.WorldAtCapacity:
      console.log("There's no room for the wizard...");
      break;
    case AgentSpawnResult.Error:
      console.log("Can't spawn the wizard");
      break;
  };
});
``` **API docs**: [spawnAgentPlayer](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.avataraiagent.spawnagentplayer.md/?api_version=2.0.0) ### despawnPlayerAgent()

The `despawnPlayerAgent()` method removes the entity from the world: **Example**:

```
this.entity.despawnAgentPlayer();
``` **API docs**: [despawnAgentPlayer](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.avataraiagent.despawnagentplayer.md/?api_version=2.0.0) For more information on spawning and despawning, see [Spawning for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/spawning-for-scripted-avatar-npcs) .

## Grabbing

Within the `AvatarAIAgent` class, the `agentGrabbableInteraction` class can be used to have the Scripted Avatar NPC grab and drop entities in the world. **Note**: Entities that can be grabbed by NPCs must be configured to be grabbable in their Properties panel. **Rules on ownership**:

*   In Meta Horizon Worlds, all unassigned entities/items are owned by the server.

*   When an entity or player grabs an item, ownership of the item is transferred to the grabbing entity/player.

*   When an entity/player drops an item, the item’s ownership remains with the entity/player until 1) the item is grabbed by another entity/player or 2) ownership of the item is explicitly assigned by TypeScript.

*   The above rules are consistent for players and entities, including Scripted Avatar NPCs, across Meta Horizon Worlds. **API docs**: [AgentGrabbableInteraction](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.agentgrabbableinteraction.md/?api_version=2.0.0) | Method | Description |
| --- | --- |
| grab() | Grab a specified entity using a specified hand. |
| getGrabbedEntity() | Gets an entity that is currently held by a specified hand. Returns a Promise indicating how the retrieval ended. If successful, the entity can then be dropped. |
| drop() | Drops an entity using a specified hand. | **Example**:

The following snippet commands the NPC to grab a specified entity ( `this.pickupItem` ) with the left hand ( `hz.Handedness.Left` ):

```
this.npc.grabbableInteraction.grab(hz.Handedness.Left, this.pickupItem);
```

For more information, see [Grabbing for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/grabbing-for-scripted-avatar-npcs) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 