# IPersistentStorage Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_ipersistentstorage)

A persistent storage object, which contains a set of functions that interact with player variables.

  

For information about using player variables, see the [Persistent Variables](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/object-type-persistent-variables) guide.

## Signature

```
export interface IPersistentStorage
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**getPlayerVariable(player, key)**</td>
      <td>Gets the value of a persistent player variable.

Signature

```
getPlayerVariable<T extends PersistentSerializableState = number>(player: Player, key: string): T extends number ? T : T | null;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player for whom to get the value.

key: string

The name of the variable to get.

Returns

T extends number ? T : T | null

The value of the variable as some PersistentSerializableState, defaulting to number.</td>
    </tr>
    <tr>
      <td>**setPlayerVariable(player, key, value)**</td>
      <td>Sets a persistent player variable

Signature

```
setPlayerVariable<T extends PersistentSerializableState>(player: Player, key: string, value: T): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player for whom to set the value.

key: string

The name of the variable to set.

value: T

The value to assign to the variable.

Returns

void</td>
    </tr>
  </tbody>
</table>