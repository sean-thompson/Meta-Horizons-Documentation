# LocalEvent Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_localevent)

Represents an event sent between TypeScript event listeners on the same client in Meta Horizon Worlds. These events support arbitrary data.

## Signature

```
export declare class LocalEvent<TPayload extends LocalEventData = Record<string, never>>
```

## Remarks

When sent between event listeners on the same client (locally), LocalEvent outperforms [CodeBlockEvent](/horizon-worlds/reference/2.0.0/core_codeblockevent) because it doesn't use the legacy messaging system used by Code Block scripting.

  

For events sent over a network, you can use [NetworkEvent](/horizon-worlds/reference/2.0.0/core_networkevent) .

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(name)**</td>
      <td>Creates a local event with the specified name.

* * *

Signature

```
constructor(name?: string);
```

Parameters

name: string *(Optional)* The name of the event.

Remarks

If a name is not provided, the event becomes unique and must be referenced by its object instance. This is useful if your event is used in an asset to avoid collision in a world.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**name**</td>
      <td>The name of the event. If a name is not provided, a randomly generated name is assigned.

Signature

```
name: string;
```</td>
    </tr>
  </tbody>
</table>