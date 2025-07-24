# Spawning for Scripted Avatar NPCs

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/spawning-for-scripted-avatar-npcs)

By default, Scripted Avatar NPCs that are added to your world are spawned in when the world is started. Like a player entering the world, the Scripted Avatar NPC begins interacting with the world based on your scripted behaviors.

In some cases, however, you may prefer to spawn in Scripted Avatar NPCs during runtime. For example, if a wizard suddenly appears in the world, you can use the available API methods for spawning and despawning NPCs. **Note**: Adding a Scripted Avatar NPC impacts performance and consumes the same resources as adding another player to your world.

## Spawn at Start

An Scripted Avatar NPC entity in your world can be configured to spawn into the world when it is initialized.

*   Select the Scripted Avatar NPC entity in your world.

*   In the Properties panel, set Spawn at Start to `true`. **Tip**: To test performance, you may want to set all Scripted Avatar NPCs to spawn at start so that you can see the maximum resource usage related to Scripted Avatar NPCs.

## NPC Detection

If you use the `onPlayerEnterWorld` CodeBlock event, you will notice that the event detects an arriving or spawning NPC as a player. In most cases, you want to handle player and NPC arrivals and departures differently.

You can use the following code to determine if the entering entity is a player or an NPC:

```
this.connectCodeBlockEvent(
      this.entity,
      hz.CodeBlockEvents.OnPlayerEnterWorld,
      (player: hz.Player) => {
        // isNPC == true -> NPC; isNPC == false -> player
        const isNpc = AvatarAIAgent.getGizmoFromPlayer(player) !== undefined;
      }
    );
```

## spawnAgentPlayer() method

At runtime, you can spawn in a Scripted Avatar NPC using the spawnAgentPlayer() method. **Example**:

The following example attempts to spawn the NPC specified in the `npc` property. If spawning returns an error, an error message is reported to the console:

```
let npcGizmo = this.props.npc.as(AvatarAIAgent);
npcGizmo.spawnAgentPlayer().then((spawnResult) => {
    if (spawnResult == AgentSpawnResult.Error) {
      console.error("Failed to spawn NPC " + npcGizmo.name.get() + "!")
    };
  };
);
``` **API docs**: [spawnAgentPlayer](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.avataraiagent.spawnagentplayer.md/?api_version=2.0.0) ## despawnAgentPlayer() method

You can despawn a Scripted Avatar NPC using the following method. **Note**: Despawning a Scripted Avatar NPC destroys the entity and removes it from the world. **Example**:

```
let npcGizmo = this.entity.as(AvatarAIAgent);
npcGizmo.despawnAgentPlayer();
``` **API docs**: [despawnAgentPlayer](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.avataraiagent.despawnagentplayer.md/?api_version=2.0.0) ## Example Script

The following example script is attached to a Trigger Zone gizmo. When the gizmo is breached by a player, the Scripted Avatar NPC (a wizard) appears. When the player exits, the Scripted Avatar NPC disappears.

```
import * as hz from 'horizon/core';
import { AgentLocomotionOptions, AgentSpawnResult, AvatarAIAgent } from 'horizon/avatar_ai_agent';

class testScript03 extends hz.Component<typeof testScript03> {

  static propsDefinition = {
    npc: { type: hz.PropTypes.Entity },
  };


  start() {
    if (this.props.npc) {
      let npcGizmo = this.props.npc.as(AvatarAIAgent);

      this.connectCodeBlockEvent(
        this.entity,
        hz.CodeBlockEvents.OnPlayerEnterTrigger,
        (player) => {
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
        });


      this.connectCodeBlockEvent(
        this.entity,
        hz.CodeBlockEvents.OnPlayerExitTrigger,
        (player) => {
          console.log("See ya, wizard!")
          npcGizmo.despawnAgentPlayer()
        });
    };
  };
};
hz.Component.register(testScript03);
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 