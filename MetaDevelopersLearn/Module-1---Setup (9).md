# Module 1 - Setup

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-analytics-tutorial/module-1-setup)

![Thumbnail of Chop 'N Pop World](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467985657_595263769678245_8393983042199091303_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=GnlaYKh9BzYQ7kNvwGLiTOB&_nc_oc=Admf8dvUBkEHje4mGcoaN51lIhKH_C8xZ73G3qqKIV8ds5iZTgA4GbpGqJrq3LCvP9U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=A9h9TjT5CdEQjpcJ8kjJ8g&oh=00_AfQNn2mbY7tzp8Pf1hs_6z1DDds6BHL5H2mrvj-_dk4_2w&oe=689BC1C9)

Important

This content is intended as a companion to the tutorial world of the same name, which you can access through the desktop editor. When you open the tutorial world, a copy is created for you to explore, and this page is opened so that you can follow along. For more information, see [Access Tutorial Worlds](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) .

Welcome to the in-world analytics tutorial, which covers the process and tools for adding in-world analytics to an existing world.

In-World Analytics enables creators to store data regarding events that occur within their worlds. Creators can then analyze this information to learn how players inhabit and use their creations. Using this captured data, creators can iterate and improve their worlds. **Note**: You can validate your analytics set-up in Edit mode using our validation tools, but in-world analytics data captured from the public only appears after your world has more than 10 Daily Active Users (DAU).

In-world analytics is comprised of the following components:

*   Data storage to store the data from events in the world

*   A TypeScript API to pass the data to the data store

These components are bundled in a starter kit, which is described later.

## Prerequisites **Note**: This tutorial assumes that you are familiar with the desktop editor, a desktop application for world building in Meta Horizon Worlds. If you are new to the desktop editor, you might want to start with the Build your first game tutorial. See [Module 1 - Build your first game](/horizon-worlds/learn/documentation/tutorial-worlds/build-your-first-game/module-1-build-your-first-game) .

## Learning objectives

In this tutorial, you learn the following:

*   How to add the TypeScript assets to simplify the integration of in-world analytics to your world

*   How to use TypeScript with the Analytics Manager class to store event data about your world

You can create a new world using the Chop ‘ N Pop Graveyard Bash Extended template to see a finished example.

## Learning pathways

You can explore this tutorial in either of the following ways:

*   Create a copy of the Chop ‘N Pop Graveyard Bash Analytics Completed Example world and explore the results.

*   Create a copy of the Chop ‘N Pop Graveyard Bash world and add the in-world analytics yourself. You can also complete the implementation examples in Module 2.

*   Add the Turbo Analytics library kit to your own world and explore from there. **Note:** You can also follow the steps in the remainder of this module to complete the addition and integration of Turbo Analytics into your own world. Some steps may not map exactly.

These pathways are described below.

## Learn by browsing Chop ‘N Pop Graveyard Bash Completed Example

You may have already created a copy of the Completed Example world. If you have not done so, open the Chop ‘N Pop Graveyard Bash Completed Example world under **Tutorials** in the Creation Home screen of the desktop editor. A copy is automatically created for you.

Then, you can follow along through the rest of the steps, as needed.

For more information on creating your own copy, see [Access Tutorial Worlds](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) .

## Learn by adding to Chop ‘N Pop Graveyard Bash

In this tutorial, you add in-world analytics to an existing game: Chop ‘N Pop Graveyard Bash. After you walk through the steps, you can explore the analytics integration in the next module.

Before you begin, please verify that you have access to your own copy of the Chop ‘N Pop: Graveyard Bash world. For more information, see [Access Tutorial Worlds](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) .

If this is your first time exploring Chop ‘N Pop Graveyard Bash, you should explore it through the [Chop ‘N Pop Graveyard Bash sample world tutorial](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-sample-world/module-1-setup) before this tutorial.

### Add the Turbo Analytics library

After you have created your own copy of the world or have opened your own world, please complete the following steps to set up the world for in-world analytics.

Meta has created a starter kit, Turbo Analytics, available in the public Asset Library that bundles the required components for in-world analytics.

To add the starter kit to the world from the desktop editor:

*   Enable the `horizon/analytics` API module through the Scripts panel.

*   Pull in the `Turbo` assets from the public assets in the Asset Library.

For more information, see [Using in-world Analytics](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/analytics/using-in-world-analytics/) .

In the Completed Example world, these entities are grouped together in the Hierarchy panel under a Text gizmo:

![Turbo imported in the world](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476862729_651374564067165_5825956647223440708_n.jpg?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=jUl-XJ9PpHIQ7kNvwGxYJbp&_nc_oc=AdmHGUNWW0-yJ5NFZzhWg8-8q_uPnhkFoKcCfPwq9sX9YL3HsiFENPZDdU1MoETxOj8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=A9h9TjT5CdEQjpcJ8kjJ8g&oh=00_AfTf8VTJ7dr6b0KBtT11v347_HiR3PXGcSC05Hlz_mqk8A&oe=689BADED)

## Turbo Analytics template

The above image displays the Turbo Analytics template, which includes the following entities:

| Entity Name | Description |
| --- | --- |
| TurboAnalytics.ts | This TypeScript script manages sending data from the world to the TypeScript API. |
| TurboAreaTrigger.ts | This TypeScript script can be attached to a TriggerGizmo entity in the world and configured to include the name of the area. The script captures AreaEnter and AreaExit analytics events when a player enters and exits the TriggerGizmo. |
| TurboDiscoveryMadeTrigger.ts | This TypeScript script can be added to a TriggerGizmo entity in the world, and configured to include the name of a discovery event. The script records DiscoveryMade analytics events when a player enters the TriggerGizmo. |
| Turbo Analytics Host | This Text gizmo entity is the attachment point for the TurboAnalytics script. It should be hidden at runtime by moving below the world or set to invisible. |

## Enable analytics logging

In-world analytics are a background activity that should have minimal impact on the player’s experience in a world. Since analytics messages are passed in the background, it can be challenging to know whether the analytics have been configured correctly.

To identify the events sent to the in-world analytics engine, you should enable in-world analytics logging during development and testing of analytics. **Note**: If you do not enable analytics logging, you cannot track if events are being sent to the Analytics API. If you do enable logging, you must remember to disable logging before publishing to the public.

To enable in-world analytics logging:

*   Open the `TurboAnalytics.ts` script in a script editor. This script contains the primary class for in-world analytics: `AnalyticsManager` and other related code.

*   Near the top of the file, change line 15 so that it reads as follows, which enables debug logging:
    
    ```
    export const TURBO_DEBUG =
     true; /** TODO (Creator): IMPORTANT!!! Set to False before Release **/
    ```
    

*   Locate the `onDebugTurboPlayerEvent()` function. Modify it as follows to also print the player and event to the console when an analytics message is sent to the in-world analytics API:
    
    ```
    onDebugTurboPlayerEvent(\_player: hz.Player, \_eventData: EventData, \_action: Action): void {
     console.log(`🚀 TURBO: Debugging Turbo Player Event: ${_player.name.get()}: ${Action[_action].toString()}`);
      }
    ```
    

*   Save your script.

*   In the desktop editor, click the **Console tab**. After the script has been recompiled and executed, click **Clear** to empty the console.

*   Preview the world. You should see some initial in-world analytics events being printed to the console.

## Adding a world data model

The information from our in-world analytics to guide improvements in the world. To manage tracking of improvements, it is a recommended practice to consolidate variables that allow us to update the balancing of the world into a single file.

Use these steps to create your own file for your world data model:

*   In the desktop editor, open the **Scripts panel**.

*   Click the **\+ icon** to create a new script.

*   Name the script: `GameConstants.ts` *   Open the `GameConstants.ts` script in your script editor.

*   Replace the entire contents of the script with the following:

```
export const GameConstants = {};
```

Save your script. This script is expanded in the next module.

## Checkpoint

This module provided an overview of in-world analytics, steps to add core libraries to your world, and the process to enable debugging and printing analytics events to the console in the desktop editor. You’ve also added a new script to use for storing modifiable variables for your world.

In the next module, you explore integrating the `AnalyticsManager.ts` script into the Chop ‘N Pop Graveyard Bash game logic, and recording events through the Analytics TypeScript API.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 