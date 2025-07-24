# EntityTagMatchOperation Enum

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_entitytagmatchoperation)

Defines the valid matching operations that are available when using [getEntitiesWithTags()](/horizon-worlds/reference/2.0.0/core_world#getentitieswithtags) to find world entities.

## Signature

```
export declare enum EntityTagMatchOperation
```

## Enumeration Members

| Member | Value | Description |
| --- | --- | --- |
| HasAllExact | 1 | All of the sought tags must be present in an Entity's tags for that entity to be included in the result. The match must be exact. |
| HasAnyExact | 0 | A single match encountered in an Entity's tags results in that entity being included in the result. The match must be exact. |