# Npc Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/npc_npc)

Extends *Entity* Represents an NPC with LLM-powered conversation capabilities that support audio and transcription.

## Signature

```
export declare class Npc extends Entity
```

## Remarks

Conversation functionality must be enabled before using conversation capabilities.

## Properties

<table>
  <tbody>
    <tr>
      <td>**conversation**

\[readonly\]</td>
      <td>The object that manages the conversation of the NPC.

Signature

```
readonly conversation: NpcConversation;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**isConversationEnabled()**</td>
      <td>Indicates whether conversation capabilities are enabled for the `Npc` object.

  

True if conversation is enabled; false otherwise.

Signature

```
isConversationEnabled(): boolean;
```

Returns

boolean</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>A string representation of the `Npc` object in the format `[Npc] id` where `id` is the identifier of the object.

Signature

```
toString(): string;
```

Returns

string</td>
    </tr>
  </tbody>
</table>