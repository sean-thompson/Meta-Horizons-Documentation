# PersistentSerializableState type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_persistentserializablestate)

A state that can persist across sessions within persistent variables for each player. Used with the [getPlayerVariable](/horizon-worlds/reference/2.0.0/core_world#persistentstorage) and [setPlayerVariable](/horizon-worlds/reference/2.0.0/core_world#persistentstorage) methods.

## Signature

```
export declare type PersistentSerializableState = {
    [key: string]: PersistentSerializableState;
} | PersistentSerializableState[] | PersistentSerializableStateNode;
```

## References

[PersistentSerializableState](/horizon-worlds/reference/2.0.0/core_persistentserializablestate)