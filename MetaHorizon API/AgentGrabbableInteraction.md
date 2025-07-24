# AgentGrabbableInteraction Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/avatar_ai_agent_agentgrabbableinteraction)

The grabbing features of an agent.

## Signature

```
export declare class AgentGrabbableInteraction
```

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
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**drop(handedness)**</td>
      <td>Commands an agent to drop a held item.

Signature

```
drop(handedness: Handedness): void;
```

Parameters

handedness: Handedness

The hand to drop the item from.

Returns

void</td>
    </tr>
    <tr>
      <td>**getGrabbedEntity(handedness)**</td>
      <td>Gets the entity currently held by the specified hand.

Signature

```
getGrabbedEntity(handedness: Handedness): Entity | undefined;
```

Parameters

handedness: Handedness

The hand to query.

Returns

Entity | undefined

\- The held entity or undefined if not holding anything.</td>
    </tr>
    <tr>
      <td>**grab(handedness, entity)**</td>
      <td>Commands the agent to pick up an entity.

Signature

```
grab(handedness: Handedness, entity: Entity): Promise<AgentGrabActionResult>;
```

Parameters

handedness: Handedness

The hand to pick up the entity with.

entity: Entity

The entity to grab. The entity must be grabbable.

Returns

Promise< [AgentGrabActionResult](/horizon-worlds/reference/2.0.0/avatar_ai_agent_agentgrabactionresult) >

\- A promise describing how the grabbing action ended.</td>
    </tr>
  </tbody>
</table>