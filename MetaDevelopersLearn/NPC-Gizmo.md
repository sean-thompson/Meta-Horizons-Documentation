# NPC Gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-gizmo)

You can add the NPC gizmo to your world to create non-player characters in your world. These characters can do things like:

*   Navigate through your world

*   Grab and use other objects

*   Spawn and despawn as needed

*   Interact with players via [AI Speech powered NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/ai-speech-npcs/ai-speech-npcs-overview) You can also edit the appearance of the NPC avatar through a web-based editor, similar to the one used for editing your personal profile.

## NPC Gizmo Properties

The following properties are available when you add the NPC gizmo to your world:

| Property | Description |
| --- | --- |
| Character Name | The display name of your avatar NPC. This name appears in a name tag when the avatar is in a world. |
| Spawn on Start | Set to true to spawn the NPC into the world when the world starts. Otherwise, the NPC must be spawned in using TypeScript. For more information, see Spawning for Scripted Avatar NPCs. |
| Edit Avatar | Click this button to edit the avatar’s appearance. See below. |
| Refresh | Click this button after you have edited your avatar’s appearance to refresh it in this world. See below. |

## Avatar Appearance

Through an external web-based interface, you can modify the body, face, clothing, and other aspects of your avatar’s personal appearance to create a unique character for your world.

In the Properties panel, click the **Edit Avatar** button.

After editing and saving your changes through the web interface, click the **Refresh button** to update the avatar in the local world.

For more information, see [Edit Scripted Avatar NPC Appearance](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/edit-scripted-avatar-npc-appearance) .

## Scripted Behaviors

Through TypeScript, you can define scripted behaviors for your avatar NPC. For more information, see [API Overview for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/api-overview-for-scripted-avatar-npcs) .

## Conversations

Creators can leverage the power of an embodied [NPC](/horizon-worlds/learn/documentation/desktop-editor/npcs/npcs) to create engaging, interactive experiences in their worlds. These NPCs are typically backed by an LLM. This could include characters that respond to user input, dynamic storylines, and more. Below are some of the use cases:

*   When it comes to Typescript API, this is similar to the [Conversation Gizmo’s API](/horizon-worlds/learn/documentation/desktop-editor/npcs/llm-gizmo-api-reference) and they share common features.
    

*   Managing NPC Engagement with the players: The current APIs allow creators to enable the AEL system engage or disengage facilitating interaction LLM. Creators can pass in items of interest to the NPC to improve NPC’s interactions, animation and responses.
    

*   Managing Voice Interactions: The current APIs provide creators with extensive control over the LLM’s voice interactions. Creators can interrupt the LLM, or instruct it to speak a specific text. This level of control allows creators to dictate when and how the LLM characters interact with users, enabling more nuanced and responsive interactions.
    

*   Real-Time Subtitles: During NPC conversations, creators can display real-time subtitles. This enhances accessibility and ensures that all users can follow along with the dialogue.
    

*   World interactions: Creators can parse LLM responses and use them to trigger actions within the world. This could include changing the environment, advancing a storyline, or triggering character behaviors.
    

*   World-Aware Responses: Creators can pass world information to the LLM using apis like setDirection or setPerception, which allows the LLM to then provide responses based on that knowledge. This allows for context-aware interactions, making the LLM characters feel more integrated into the world.
    

*   These APIs unlock a new level of interactivity and immersion for creators. They allow you to set up your own LLM backed embodied characters to enhance your worlds. This means you can design characters that can understand and respond to user commands, interact with the world context, and even initiate actions based on their responses. This greatly expands the possibilities for interactive storytelling and gameplay, making the worlds created by you more engaging and dynamic.
    

*   This API is based on the Conversation Gizmo and continues to provide most of the functionality of Conversation Gizmo. However, the Conversation Gizmo doesn’t support the NPC platform’s new NPC embodiment system (AEL). The NPC Gizmo works with the new platform and is the ultimate tool for generating NPCs in Horizon.
    

### Declaration

Codeblock Events:

```
export const ExperimentalCodeBlockEvents = {
 /*
   * Triggered when the NPC disengages from the player.
   */
  OnNpcDisengagePlayer: new CodeBlockEvent<[player: Player, npc: Entity]>(
    'OnNpcDisengagePlayer',
    [PropTypes.Player, PropTypes.Entity],
  ),

  /*
   * Triggered when the NPC engages with the player.
   */
  OnNpcEngagePlayer: new CodeBlockEvent<[player: Player, pc: Entity]>(
    'OnNpcEngagePlayer',
    [PropTypes.Player, PropTypes.Entity],
  ),

  /*
   * Triggered when the NPC's engagement phase with player changes.
   */
  OnNpcEngagementPhaseChangedEvent: new CodeBlockEvent<
    [npc: Entity, phase: NPCEngagementPhase]
  >('OnNpcEngagementPhaseChanged', [PropTypes.Entity, PropTypes.Number]),

  /*
   * This event is raised when the player speaking to LLM's mic level changes
   */
  OnPlayerMicLevelUpdate: new CodeBlockEvent<
    [player: Player, micLevel: number]
  >('OnInternalOnlyPlayerMicLevelUpdate', [PropTypes.Player, PropTypes.Number]),
};

/**
 * Represents an AI NPC's engagement phase with the user.
 * @privateRemarks
 * Must remain in sync with AelEngagementPhase enum in AelAPIEnums.cs AND
 * NPCEngagementPhase in NpcEngagementPhaseChangedEvent.cs
 */
export enum NPCEngagementPhase {
  /**
   * The NPC is idle.
   */
  NPCIdle = 0,

  /**
   * The npc is listening to the user.
   */
  NPCListening = 1,

  /**
   * The npcis about to respond to the user.
   */
  NPCReacting = 2,

  /**
   * The npcis speaking to the user.
   */
  NPCResponding = 3,

  /**
   * The npcfinished speaking and is yielding to the user.
   */
  NPCYielding = 4,

  /**
   * The npcis idle and is still focused on waiting for the user.
   */
  NPCFocusedIdle = 5,
}
```

### APIs:

```
/**
 * An AI NPC gizmo, which manages interactions between an LLM powered NPC and players.
 */
export class NPCGizmo extends Entity {
  /**
   * Creates a human-readable representation of the NPCGizmo object.
   * @returns A string representation of the NPCGizmo object.
   */
  override toString() {
    return `[NPCGizmo] (${this.id})`;
  }

/**
   * Request the NPC to add the player to the list of its recognized players.
   *
   * @param player - The player object to be added.
   */
  addRecognizedPlayer(player: Player) {
    bridgeInstance.invoke(BridgeMethod.AddRecognizedPlayer, this, player);
  }

  /**
   * Request the NPC to remove the player from the list of its recognized players.
   *
   * @param player - The player object to be removed.
   */
  removeRecognizedPlayer(player: Player) {
    bridgeInstance.invoke(BridgeMethod.RemoveRecognizedPlayer, this, player);
  }

  /**
   * Request the NPC to remove all the players from the list of its recognized players.
   */
  removeAllRecognizedPlayers() {
    bridgeInstance.invoke(BridgeMethod.RemoveAllRecognizedPlayers, this);
  }

  /**
   * The player entity that represents the NPC.
   */
  npcPlayer: ReadableHorizonProperty<Player | null> = {
    get: () => {
      return bridgeInstance.invoke(BridgeMethod.GetNPCPlayer, this);
    },
  };

   /**
   * Adds an item to the list of items of interest for the npc.
   * @param item - The item to add.
   */
  addItemOfInterest(item: Entity) {
    bridgeInstance.invoke(
      BridgeMethod.NPCAddItemOfInterest,
      this,
      item,
    );
  }

  /**
   * Removes an item to the list of items of interest for the AI npc.
   * @param item- The item to remove.
   */
  removeItemOfInterest(item: Entity) {
    bridgeInstance.invoke(BridgeMethod.NPCRemoveItemOfInterest, this, item);
  }
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 