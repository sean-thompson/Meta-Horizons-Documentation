# World Streaming

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/asset-spawning/world-streaming)

World streaming is a Meta Horizon Worlds feature that provides an efficient approach to building and running large worlds. It lets you divide a large world (a parent world) into a set of smaller worlds (sublevels). At runtime, you don’t have to load the world all at once. Instead, you can stream each subworld into the parent world programmatically.

This approach provides tooling that lets you preview sublevels and configure them correctly within a parent world. It allows a team of world creators to work independently, where each developer works on a different sublevel. Sublevels are integrated into the parent world as they’re completed.

From a runtime perspective, this approach gives better load times than streaming in parts of the world using asset spawning. Sublevels can load two to three times faster due to leveraging cached global illumination (GI) information, and removing the cost of dynamically computing lighting during load.

This document details the procedure for dividing large Meta Horizon Worlds into multiple sub-levels.

## Benefits and limitations

The following section lists the benefits and limitations of the World Streaming feature.

### Benefits **Divide a world into smaller sublevels** Sublevels are separate worlds, which can each contain meshes, gizmos, scripts. You can preview and organize sublevels during world creation, and at runtime. You can dynamically stream sublevels in and out. **Faster load time** You’ll experience a two to three times improvement in world load time, versus regular asset spawning for worlds containing only imported meshes. Cached global illumination is leveraged to precompute mesh lighting in the cloud. This speeds up loading at runtime. **Note**: Meshes are lit based on the environment settings defined in the sublevel world. **Typescript APIs for setting and retrieving the state of sublevels at runtime** This allows you to create worlds in which sublevels load and unload according to the player’s actions. **Improved collaboration for groups of creators** Groups of creators can work independently on different sublevels, which may then be stitched together into a single large coherent experience.

### Limitations **Per-player world streaming is not supported** World streaming is client independent. Loading a sublevel loads it for every player simultaneously. **Multiple sublevels loaded at the same time will negatively impact performance** You should be wary of performance considerations when spawning in multiple sublevels at the same time. **Automated streaming based on player movement is not supported** You must use Typescript APIs to manually stream sublevels.

## World streaming vs asset spawning

World Streaming or [Asset Spawning](/horizon-worlds/learn/documentation/typescript/asset-spawning/introduction-to-asset-spawning/) are two approaches that you can use to spawn content into your world at runtime. Which approach you use depends on the following considerations. **Use world streaming if** *   You want to spawn large chunks of static content.

*   The content always spawns in the same location.

*   You want to optimize the load time and improve the lighting quality for your content. **Use asset spawning if** *   You want to spawn smaller chunks of content.

*   The content is dynamic, or it spawns at different locations each time.

Meta encourages you to consider these factors when choosing which approach to implement. In many cases, it’s likely that you might want to use both strategies in the same world to spawn different kinds of content. For example, you might use world streaming to spawn static parts of the world as the player traverses it, and then use asset spawning to spawn dynamic content on top of the sublevel.

## Example: Create a world with sublevels

You can learn about the workflow involved in creating a world with sublevels by following the steps in this example scenario.

### Create sublevel worlds.

*   In the Horizon Desktop Editor, create two new worlds called Sublevel1 and Sublevel2. Under **Choose how you’ll create**, select **Custom model imports**. 
    
    ![Image shows the world creation window with the 'custom model imports' option selected.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462507050_563224309548858_7735022226235344296_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=uWe757DMYzcQ7kNvwH-Ibbm&_nc_oc=AdmojD0mT3-PWdOievM4-O_3qED9uCqWhu25RuPJjvFknZV-Or87xJGj_xq3YBskMlY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfSoYdwwcZ7v4hOg4m_1kfqBHDZQBKib1Mxkzv6YMmodfw&oe=689B9D42) 

*   Place several pieces of recognizable geometry inside each world. For example, you could use green objects in Sublevel1, and red objects in Sublevel2. 
    
    ![Image shows an example of two worlds, one with green furniture and one with red furniture.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462629009_563224286215527_7331852403028520582_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=MqGbUQHEDu8Q7kNvwHuCQYW&_nc_oc=AdnI7-Zmdy3Gbevnu_2HTn5RZOzJ2t9PWuaKPTNftmk1jLrRisXPWdEmw3oe6qlfMCY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfRo0mLJ0WOVdzF69q5FXL7Tflepvy1WxyvkVBMbWF2XbQ&oe=689B9D27) 

*   In each world, create a new sublevel entity. 
    
    ![Image shows a dropdown menu with the 'Sublevel' option selected.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462369543_563224319548857_5410471249327829752_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=1R0DE7EEHjcQ7kNvwGkTwHH&_nc_oc=AdmDNeG_H3s3X652AnCHUpimuG0e0QnDdCvMxBBdah3fnJZTZQbOCWHLTIlA-d8EG-g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfS2FaVA6B6e8vlwwU5J3bgf-AgKFGtGxuBLq9IFmSpVDA&oe=689B9F16) 

*   Set the type of the sublevels to **Exclude**, and rename it to “Testing Only”.
    
      
    
      
    
    This informs the world that any entities that are children to this sublevel should be ignored when loading it into the parent world. Note that they still exist when you load the sublevel world directly. This allows you to add content that you can use to test sublevels in isolation, without worrying about it being included in the integrated version. 
    
    ![Image shows a Properties menu with the type set to Exclude.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462454490_563224282882194_1061395988203076613_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=S0JhG5TpF44Q7kNvwHSbA95&_nc_oc=AdnD4XKDpvX73PKRztKiNcP7hnzW5mnTgt-agBwOVALyL_PvM-7pH47q5YKryPLgmRw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfQOWmH75za1bTZja3RE-vlbuQ04CmUQWFh1c5N_PziP9g&oe=689B9956) 

*   Drag the default spawn point under this new sublevel entity in the hierarchy so it won’t be included when you load this sublevel into the parent world.

*   Publish both worlds, and be sure to turn off the setting **Visible to the public**.

### Create a parent world.

*   Create a new world called “Overworld”. Under **Choose how you’ll create**, select **Custom model imports**.

![Image shows the 'Create a World' window with the 'Custom Model Import' option selected.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462492910_563224332882189_5157749398908009325_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=Q7o-EKHjzvgQ7kNvwEX45qb&_nc_oc=Adl8VOuynpwJnE23XJKRWfE4XF-7PW8XfycrbJShk0kGq3sQ3OfojfnfOFlwlq0iFVc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfSJf2ADGkHSozvaV7_3KfZ0fKJtX3difJaOIGaAlcJFug&oe=689B9762)

### Add the sublevels.

*   Using the drop-down list, add the two sublevel worlds to the overworld.

![Image shows a drop-down menu with the 'Sublevel' option selected.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462463696_563224326215523_8369992740494252695_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=601z6Tw4eoYQ7kNvwHzc1OU&_nc_oc=AdmroH9WAXMQTDIxLCSHXJS6TB6rUnddFY8C5rhQovxDWZYxXOoAAO34qb9Mkc-uxKQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfRHwW-gkrjaAhD8MVsv2h66wXgZT5ZW3g1drxCehOFqmw&oe=689B94A7)

### Link the sublevels.

*   Select a sublevel object from the hierarchy.

*   In the property panel, ensure that the **Sublevel Type** is set to Deeplink.

![Image shows the 'Properties' menu with the 'Sublevel Type' set to Deeplink.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462466842_563224302882192_512977330414403837_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=6ZfXC5QOFWMQ7kNvwFzvinD&_nc_oc=AdlReSf2Y5S9-Nj5RsgGGS2GI5_8eov2X_94VY6HkkuUivWqiPzIwkD96gXysfaZTZg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfQnl44H2w7L-vwZ6B_yz12VZdmaYo-omnceszzRolGHiQ&oe=689B96E0)

*   Click on the thumbnail square.

*   Select one of the sublevels from the world picker dialog box.

![Image shows an example window where sublevels may be chosen.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462531591_563224366215519_3816575801335575806_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=ycV5O_Px4TwQ7kNvwE7DqeD&_nc_oc=AdkePv9LeMdTsVNyK4-Cxxwojt2nPog7pU5DjieFOZRhn1hBOqsqryzuyKoNEqGADcA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfTBZi9DVRF8RLtJTbluXXAo-Z6SXN_WZh6YD4Vc5FAZkg&oe=689BBBF3)

### Position the sublevels.

*   Select a sublevel in the scene hierarchy.

*   Using the transform handles, position the sublevel so you can easily see it turn on and off.

![Image shows a sublevel being placed into a scene.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462395401_563224316215524_2125350969875732958_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=Rc6HV4_VZNsQ7kNvwGWu2SZ&_nc_oc=AdnLbNQorVUJptyIIN2QX-kKxKlKD88axMxVVPIHJtGhfUg42xxC2Mq3t_eps-SPxr8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfRHxo6GxDUlkmJTyjfL9o5URsc8vnjK5pXhM-JEF00AmQ&oe=689BBFC5)

*   Repeat the preceding two steps for the other sublevel.

### Set the initial state on the sublevels.

*   In the **Properties** dialog, under **Sublevel Initial State**, try setting each of the initial sublevel states.
    
    *   Select **Active**, and the entities are loaded and become active.
    
    *   Select **Loaded**, and the entities are loaded, but are neither active nor visible.
    
    *   Select **Unloaded**, and no entities are loaded.

As you change the states, you’ll see the sublevel load and become active, and unload.

![Image shows the properties menu with the 'Sublevel Initial State' field highlighted.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462525127_563224322882190_3387601690689725349_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=IWt-UNuVgqgQ7kNvwFA27pF&_nc_oc=AdlqMCOyvwoQ7rsYcij2Xfqspr9Kh4wf4lEHIV3OLW423AB5t7bB4P4KJnApHz5mfkk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfSXxYc45sD1dHd-evMcD-gXJ3vVP5zynovRwziB-_Aruw&oe=689BA37F)

## Programmatically spawn and despawn the sublevels

Follow this procedure to configure the Desktop Editor to run the sample script. You can run the script to see the SublevelEntity API in action. The sample code demonstrates how to:

*   Get the current state of the sublevel (for example, loading).

*   Get the target state of the sublevel (for example, loaded).

*   Set the target state of the sublevel by using the following functions: [activate()](https://horizon.meta.com/resources/scripting-api/world_streaming.sublevelentity.activate.md/?api_version=2.0.0) Make the sublevel visible to users and start running scripts. [hide()](https://horizon.meta.com/resources/scripting-api/world_streaming.sublevelentity.hide.md/?api_version=2.0.0) Return an active sublevel back to the loaded state. [load()](https://horizon.meta.com/resources/scripting-api/world_streaming.sublevelentity.load.md/?api_version=2.0.0) Begin the process of loading a sublevel into memory, but don’t activate it yet. [pause()](https://horizon.meta.com/resources/scripting-api/world_streaming.sublevelentity.pause.md/?api_version=2.0.0) Temporarily pause the load of a sublevel. Loading a sublevel has an impact on performance, so you might want to temporarily pause a load at performance-critical times. Resume the load by calling load() again. [unload()](https://horizon.meta.com/resources/scripting-api/world_streaming.sublevelentity.unload.md/?api_version=2.0.0) Completely remove a sublevel from memory.

You can find the SublevelEntity class API in the [v2.0.0 world_streaming package](https://horizon.meta.com/resources/scripting-api/world_streaming.sublevelentity.md/?api_version=2.0.0) . This API is not supported in v1.0.0 of the Meta Horizon Worlds API.

### Preconditions

Follow these steps to configure the Desktop Editor for running the example script.

*   In the Desktop Editor, click the Scripts panel dropdown. 
    
    ![Image shows the icon for the dropdown menu.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462463689_563224329548856_8861115945399082503_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=92Wq27UX5rwQ7kNvwFg8LZ3&_nc_oc=Adkz9hT2ODwwNoOS1CpI8IWoCwk0GequqklZRIpzCPFpduhrSxvsq7c5Flkntfr1eqI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfQXH8ovAlFzVo1PVuC0xiMdpjYjHAIdMjybK6PXyuAn9w&oe=689BA579) 

*   When the Scripts panel appears, select the **Settings** icon. 
    
    ![Image shows a close-up of the settings icon.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462596018_563224369548852_1254548336609362418_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=56zOA-HAcC4Q7kNvwEOia8N&_nc_oc=AdmnPUMjp0LJCQJMTgz3l8c1UB3RJPFnA4CfkkYTbM9oNsTe7Q-DE0mwj3Y0_PKYO2E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfS2sQZfXUJFk1KVPN994dhdjQRzb85SpTENhlBIFbFExA&oe=689B9E58) 

*   Enable the **horizon/world_streaming** module. 
    
    ![Image shows the script settings menu with the 'horizon/world streaming' option enabled.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462429142_563224362882186_9097024643678864104_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=Eash1_tBMlsQ7kNvwGWo2M_&_nc_oc=Adn2vvTNXk4BrM9LWA2sQsygkTGK5snxH5VZwdaifmxr-sXWXN8EK-V20D9ZXXIOFmI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8hNhxmRg8IciWwMZ32m_IA&oh=00_AfQRsSDLJOFr8sPcOXtbXwHYEVbvDQ2Y8opklsCD5cy9Zw&oe=689BB32A) **Note**: You must have at least one script to enable a module.

### Example script

The following code demonstrates how to spawn and despawn sublevels at runtime.

```
import { Component, PropTypes, Entity, CodeBlockEvents } from 'horizon/core';
import { SublevelEntity } from 'horizon/world_streaming';


class TestSublevelAPI extends Component {
  static propsDefinition = {
    sublevel: {type: PropTypes.Entity},
    state: {type: 'number', default: 0}, // States 0 to 4 are:
                                         // Unloaded, Loaded, Active,
                                         // Pause, and Hide (Loaded).
  };


  start() {
    this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnPlayerEnterTrigger, async (player) => {
      var sublevel = this.props.sublevel?.as(SublevelEntity);
      var state = this.props.state;


      if (sublevel == null \|\| sublevel == undefined) {
        console.log("The sublevel entity was either null or invalid.")
        return;
      }

      console.log("Sublevel Trigger entered. Trying to set sublevel " + sublevel.toString() + " to " + state + ", current sublevel state is " + sublevel.currentState.get() + ", previous target sublevel state is " + sublevel.targetState.get());
      switch(state) {
        case 0: {
          sublevel.unload().then(() => {
            console.log("Sublevel " + sublevel?.toString() + " is now unloaded!");
          });
          break;
        }
        case 1: {
          sublevel.load().then(() => {
            console.log("Sublevel " + sublevel?.toString() + " is now loaded!");
          });
          break;
        }
        case 2: {
          sublevel.activate().then(() => {
            console.log("Sublevel " + sublevel?.toString() + " is now activated!");
          });
          break;
        }
        case 3: {
          sublevel.pause().then(() => {
            console.log("Sublevel " + sublevel?.toString() + " is now paused!");
          });
          break;
        }
        case 4: {
          sublevel.hide().then(() => {
            console.log("Sublevel " + sublevel?.toString() + " is now hidden!");
          });
          break;
        }
        default: {
          console.log("Invalid/Unexpected sublevel state # given: " + state);
          // unexpected state
          break;
        }
      }
    });
  }
}
Component.register(TestSublevelAPI);
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 