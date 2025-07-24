# NPCs Overview

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/npcs)

Important

Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs) ! As a member, you gain:

*   Access to monetization opportunities including monthly bonuses, in-world purchases and competition cash prizes.

*   Helpful resources including educational content, technical support and a collaborative creator community.

Important

The desktop editor is in early access and we need your feedback! To report bugs, go to the main menu and select **Report a problem**. To give us feedback, select **Help us improve** from the main menu.

A Non-Player Character (NPC) is a computer-controlled character in a Meta Horizon Worlds world. An example of an NPC could be a monster that patrols the hallways of a haunted house as an enemy for the player. When the player encounters this NPC, or makes contact with them, the game ends. Worlds creators can add NPCs for a variety of purposes. These include:

*   To provide information or quests to the player.

*   To serve as enemies or obstacles for the player to overcome.

*   To sell goods and services.

*   To engage the player in conversation.

*   To add to the game’s atmosphere and immersion.

NPCs can range from simple [scripted characters](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/getting-started-with-scripted-avatar-npcs) , to complex [AI-driven characters](/horizon-worlds/learn/documentation/desktop-editor/npcs/ai-speech-npcs/ai-speech-npcs-overview) that learn and adapt to the player’s actions.

## How to spawn a stock NPC

You can spawn a stock NPC asset into your scene from the [Public Asset Library](/horizon-worlds/learn/documentation/desktop-editor/assets/public-asset-library) by clicking the **Asset Library** drop-down, and then selecting **Interactive**. The stock NPC characters appear, ready for you to select one to spawn into your scene.

![You can spawn stock npc characters into your scene by using the public asset library](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/469635362_606945868510035_635187677289325851_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=IlwjDsUJ4XoQ7kNvwFNxIP_&_nc_oc=AdnnKDcMCCu3hKDYaFuy_nSlkorwqHdRAxCug7EzbU1s2jeftIqFP79CJyW99WMw4KE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=_RkdHsi1iw0R8LXvil95wQ&oh=00_AfTKKz-5xb8A6QYaAe4YCTDWYeeBaPCJH-gPD5bpjW0KKA&oe=689BA03B) **Note:** You can use the [NavMesh API](https://horizon.meta.com/resources/scripting-api/navmesh.md/?api_version=2.0.0) to script NPC character movement so they can move automatically through your world. For more information, see [NPC Scripts](/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-scripts/) .

## Types of stock NPCs

There are five types of stock NPC characters that you can spawn into your scene, according to your needs. Each NPC character includes several animations that you can trigger.

| Name | Type | Animations |
| --- | --- | --- |
| Robot | Utility, Environmental | - Idle bobbing- Floating walk- Welcome wave- Directional point- Celebration |
| Chicken | Environmental | - Idle breathing- Idle look around- Idle pecking- Walking- Walking with pecking |
| Android | Utility, Storyteller | - Idle- Walking- Welcome wave- Celebration- Yes- No- Listening |
| Skeleton | Antagonist | - Idle- Walk- Aggressive/scary walk- Taunting roar- Hit reaction- Death |
| Zombie | Antagonist | - Idle/walk- Aggressive/scary walk- Taunting roar- Hit reaction- Death |
| Mascot | Antagonist | - Idle- Walk- Run- Attack- Hit- Death- Welcome- Taunt- Celebrate- Directional Look |
| Pineapple | Ally | - Idle- Walk- Run- Attack- Hit- Death- Welcome- Taunt- Celebrate- Directional Look |
| Samurai | Ally | - Idle- Walk- Run- Attack- Hit- Death- Welcome- Taunt- Directional Look |
| Toaster | Ally | - Idle- Walk- Run- Attack- Hit- Death- Welcome- Taunt- Celebrate- Directional Look |
| Ice Cream Character | Ally | - Idle- Walk- Run- Attack- Hit- Death- Welcome- Taunt- Celebrate- Directional Look |
| Zombie Female | Antagonist | - Walk- Run- Attack- Hit- Death- Welcome- Taunt- Directional Look |
| Skeleton Mage | Antagonist | - Walk- Run- Attack- Hit- Death- Welcome- Taunt- Directional Look |
| Henchman | Antagonist | - Walk- Run- Attack- Hit- Death- Welcome- Taunt- Directional Look |

## NPC character archetypes

NPC behavior is controlled using a combination of AI, and software design patterns like [Singletons](https://en.wikipedia.org/wiki/Singleton_pattern) . This approach allows NPCs to fulfill a thematic character type. **Note:** Most NPC behavior is controlled using AI.

| NPC Type | Description |
| --- | --- |
| Utility | Performs basic functions to move a narrative or game experience forward. For example, Quest lines, buying, selling, and trading items, or directing the player to do something. Utility NPCs can move around an environment and identify specific things. Utility NPCs support scripting. |
| Storyteller | Similar to the AI Agent. Storyteller NPCs are conversationally driven. Storyteller NPCs operate within specific guidelines to move a narrative forward, but with a comprehensive world understanding and context, including the game state. |
| Antagonist | Enemy NPC characters. Antagonist NPCs have the ability to move, fight, and obstruct the player from accomplishing an objective. You can add AI to control this character archetype to add more personality, and to add a higher level of decision-making ability. |
| Ally | Friendly NPC characters. Ally NPC characters are aligned with the player’s objective. Ally NPC characters can operate on something in the scene. They can follow the player, and hide from the player. |

## Simple groups

You can group NPC assets according to the way you use them.

### Shared context

Shared context NPCs all share the same understanding of the world, including an understanding of the current dynamic context. Shared context NPCs independently respond to world and player stimuli. Shared context NPCs all use AI to control responses to the shared stimuli.

### Antagonistic

Antagonistic NPCs all have knowledge of the existence of the other antagonistic NPC characters in the world. All antagonistic NPC characters are in direct opposition to each other. They have opinions about one another. This dynamic drives conversations and decisions. As an example, consider the scenario where the player has to convince a jury of antagonistic NPC characters by using various persuasion techniques.

### Complex

Complex NPCs combine simple NPCs with complex AI driven NPCs. For example, consider an AI-driven storyteller NPC commanding a group of simple NPCs. You can use this approach to give the simple NPCs complex, interesting behaviors.

### Overseer

Overseer NPCs are AI-driven observers. They can command simpler NPCs based on their personality and a set of corresponding strategies. The controlled NPCs are closer to simple bots. For example, zombies or minions. Overseer NPCs work in opposition to the player to accomplish a specific goal.

### Persistent relationships

Persistent relationship NPCs have memory of repeat visits to the world by the player, and potentially by other players. Persistent relationship NPCs can develop over multiple sessions. Each persistent relationship NPC is driven by its own AI.

## Sample NPC scripts

You can explore the NPC Examples tutorial world documentation to see how NPCs can be added and function in a world. Learn to make NPCs interactive, animate behaviors, or create enemies by referencing the NPC example world and the [NPC Scripts](/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-scripts) page.

## What’s Next?

*   [NPCs Gizmo](/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-gizmo)
    
     provides an overview of the NPC Gizmo, which is a gizmo that allows you to spawn NPCs into your world.
    

*   [Getting started with scripted avatar NPCs](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/getting-started-with-scripted-avatar-npcs)
    
     provides an overview of getting started with scripted NPCs.
    

*   [API Overview](/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/api-overview-for-scripted-avatar-npcs)
    
     provides an overview of the APIs available for scripted avatars like locomotion and spawning and despawning.
    

*   [AI Speech NPCs Overview](/horizon-worlds/learn/documentation/desktop-editor/npcs/ai-speech-npcs/ai-speech-npcs-overview)
    
     provides an overview of getting started with AI Speech NPCs.
    

*   [NPC scripts](/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-scripts)
    
     provide example scripts to use for animating your NPCs and giving them functionallity to interact with players in your world.
    

*   [Setting up NPCs with navigation](/horizon-worlds/learn/documentation/desktop-editor/npcs/setting-up-npcs-with-navigation)
    
     is a walkthrough of the NPC Sample world. This walkthrough provides information on adding NPCs to your world, attaching scripts, playing animations and configuring and enabling locomotion navigation.
    

*   [Navigation mesh generation](/horizon-worlds/learn/documentation/desktop-editor/npcs/navigation-mesh-generation)
    
     provides navigation meshes for defining walkable areas of an environment. Horizon includes World Builder tools and APIs that use navigation meshes to determine the areas of your world that NPCs can access, and the paths they can use to get there. With World Builder tools, you can set up, create, and update your meshes. You can then use the NavMesh TypeScript APIs to create scripts that retrieve navigation path calculations for your NPCs.
    

*   [Nav mesh agents](/horizon-worlds/learn/documentation/desktop-editor/npcs/nav-mesh-agents)
    
     allows you to create agents that autonomously navigate through a world avoiding obstacles, guided by navigation meshes. Agents can be simple, like a primitive object or complex, like a premade NPC asset.
    

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 