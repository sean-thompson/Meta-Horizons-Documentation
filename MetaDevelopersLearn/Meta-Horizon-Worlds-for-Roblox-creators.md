# Meta Horizon Worlds for Roblox creators

[source](https://developers.meta.com/horizon-worlds/learn/documentation/get-started/meta-horizon-worlds-for-roblox-creators)

This article provides information to help experienced Roblox creators get started with Meta Horizon Worlds, including basic UI orientation, conceptual comparisons, and key differences between the two platforms.

## UI overview - Meta Horizon Worlds Desktop Editor vs. Roblox Studio

The [desktop editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/user-interface) for Meta Horizon Worlds shares many features with Roblox Studio:

*   The Hierarchy window in Meta Horizon Worlds is similar to the Workspace folder in the Explorer window in Roblox Studio for organizing elements in your 3D scene. Both allow you to manage and organize objects (called entities in Meta Horizon Worlds), and both use a tree structure to represent parent-child relationships between objects.

*   Roblox Studio’s Creator Store and Inventory are also similar to the Asset Store and Assets window in Meta Horizon Worlds, respectively.

![Meta Horizon Worlds UI Overview](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481211737_656797423524879_5559882393384641164_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=cDOsOvnxSxsQ7kNvwE7GDsg&_nc_oc=Adlyky7GJXxwH-FBxgAWU3k2lJEfPrMMMZz_b6-_TMaBBovO9E8uXpnB-nketD1F6v8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BSZs7KBTcuCWIUj_Gj9PnQ&oh=00_AfR5LmPMVaSEG_U6_Kl7ozetQIlrjOowdtTifNf5G9y6rQ&oe=689B9B55)

## Terminology differences

Meta Horizon Worlds uses different terminology to describe some concepts that Roblox creators may already be familiar with. The following is a partial list of terms from Meta Horizon Worlds that have corresponding names in Roblox:

| Meta Horizon Worlds | Roblox | Notes |
| --- | --- | --- |
| World | Place |  |
| Entity | Part | Most basic building block. |
| Asset Template | Packages/Models | A container object that groups multiple gameplay elements including meshes, gameplay logic, audio, and more. These are stored in a library and can be used across worlds and shared with other creators. |
| Transform | Transform/CFrame |  |
| Hierarchy window | Explorer window |  |
| Properties window | Properties window |  |
| Scene window | Viewport |  |
| Assets window | Toolbox |  |
| SpawnPoint | SpawnLocation |  |
| Console | Output |  |
| Asset Library | Creator Store |  |

## Scripting differences

Roblox supports three different types of Luau scripts:

*   Client scripts that run on the client independently of the server

*   Server scripts that run on the server where the client has no visibility to their behavior

*   Module scripts that are reusable pieces of code that return a value, typically a function **Script type comparison** | Meta Horizon Worlds | Roblox |
| --- | --- |
| Script in Local Execution Mode | Client Script |
| Script in default Server Execution Mode | Server Script |
| Export functions/classes in any script | Module script |

Scripts in Meta Horizon Worlds are not separated into types, but can be run in either Default or [Local execution mode](/horizon-worlds/learn/documentation/typescript/local-scripting/getting-started-with-local-scripting) :

*   Default Script Execution
    
    *   A server-side script that never executes on the client.

*   Local Script Execution
    
    *   A script that can execute on the client (but does not have to - can be owned by the server).
    
    *   Offers better performance for the client at the cost of some features and interactivity with Default scripts.

In Meta Horizon Worlds, scripts must be given ownership via code. Generally, the paradigm in Meta Horizon Worlds is to have a server-side manager which assigns local scripts to players as needed when they join the World. In Roblox, local script ownership is handled automatically.

### TypeScript and Luau

Roblox creators add custom gameplay logic to their creations by using Luau, a scripting language derived from Lua 5.1. Meta Horizon Worlds uses [TypeScript](/horizon-worlds/learn/documentation/typescript/getting-started/using-typescript-in-horizon-worlds) , a statically-typed extension of JavaScript. Meta Horizon Worlds provides [APIs](/horizon-worlds/learn/documentation/typescript/getting-started/horizon-typescript-apis) for interacting with the players and environment.

Lua uses a simple and flexible syntax. TypeScript uses a JavaScript-like syntax, is object oriented, and is statically typed.

Here’s an example function written Lua and TypeScript for comparison. The function sums numbers up to a value “n” and returns the sum.

Lua

```
-- Sum numbers up to "n" and returns the sum
function sumUpTo(n)
    local sum = 0
    for i = 1, n do
        sum = sum + i
    end
    return sum
end

print(sumUpTo(5))  -- Output: 15 (1 + 2 + 3 + 4 + 5)
```

TypeScript

```
// Sum numbers up to "n" and returns the sum
function sumUpTo(n: number): number {
    let sum = 0;
    for (let i = 1; i <= n; i++) {
        sum += i;
    }
    return sum;
}

console.log(sumUpTo(5));  // Output: 15 (1 + 2 + 3 + 4 + 5)
``` **Note**: The above example does not show the API differences between Roblox and Meta Horizon Worlds. This is simply an example of the differences between the scripting languages.

Related articles:

*   [Using TypeScript in Meta Horizon Worlds](/horizon-worlds/learn/documentation/typescript/getting-started/using-typescript-in-horizon-worlds)

*   [TypeScript Tutorial](/horizon-worlds/learn/documentation/typescript/getting-started/typescript-tutorial)

*   [Meta Horizon Worlds TypeScript APIs](/horizon-worlds/learn/documentation/typescript/getting-started/horizon-typescript-apis)

## Asset pipeline

Meta Horizon Worlds allows you to [import a variety of asset types](/horizon-worlds/learn/documentation/desktop-editor/assets/creating-importing-viewing-and-spawning-assets) such as 3D models, textures, and sounds. The following is a list of accepted asset types and file formats:

| Asset type | File format(s) |
| --- | --- |
| 3D model | Must have at least one FBX (.fbx) and one PNG (.png) |
| Audio | OGG Opus (.opus) or WAV (.wav) |
| Material | PNG (.png) |
| Skydome | PNG (.png) or EXR (.exr) |
| Texture | PNG (.png) |
| Text | JSON (.json) |

### Importing a world from Roblox to Meta Horizon Worlds

If the assets in your Place were originally imported from an external source as .FBX files, you can import those original .FBX files to Meta Horizon Worlds with no additional conversion. For assets constructed using native Roblox parts, you will need to export them from Roblox, convert them to the file formats listed above using a tool such as [Blender](https://www.blender.org/) , and import them to Meta Horizon Worlds. **Note**: At this time, there is no way to convert scripts written for Roblox into a form usable by Meta Horizon Worlds; all scripts will need to be re-written using the Meta Horizon Worlds [TypeScript API](/horizon-worlds/learn/documentation/typescript/getting-started/horizon-typescript-apis) .

#### How to export assets from your Roblox world

To export an asset from Roblox, you can right-click it in the Explorer and choose **Export Selection**. Models and textures exported from Roblox are in .OBJ and .MTL format, respectively.

![Export Selection](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480812910_656797433524878_3994810472038585410_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=_hpkPFOwRFwQ7kNvwEPVoyY&_nc_oc=AdnK3owueXS2QQVMRh4CUazPk7UF9G_HhzABKfiiWxtpb2_XU0ZUryjMulAytxFZtRc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BSZs7KBTcuCWIUj_Gj9PnQ&oh=00_AfTPo5yRzVl6He9rpVX8FE13sVIr-6ELt0vXOrlDwQ7CWA&oe=689B8387)

## Monetization

Members of the [Meta Horizon Worlds Creator Program (MHCP)](https://developers.meta.com/horizon-worlds/programs) are eligible to monetize their worlds through the MHCP bonus program and the sale of in-world items.

The [MHCP bonus program](/horizon-worlds/learn/documentation/mhcp-program/monetization/bonus-program-overview) tracks the following metrics and pays a separate cash bonus for each metric on a monthly basis, with higher performance tiers resulting in increased payout:

*   **Retention bonus**: Based on the number of users that return to your world within a week of visiting.

*   **Time spent bonuses**: There are two bonuses based on the total number of hours users spend in your world on mobile or headset.

*   **In-world purchase bonus**: Based on the number of dollars spent per paying user who visits your world. [In-world purchases](/horizon-worlds/learn/documentation/mhcp-program/monetization/meta-horizon-worlds-inworld-purchase-guide) are the sales of items and services in your world, such as consumables, cosmetics, game items, and more. Prices for all in-world purchases are set in Meta Credits, which are the non-convertible tokens used to acquire digital goods and services in Meta Horizon Worlds. You receive the full transaction value of each purchase made with Meta Credits based on an exchange rate of **1 Credit = $0.0032**, with the number of dollars spent per user contributing to your **in-world purchase bonus**.

## Community

The [Meta Quest Community Discord](https://discord.gg/mqhwcommunity) provides a platform for discussion and collaboration between Meta Horizon Worlds creators and community members. It is a great place to ask your peers for tips and tricks, and to keep up with the latest discussions.

Members of the [Meta Horizon Creator Program (MHCP)](https://developers.meta.com/horizon-worlds/programs) are invited to join the [Meta Horizon creator forum](https://communityforums.atmeta.com/t5/Meta-Horizon-Creator-Forums/ct-p/Meta_Horizon_Creator_Forums) , where they can connect and collaborate with other MHCP creators. Non-members may still visit the forum and observe the conversation, but you’ll need to enroll in MHCP in order to see all the content or fully participate in the conversation.

## Collaboration tools

You may add [Collaborators](/horizon-worlds/learn/documentation/desktop-editor/getting-started/collaborator-management) to your world to help you with testing and creation. Up to 4 owners and collaborators may simultaneously visit and/or edit your unpublished worlds. If you are a member of the [Meta Horizon Worlds Creator Program](https://developers.meta.com/horizon-worlds/programs) , this number is increased to 20.

Collaborators may be assigned one or more roles:

*   **Tester**: Can visit your unpublished worlds, but cannot edit or publish them.

*   **Editor**: Can visit and modify your unpublished worlds, but cannot publish them.

## Notable feature implementations

Meta Horizon Worlds implements some features in ways that may not be obvious to Roblox creators. Here are a few notable examples:

*   **Lighting and Environment Settings**
    
     \- To edit a world’s lighting settings, create an [Environment gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/use-the-environment-gizmo) and set your options there. This gizmo also allows you to hide the grid in the viewport.

*   **Materials and Textures**
    
     \- Unlike Roblox, a single model in Meta Horizon Worlds can have multiple materials and textures.

*   **Custom UI**
    
     \- To edit the UI in Meta Horizon Worlds, you must use a [Custom UI gizmo](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/creating-a-custom-ui-panel) and associated script.

## Publishing and world discovery

Our recommendation engine fuels discovery across multiple product surfaces in headset (such as Horizon Feed, Horizon Worlds catalog, Horizon Store), on web, and in our Meta Horizon mobile app. For more information about how world discovery works in Meta Horizon Worlds, see [Intro to Horizon Worlds Discovery](/horizon-worlds/learn/documentation/mhcp-program/faq/intro-to-worlds-discovery) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 