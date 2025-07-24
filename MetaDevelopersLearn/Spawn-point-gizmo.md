# Spawn point gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/use-the-spawn-point-gizmo)

In Meta Horizon Worlds, a spawn point refers to a designated location within a virtual environment where [entities](/horizon-worlds/reference/2.0.0/core_entity) such as players, enemies, and NPCs appear or spawn when they enter the world. These spawn points are important for managing entities’ entry and movement within the game.

The spawn point [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) , is a helper tool that you can use to enhance the creation and interactivity of worlds. In the desktop editor, it is a visual representation of a spawn point with editable options for adjusting properties such as position, rotation, and scale. You can also use the [SpawnPointGizmo API](/horizon-worlds/reference/2.0.0/core_spawnpointgizmo) to facilitate the management of spawn points such as [respawn](/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/codeblocks-to-typescript#simplerespawnscriptts) . Additionally, when developing for mobile and web platforms, the spawn point gizmo can be configured to control [player camera’s point of view](/horizon-worlds/learn/documentation/tutorial-worlds/developing-for-web-and-mobile-players-tutorial/module-4-camera-manager#spawnpoint-camera-control) . **Note**: While you can access and use spawn point gizmo in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , this introductory topic to spawn point gizmo focuses on the creator experience in the [desktop editor](/horizon-worlds/learn/documentation/get-started/install-desktop-editor) .

## Limitations

When the entity is teleported to another location, a transition scene may be included. The use of this gizmo may also affect camera view, player gravity, and speed.

## Access and use the spawn point gizmo

In the Meta Horizon Worlds desktop editor, do the following to access the spawn point gizmo:

*   In the desktop editor while in Build mode, select **Build** \> **Gizmos** from the menu bar, search for “spawn point” in the search field.
    

*   Select the spawn point gizmo and drag it into the scene.
    

*   You can now edit the new gizmo properties in the **Properties** panel.
    

## Spawn point properties

The spawn point gizmo properties can be configured in the [Properties panel](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) of the desktop editor or through [scripting](/horizon-worlds/learn/documentation/typescript/getting-started/using-typescript-in-horizon-worlds) .

## Scripting

To govern entity lifecycles throughout the game and implement more complex and dynamic behaviors, use Meta Horizon Worlds [SpawnPointGizmo API](/horizon-worlds/reference/2.0.0/core_spawnpointgizmo) . See [tutorial worlds](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/tutorial-prerequisites) for complete code samples and follow the [companion documentation](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds#in-the-desktop-editor) for an in-depth explanation of the implementation details.

## What’s next?

Now you’ve been introduced to the spawn point gizmo, further your learning with hands-on tutorials, tutorial worlds with completed samples, and developer guides:

*   [Create your first world tutorial: designate a spawn point](/horizon-worlds/learn/documentation/get-started/create-your-first-world#section-2-place-assets-in-the-scene)

*   [Simple respawn script](/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/codeblocks-to-typescript#simplerespawnscriptts)

*   [Multiplayer lobby entering the match](/horizon-worlds/learn/documentation/tutorial-worlds/multiplayer-lobby-tutorial/module-5-entering-the-match)

*   [Chop’N pop](/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-sample-world/module-1-setup)

*   [Rooftop racer](/horizon-worlds/learn/documentation/tutorial-worlds/horizon-traversal-sample-world/module-1-setup)

*   [Set initial PlayerCamera point of view](/horizon-worlds/learn/documentation/tutorial-worlds/camera-api-examples-tutorial/module-2-playercamera-overview#set-initial-playercamera-point-of-view)

*   [Meta Horizon Creator Program creators manual](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#spawn-point-gizmo)

*   [Object spawning](/horizon-worlds/learn/documentation/tutorial-worlds/spawning-and-pooling-in-typescript/module-1-setup)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 