# Setting up worlds for mobile and web

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/setting-up-worlds-for-web-and-mobile-compatibility)

## Overview

Setting worlds up to work on web and mobile requires some extra considerations. This page gives an overview of:

*   [Common areas for content improvement](/horizon-worlds/learn/documentation/create-for-web-and-mobile/setting-up-worlds-for-web-and-mobile-compatibility#common-areas-for-content-improvement)

*   [Feature references and examples](/horizon-worlds/learn/documentation/create-for-web-and-mobile/setting-up-worlds-for-web-and-mobile-compatibility#feature-references-and-examples)

## Common areas for content improvement

### Testing

The best way to ensure your world offers a great experience on mobile and web is to test it on these devices throughout the development lifecycle.

You can configure your preview mode in the Desktop Editor to emulate a mobile experience, or you can select a Preview Action to test directly within the Meta Horizon App.

Further reading: [*Preview Device*](/horizon-worlds/learn/documentation/desktop-editor/getting-started/preview-mode#preview-device) ### Inputs and HUD buttons

Avoid unnecessary HUD button clutter.

Set the actions per grabbable (turning them off where unneeded), or if most grabbables in your world have no interaction logic you can turn it off and turn it back on on a per item basis.

Further reading: [*Action buttons*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/action-buttons/) Prefer displaying custom-bound inputs only when contextually relevant.

Use Custom Input API to bind and unbind custom inputs as required.

Further reading: [*Custom Input API Example*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/custom-input-api/) Communicate what action pressing a button will perform.

Select a button icon that closely represents the action pressing a button will perform. Select an icon to represent the grabbable item when holstered. Upload and use custom images for held item actions in the HUD (or for use in holstering).

Further reading: [*Action buttons*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/action-buttons/) , 

[*Custom action button icons*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/custom-action-button-icons/)

 (2P-only), [*Holster button icons*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/holster-icon-menu/) ### Optimization

If your world is targeting mobile players, invest time in optimising as you go.

Loading time is a key factor for mobile users, we are working to improve this at the platform level but there is a lot that you can do yourselves when building. Think carefully about the assets that you include and the complexity of the environment and look into the debugging and testing tools available.

Further reading: [*Using performance tools from web and mobile*](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/using-performance-tools-from-web-and-mobile) ### Design

Design for mobile from the start.

Retrofitting a VR world to work on web & mobile can often take more work. The work to do varies depending on the world but here are some examples of the different methods that can be used:

*   Emulate: Enable players to interact in the same way they would in VR. For example, pressing a button in the world.

*   Adapt: Give mobile players the same experience as VR players, but adapt the mechanic to leverage the different inputs for mobile players. For example, a button to reload a gun rather than physically reloading the weapon, or using Focused Interaction to throw a paper aeroplane.

*   Bifurcate: Offer mobile players a different experience from VR players, but in the same world by using focused interaction and camera API to produce standard modern mobile game type interactions.

\[2P Only\] Use Core Loop quests & rewards for engagement and retention.

Ensure you have quests covering both early game (to aid initial onboarding and generate investment in the world) and long play (to give players depth and reasons to continue to engage over time).

### Metadata

Present your world in an attractive and representative fashion.

Ensure your world’s name and description display correctly on all surfaces and are clear and concise.

Provide images - either through your Meta Producer or via MHCP submission - that are attractive and representative, and that conform to the technical specs.

Further reading: [*Image technical specifications*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/publishing-worlds-on-mobile#image-technical-specifications) ### Player Acquisition

Consider link sharing and social promotion.

The ability to share a direct link to your world (which will open in the mobile app if the person who clicks it has it installed) is a critical advantage, enabling single-click low-friction play. Use this to your advantage to drive players into your world from anywhere!

## Feature references and examples

| Creation Tool | Description | Example world and function |
| --- | --- | --- |
| Selectable on screensGuide | Editor PropertySet trigger volumes as “interactable” in screens, such that web and mobile players can interact with buttons (that MR players would physically push). | Horizon CentralUsed to interact with various gizmos and toys (e.g. making a drink in the plaza). |
| Aim directionGuide | Editor PropertySet the “forwards” direction for a grabbable, ensuring that it looks correct & that any projectiles travel in the right direction. | CitadelUsed to set up the weapon launchers used heavily throughout the world. |
| Action iconsGuide | Editor PropertyChoose from a pre-defined (everyone) or custom-uploaded (1P/2P/MHCP) set of icons for the on-screen “action” buttons. | Horizon CentralChanges the use icon when picking up items e.g. drink icon for a drink. |
| Multi holsteringGuide | Editor PropertySet the icon to use in the “holster” system UI (allowing mobile players to switch between several attached-to-avatar grabbables with on-screen buttons). | CitadelRequired to set up the weapon launchers used heavily throughout the world. |
| Attach to ScreenGuide | Editor PropertyEnables (pre-Custom UI) UI to be attached to the screen to provide a pseudo-HUD (UI still exists in world & can clip with environment). | CitadelUsed to inform users about game progression (e.g. weapons being unlocked). |
| Grip poseGuide | Editor PropertySet how the player’s avatar should hold a grabbable entity. |  |
| Crosshair selectionGuide | Editor PropertyEnables creators to select from a predefined list of crosshairs, enhancing player aiming. | Super RumbleUsed to select different crosshairs for the weapons (e.g. pistol vs rifle). |
| Spawn point cameraGuide | Editor propertySet the player camera (1st or 3rd person) on spawning the player (e.g. at start of experience, or when moving between sections like lobby/arena). |  |
| Device branchingAPI DocsGuide | TypeScript \| CodeBlocksEnables script to respond to player’s device and branch based on device type (mobile, PC, VR). | Super RumbleTailoring the instructional content in the lobby to the user’s device. |
| Avatar animationsAPI DocsGuide | TypeScript \| CodeBlocksEnables creators to play avatar animations appropriate to their grip pose, as well as death and respawn animations. Using TypeScript, creators can override grip poses (i.e. how grabbable entities are held). | Super RumbleHold weapons in different grips as well as trigger the death animation when killed. |
| Custom UIGuide | TypeScriptEnables rich interactive and non-interactive UI, both world (in-environment) and screenspace (HUD). | CitadelAllows selecting a difficulty in the lobby area as well as upgrading your equipment. |
| Custom inputGuide | TypeScriptBind inputs for actions that do not depend on holding a grabbable (e.g. to trigger a special ability). | Super RumbleUsed for the special ability and moved to the “tray” location. |
| Focused interactionAPI DocsGuide | TypeScriptEnables players to directly interact with the world using touch (tap, swipe) or mouse input. Provides (customisable by the creator) visual feedback to the player. | Puzzle ParadiseUsed for positioning puzzle pieces. |
| Unfocus | TypeScriptEnables creators to programmatically unfocus a focused element such as custom UI or SUI (e.g. leaderboards) | CitadelUsed to close the selection UI after selecting a difficulty at the start. |
| ThrowingAPI DocsGuide | TypeScriptEnables triggering throwing the currently-held item through TypeScript, providing greater control over how the item is thrown (e.g. speed, pitch, handedness) |  |
| Aim assistGuide | TypeScriptEnables creators to add aim assist to their world, generating a force to pull the camera towards a particular entity, player, or vector |  |

## Publishing your world on mobile and web

Any world you create is available on web and mobile by default. To inform mobile players of a world’s level of mobile compatibility, worlds are tagged as Unsupported, Playable or Optimized for mobile in the Meta Horizon App, and in the Horizon menu when playing on mobile.

For more information on the world review and tagging process visit [*Publishing worlds on mobile*](/horizon-worlds/learn/documentation/create-for-web-and-mobile/) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 