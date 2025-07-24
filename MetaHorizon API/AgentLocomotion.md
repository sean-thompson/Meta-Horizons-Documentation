# AgentLocomotion Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/avatar_ai_agent_agentlocomotion)

Exposes the locomotion features of an AI agent.

## Signature

```
export declare class AgentLocomotion
```

## Remarks

To use agent locomotion, you must enable Navigation Locomotion in Desktop Editor. For more information, see the [Nav Mesh Agents](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/nav-mesh-agents) guide.

## Properties

<table>
  <tbody>
    <tr>
      <td>**entity**</td>
      <td>The entity that is attached to the agent.

Signature

```
entity: Entity;
```</td>
    </tr>
    <tr>
      <td>**isGrounded**</td>
      <td>Indicates whether the agent is on the ground. true if the agent is on the ground, false if the agent is above, below, or otherwise away from the ground.

Signature

```
isGrounded: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**isJumping**</td>
      <td>Indicates whether the agent is performing a jump.

Signature

```
isJumping: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**isMoving**</td>
      <td>Indicates whether the agent is moving.

Signature

```
isMoving: ReadableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**targetDirection**</td>
      <td>The current target direction of the agent. Undefined if the agent isn't currently rotating to a specific target direction.

Signature

```
targetDirection: ReadableHorizonProperty<Vec3 | undefined>;
```</td>
    </tr>
    <tr>
      <td>**targetPosition**</td>
      <td>The current locomotion target of the agent. Undefined if the agent isn't currently moving.

Signature

```
targetPosition: ReadableHorizonProperty<Vec3 | undefined>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| jump() | Issues a jump command.Signaturejump(): Promise<AgentLocomotionResult>;ReturnsPromise<AgentLocomotionResult>A promise describing how the jump ended. |
| moveToPosition(position, options) | Issues a movement command to the agent. Issuing a new move, rotate, follow, or jump command cancels any previous move command.SignaturemoveToPosition(position: Vec3, options?: AgentLocomotionOptions): Promise<AgentLocomotionResult>;Parametersposition: Vec3The desired destination.options: AgentLocomotionOptions(Optional) Optional parameters.ReturnsPromise<AgentLocomotionResult>- A promise describing how the locomotion ended. |
| moveToPositions(path, options) | Issues a movement command along a path. Issuing a new move, rotate, follow, or jump command cancels any previous move command.SignaturemoveToPositions(path: Array<Vec3>, options?: AgentLocomotionOptions): Promise<AgentLocomotionResult>;Parameterspath: Array<Vec3>An array of points to follow, in order.options: AgentLocomotionOptions(Optional) Optional parametersReturnsPromise<AgentLocomotionResult>- A promise describing how the locomotion ended. |
| rotateTo(direction, options) | Issues a rotation command to change the direction the agent faces. Issuing a new move, rotate, follow, or jump command cancels any previous move command.SignaturerotateTo(direction: Vec3, options?: AgentRotationOptions): Promise<AgentLocomotionResult>;Parametersdirection: Vec3The desired facing direction.options: AgentRotationOptions(Optional) Optional parameters.ReturnsPromise<AgentLocomotionResult>- A promise describing how the rotation ended. |
| stopMovement() | Stops any movement in progress.SignaturestopMovement(): void;Returnsvoid |