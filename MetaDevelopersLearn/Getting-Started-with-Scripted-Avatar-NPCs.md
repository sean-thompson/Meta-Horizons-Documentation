# Getting Started with Scripted Avatar NPCs

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/getting-started-with-scripted-avatar-npcs)

Scripted Avatar NPCs provide you with a method to craft NPCs that can interact with your players, enhance gameplay, and provide narrative context to your worlds regardless of your skill level or expertise.

## Prerequisites

*   Scripted Avatar NPCs are supported for TypeScript v2.0.0 or later.

## Known Limitations

*   Conversation features are not available.

*   Adding a Scripted Avatar NPC has the same performance impacts on your world as adding another player.
    
    *   **Tip**: If you are adding multiple NPCs to your world, you should consider spawning them in as needed.

*   Place the NPC gizmo on the ground of your world. Do not locate Scripted Avatar NPCs above or below the surface of the world.

## How to Get Started

To create a fully functioning Scripted Avatar NPC, you must build the following elements:

*   Create a Scripted Avatar NPC entity:
    
    *   Add NPC gizmo to your world.
    
    *   Click **Edit Avatar** to change appearance.
    
    *   Modify Scripted Avatar NPC properties as needed.
    
    *   **Checkpoint**: NPC exists as an entity in your world.
    
    *   See [Create Scripted Avatar NPC](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/create-scripted-avatar-npc) .

*   Add Navigation (if Scripted Avatar NPC is mobile in the world):
    
    *   Create a navigation profile for your NPC.
    
    *   Build navigation volumes in your world for the NPC to use.
    
    *   Assign these volumes to the profile used for your NPC.
    
    *   Assign the navigation profile to your NPC.
    
    *   Build behaviors in TypeScript for the NPC to maneuver through the navigation volume(s).
    
    *   **Checkpoint**: NPC has a navigation space in the world and uses it to move.
    
    *   See [Build Navigation for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/build-navigation-for-scripted-avatar-npcs) .

*   Script the NPC Controller (if Scripted Avatar NPC responds to the environment):
    
    *   Build TypeScript to manage NPC behaviors.
    
    *   Map TypeScript to APIs to drive behaviors.
    
    *   **Checkpoint**: NPC expresses behaviors in the world

*   Conversation (if Scripted Avatar NPC speaks to the player):
    
    *   **Note**: Not supported at this time.

*   Spawning and despawning:
    
    *   If your Scripted Avatar NPC is not spawned in at start, you can spawn and later despawn it at runtime through APIs.
    
    *   See [Spawning for Scripted Avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/spawning-for-scripted-avatar-npcs) .

### Managing performance

When you deploy or spawn a Scripted Avatar NPC, it consumes the same resources as adding another player. To assess performance:

*   Determine the maximum number of players that you can technically support in the world. Call this value `maxPlayerCount`.

*   Determine the number of Scripted Avatar NPCs you need for your world. Call this value `totalScriptedNPCs`.
    
    *   This figure should also include any Scripted Avatar NPCs that you intend to spawn.

*   Modify your world’s player settings:
    
    *   In the menu system, select **Horizon menu > Player Settings**.
    
    *   Set the value of **Maximum number of players** to `maxPlayerCount` \- `totalScriptedNPCs`.
    
    *   **Note**: This value represents the true number of human players who can participate in the world.

*   Into your world, add NPC gizmo instances for each of the `totalScriptedNPCs`.
    
    *   This should also include NPCs that you will later spawn through code.

*   Test performance of your world when you have `maxPlayerCount` players in it.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 