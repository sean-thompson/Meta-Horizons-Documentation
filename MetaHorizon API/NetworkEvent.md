# NetworkEvent Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_networkevent)

Represents an event sent over a network. These events support any type of data that can be serialized through JSON.stringify().

## Signature

```
export declare class NetworkEvent<TPayload extends NetworkEventData = Record<string, never>>
```

## Remarks

When sent over the network, NetworkEvent outperforms [CodeBlockEvent](/horizon-worlds/reference/2.0.0/core_codeblockevent) because it doesn't use the legacy messaging system used by Code Block scripting.

  

For events sent between event listeners on the same client (locally), you can use [LocalEvent](/horizon-worlds/reference/2.0.0/core_localevent) .

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(name)**</td>
      <td>Creates a NetworkEvent with the specified name.

* * *

Signature

```
constructor(name: string);
```

Parameters

name: string

The name of the event.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**name**</td>
      <td>The name of the event.

Signature

```
name: string;
```</td>
    </tr>
  </tbody>
</table>