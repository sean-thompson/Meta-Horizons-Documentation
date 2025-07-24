# AvatarAIAgent Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/avatar_ai_agent_avataraiagent)

Extends *AIAgentGizmo* An AI-powered NPC that scripts can spawn and despawn at runtime and is represented by a player avatar. `AvatarAIAgent` objects are also capable of pathfinding, locomotion, and grabbale interacation.

## Signature

```
export declare class AvatarAIAgent extends AIAgentGizmo
```

## Remarks

For more information, see [Getting Started with Scripted Avatar NPCs](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/getting-started-with-scripted-avatar-npcs) and [Spawning for Scripted Avatar NPCs](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/spawning-for-scripted-avatar-npcs) .

## Properties

<table>
  <tbody>
    <tr>
      <td>**agentPlayer**</td>
      <td>The player controlled by the `AvatarAIAgent` object.

Signature

```
agentPlayer: ReadableHorizonProperty<Player | undefined>;
```</td>
    </tr>
    <tr>
      <td>**grabbableInteraction**

\[readonly\]</td>
      <td>The grabbable interaction capabilities of the agent.

Signature

```
readonly grabbableInteraction: AgentGrabbableInteraction;
```</td>
    </tr>
    <tr>
      <td>**locomotion**

\[readonly\]</td>
      <td>The Locomotion capabilities of the agent.

Signature

```
readonly locomotion: AgentLocomotion;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| despawnAgentPlayer() | Despawns the player controlled by the AvatarAIAgent object.SignaturedespawnAgentPlayer(): void;Returnsvoid |
| getGizmoFromPlayer(player) static | Returns the AIAgentGizmo that is associated with the provided player.Signaturestatic getGizmoFromPlayer(player: Player): Entity \| undefined;Parametersplayer: PlayerThe player.ReturnsEntity \| undefinedThe gizmo, or undefined if no gizmo is associated with the player. |
| spawnAgentPlayer() | Spawns a player controlled by the AvatarAIAgent object.SignaturespawnAgentPlayer(): Promise<AgentSpawnResult>;ReturnsPromise<AgentSpawnResult>A promise describing the results of the spawn operation. |
| toString() | The ID of the AvatarAIAgent object.SignaturetoString(): string;ReturnsstringA string representation of the ID. |