# AgentGrabActionResult Enum

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/avatar_ai_agent_agentgrabactionresult)

The result of a request for an agent to pick up an entity.

## Signature

```
export declare enum AgentGrabActionResult
```

## Enumeration Members

| Member | Value | Description |
| --- | --- | --- |
| AlreadyHolding | 1 | The request failed because another entity is already being held. |
| InvalidEntity | 3 | The entity is not grabbable. |
| NotAllowed | 2 | The agent is not allowed to hold the entity. |
| Success | 0 | The entity was successfully picked up. |