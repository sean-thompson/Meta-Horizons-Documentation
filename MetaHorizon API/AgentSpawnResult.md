# AgentSpawnResult Enum

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/avatar_ai_agent_agentspawnresult)

The result of a player spawn request

## Signature

```
export declare enum AgentSpawnResult
```

## Enumeration Members

| Member | Value | Description |
| --- | --- | --- |
| AlreadySpawned | 1 | This agent already has a player. |
| Error | 3 | An error has occured. |
| Success | 0 | The player was successfully spawned |
| WorldAtCapacity | 2 | There is no room in the world for an additional player. |