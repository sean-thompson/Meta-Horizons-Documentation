# AI Speech NPCs Overview

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/ai-speech-npcs/ai-speech-npcs-overview)

This guide will walk you through the process of creating an AI speech NPC. AI speech NPCs are AI-powered characters that can interact with players in a variety of ways. They are designed to be engaging, responsive, and unpredictable, making them a great addition to any game or application. In this guide, we’ll cover the basics of creating a generative NPC, including how to set up the NPCs background and implement it into your created world. First lets go over the types of NPCs.

## Types of NPCs

There are three categories of NPCs, each with its own distinct functionality:

### Stock NPC Assets

Stock NPCs can be found in the asset library under the interactive section. These NPCs are high fidelity and have expressive animations that can be controlled through scripts. However, they do not have AI Speech capabilities. Check the NPC Examples world under the Tutorial Worlds section of Creation Home to see examples of stock NPCs in action.

### NPC Gizmo: Horizon Avatar (Body Only)

The NPC Gizmo can be configured so it displays like a Horizon avatar. This avatar can be customized and scripts can be added to add behaviors like jumping and navigating around a world. Creators can also play pre-recorded audio clips along with these NPCs. You can learn more in the Scripted Avatar NPC tutorial world.

### NPC Gizmo: AI Speech (Voice Only)

The NPC Gizmo can be configured so it can speak as an AI character. This AI Speech can be configured in Character Builder, and is accessible from the **Edit Character** button. Currently, NPCs configured configured for AI Speech need scripts to trigger speech.

## Prerequisites

To create an AI speech NPC you’ll need to have created a world in the Horizon Desktop Editor.

## Set up an AI Speech NPC

To create and configure an NPC, use the following process:

*   In your world, open the **Gizmos** menu and drag in a NPC gizmo. You can use the search field if the gizmo is not currently visible.

*   Once the NPC has been added to your world, select it to open the NPC properties panel.

*   In the properties panel, you can configure various settings for your NPC. To make your created NPC an AI speech NPC set the **NPC Type** to **AI Speech (Voice Only)**. 
    
    ![Horizon NPCs AI Character property](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/518047246_763034862901134_3877317073927183006_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=OJOOWi43o-wQ7kNvwHXvh5B&_nc_oc=AdkJfN3JEs_XVfLidsccKIyssCHvCEqLvS4szdYJ9-PY-ZFklj8dWHdsvA79_qzDl6g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e9RglUYeABCSM1dCN530MQ&oh=00_AfQota3PLKsNgLlXq4nyvHHMo55hec9SaPv9xzyzruZ9QA&oe=689B87CB) 

*   After setting the **NPC Type** property to **AI Speech (Voice Only)**, you can select the **Edit Character** button to open the **Character Builder** window.

*   In the character builder window, you can give your NPC a name. Then click **Create**. 
    
    ![Character Builder Window](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/499540153_749732620898025_6090876886713937585_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=o8CYoIzUFhQQ7kNvwHlggpw&_nc_oc=Adk4y3FQ7DjM1QR4VmX_n2UqfXqXiCCOLprj8FLgIDfpTpcHs30P6PdllUrOtQmJV_w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e9RglUYeABCSM1dCN530MQ&oh=00_AfRJnviC-3A9pk9NNUuQx821cMZA4qR55uYiO9Z5ER5OMQ&oe=689BA4A3) 

*   Once your character is named, you can give your character a backstory. For more information about adding a backstory to your character, check the Backstory section.

*   After establishing the character’s backstory, select the **Voice and Speech** tab. Try testing some of the preset voices, once you find a voice you like for your character, select it and press **Save**.

*   Currently, scripting is required for your created NPC to speak. In your NPC’s select **Attach script** then, **Create new script** and name your script.

*   Once your script is named, click **Create and attach** to attach it to your NPC. Once attached, you can select the script in your NPC’s property panel, click the three dots, then select **Edit script**. 
    
    ![Character NPC edit script](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/499487252_749732607564693_7391081087052432134_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=R3opqoVb82QQ7kNvwGPVcKT&_nc_oc=AdloEqBlTM1yQwnLzpMg3wud5eFj-Re8rPBesnPGTnBEBRui8nizrpxG1IdT1Dho3Is&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e9RglUYeABCSM1dCN530MQ&oh=00_AfS1eGfsqPkcMczhPMUxNeAnZFiGeoQabWpucH6dRtCHtw&oe=689B8B9F) 

*   Your newly created script will open in your linked code editor. This new scripts default behavior will be speaking when the world initially starts. `elicitResponse()` takes an instruction for the NPC to respond to. You can find more examples of script NPCs in the NPC section of the asset library and in the sample script below.

*   Next, select **Build** \> **Gizmo** and drag out a **Trigger Zone** gizmo. Reposition and scale the gizmo so that it encompasses the NPC’s spawn point. This will ensure the `OnPlayerEnterTrigger` event is dispatched any time your player spawns in the world.

*   Select your NPC in the hierarchy. Go to the script property panel and point the Trigger property at the **Trigger Zone** gizmo.

*   Click the **Play** button to enter preview mode. You should hear your NPC speak shortly after spawning in the world.

### Sample NPC Script

The following is a sample script that configures an AI Speech NPC to introduce itself when a player enters the trigger.

```
import { CodeBlockEvents, Component, Player, PropTypes, TriggerGizmo } from 'horizon/core';
import { Npc } from 'horizon/npc';


class NPCScript extends Component<typeof NPCScript>{
  static propsDefinition = {
    trigger: { type: PropTypes.Entity },
  };


  start() {
    // Configures the NPC to introduce itself when a player enters the trigger.
    // For more details and examples go to:
    // https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/ai-speech-npcs/ai-speech-npcs-overview
    if (this.props.trigger!) {
      const trigger = this.props.trigger!.as(TriggerGizmo);
      const npc = this.entity.as(Npc);
      if (npc.isConversationEnabled()) {
        this.connectCodeBlockEvent(trigger, CodeBlockEvents.OnPlayerEnterTrigger, (player: Player) => {
          npc.conversation!.elicitResponse('Introduce yourself to player');
        });
      } else {
        console.error('NPC does not have conversation enabled. Please enable conversation in the NPC Gizmo.');
      }
    } else {
      console.error('Trigger property is not set. Please specify the trigger zone you want to trigger the NPC.');
    }
  }
}
Component.register(NPCScript);
```

The following sections will cover the various settings you can configure and how they impact the performance of your AI speech NPC.

### Backstory

The NPCs backstory should be a condensed version of the character that includes core personality traits. It shapes your character’s conversation with players and contains its key personality traits. The NPC’s backstory is included in its entirety in the prompt for the AI Speech NPC, so it’s recommended that you keep it simple. Too much detail in the backstory has been shown to water down the character’s performance rather than reinforce it, after a certain threshold.

The following is an example of an effective backstory prompt:

Denu is a small, shy Brown-banded Snail with a big heart and a strong sense of self. Despite being timid, Denu is fiercely loyal and determined to make the world a better place. With a passion for kindness, empathy, and environmental protection, Denu embarks on a journey to explore new places and help those in need.

Key Traits -Compassionate: Always willing to lend a listening ear or a helping foot to those in need. -Brave and Determined: Never backing down from a challenge, despite being shy and vulnerable. -Persevering: Possessing unique abilities such as perseverance, patience, and strength, allowing Denu to overcome obstacles and achieve goals. -Environmentally Conscious: Deeply committed to protecting the environment and preserving the beauty of nature.

### Voice and Speech

Voice is how your NPC sounds when speaking. There is a collection of preset voices that you can choose from when creating your NPC. You can hear a sample by clicking the speaker icon. You can hear specific lines of text by typing them into Voice Testing and clicking the play icon. You can use the **Speed** and **Pitch** sliders to fine tune your NPC’s voice.

![Voice and Speech window](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/499613797_749732614231359_4357326916385793980_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=OWzjRMwP0koQ7kNvwFYOPma&_nc_oc=AdmLUZ1YWY6RbJDUfGzdR_IYtiV58cU0DMnQ0YOrSZgzaKACkLaWCc3RM4wZ6Ij_tb4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e9RglUYeABCSM1dCN530MQ&oh=00_AfQ9s0MxAwxB8OsOM8ikppNvqp4w1YAuhPjpI460qstVrQ&oe=689B9A43)

### Conversation

The conversation panel allows you to test responses and emotional indicators from your created NPC. You can type a message into the **Message** field and click send to see how the character would respond.

When testing conversation responses, its important to note that the character has memory - past messages and responses sent to the NPC will influence what the character says. If you’d like to erase the message history click the **Reset Session** button.

![AI speech conversation panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506473468_749732610898026_8897556885164692705_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZpgTyiw6ej8Q7kNvwEJBGDW&_nc_oc=AdmUFm0cKa7YxemuDbUXn5ujg9FQZPbGf9ph8RsNY1GLEqdXHiPyoqNc0guwDxVBDSc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e9RglUYeABCSM1dCN530MQ&oh=00_AfTLgK8TfAgsfBLNKyShQxsGOrOwzKnK54l5J9t2x5NG0Q&oe=689BB292)

## Events

There are several events that you can take advantage of with your NPC. These events give you the opportunity to give some partial embodiment to your NPC. All NPC events are accessible through the NpcEvents object that can be subscribed to with NetworkEvent.

*   **OnNpcEngagementChanged**
    
     \- Triggered when an NPC goes through phases of a conversation. This provides the following engagement states:
    
    *   **Idle**
        
         \- The NPC is idle and can start a conversation anytime. No user is engaged yet. New instructions can be processed by the NPC.
    
    *   **Listening**
        
         \- The NPC is listening to the user. Listening to the user isn’t currently supported.
    
    *   **Reacting**
        
         \- The NPC is processing input and formulating a response based on instructions from `NpcConversation.elicitResponse()` method.
    
    *   **Yielding**
        
         \- The NPC finished speaking and is waiting for further instructions. The {@linkNpcAttentionTarget} is still engaged. The NPC can process new instructions.
    
    *   **Focused Idle**
        
         \- The NPC is idle and can process new instructions. The {@linkNpcAttentionTarget} is still engaged with the NPC.

*   **OnNpcVisemeChanged**
    
     \- Provides the mouth shapes that should be shown while the NPC is speaking. This is great for custom facial animations. You can learn more about Visemes in the Viseme Reference

*   **OnEmoteStart**
    
     \- Triggered when an NPC wants to show an emotion or trigger a quick emote.

*   **OnEmoteStop**
    
     \- Triggered when an emotion or animation state ends.

*   **OnNpcError**
    
     \- Triggered when the NPC experiences an error during a conversation

### Connecting Events

The following is a sample of connecting events together for your created NPC:

```
// Handles grabbing and releasing an item as well as adding the item to Npc's contextual awareness
class NpcEventExample extends Component<typeof NpcGrabbableItem> {
  static propsDefinition = {
    itemName: { type: PropTypes.String },
    npc: { type: PropTypes.Entity },
  };

  // Stored data
  private npc!: Npc; // TODO: Make Multiple
  private contextKey: string = "";
  public isHolding: boolean = false;
  public itemName: string = "";

  start() {
    // Cache Props
    this.grabbable = this.entity.as(GrabbableEntity);
    this.npc = this.props.npc!.as(Npc);

    this.connectNetworkEvent(this.npc, NpcEvents.OnNpcStartedSpeaking, () => {
      console.log("OnNpcStartedSpeaking");
    });
    this.connectNetworkEvent(this.npc, NpcEvents.OnNpcStoppedSpeaking, () => {
      console.log("OnNpcStoppedSpeaking");
    });
  }
}
Component.register(NpcEventExample );
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 