# NpcEvents Variable

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/npc_npcevents)

A set of events that are triggered by various types of [NPC](/horizon-worlds/reference/2.0.0/npc_npc) engagement.

## Signature

```
NpcEvents: {
    OnNpcEngagementChanged: NetworkEvent<{
        phase: NpcEngagementPhase;
        playerId: number;
    }>;
    OnNpcStartedSpeaking: NetworkEvent<Record<string, never>>;
    OnNpcStoppedSpeaking: NetworkEvent<Record<string, never>>;
    OnNpcVisemeChanged: NetworkEvent<{
        viseme: Viseme;
    }>;
    OnNpcEmoteStart: NetworkEvent<{
        emote: string;
    }>;
    OnNpcEmoteStop: NetworkEvent<{
        emote: string;
    }>;
    OnNpcError: NetworkEvent<{
        category: NpcErrorCategory;
        errorCode: number;
        errorMessage: string;
        playerId: number;
    }>;
}
```