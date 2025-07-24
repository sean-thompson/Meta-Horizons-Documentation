# IPersistentStorageWorld Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_ipersistentstorageworld)

A persistent storage object, which contains a set of functions that interact with persistent variables.

## Signature

```
export interface IPersistentStorageWorld
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**fetchWorldVariableAsync(key)**</td>
      <td>Signature

```
fetchWorldVariableAsync<T extends PersistentSerializableState>(key: string): Promise<T | null>;
```

Parameters

key: string

Returns

Promise<T | null></td>
    </tr>
    <tr>
      <td>**getWorldCounter(key)**</td>
      <td>Signature

```
getWorldCounter(key: string): number;
```

Parameters

key: string

Returns

number</td>
    </tr>
    <tr>
      <td>**getWorldVariable(key)**</td>
      <td>Signature

```
getWorldVariable<T extends PersistentSerializableState>(key: string): T | null;
```

Parameters

key: string

Returns

T | null</td>
    </tr>
    <tr>
      <td>**incrementWorldCounterAsync(key, amount)**</td>
      <td>Signature

```
incrementWorldCounterAsync(key: string, amount: number): Promise<number>;
```

Parameters

key: string

amount: number

Returns

Promise<number></td>
    </tr>
    <tr>
      <td>**setWorldVariableAcrossAllInstancesAsync(key, value)**</td>
      <td>Signature

```
setWorldVariableAcrossAllInstancesAsync<T extends PersistentSerializableState>(key: string, value: T): Promise<T>;
```

Parameters

key: string

value: T

Returns

Promise<T></td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)