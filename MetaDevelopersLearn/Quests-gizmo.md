# Quests gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/quests-gizmo)

Quests refer to a set of tasks that players can complete to earn rewards. These quests are designed to engage players and encourage exploration in the virtual environment. Completing quests can lead to various rewards, and are a way to drive player interaction and retention.

In Worlds, [quests](/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/quests-overview) is the global system that’s used to create and manage a set of objectives or tasks in a world. The feature provides a way for creators to define the objectives, rewards, and rules for completing quests. The quests system uses [persistent variables](/horizon-worlds/learn/documentation/typescript/getting-started/persistent-variables-v2) to manage objectives or tasks as they allow creators to store and maintain data across player sessions.

The quest [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) is a helper tool that creators use to display a list of achievable tasks and track user progress towards completing these tasks. The quests gizmo, the visual display panel, is linked to quests you set up in [**Systems**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/creator-toolbar#systems-tools-menu) from the menu bar.

## Access the quests gizmo

While you can access and configure the gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , the following steps show you how to access the quests gizmo from the desktop editor and add it to the [scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .

*   In the desktop editor while in the Build mode, select **Build** \> **Gizmos** from the menu bar, search for “quests” in the search field.

*   Select the quests gizmo and drag it into the scene.

*   You can now edit the new gizmo properties in the [Properties panel](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) .

## Properties

The quests gizmo is an entity. All objects in a world are represented by entities. [Entities](/horizon-worlds/reference/2.0.0/core_entity) have their respective properties such as position, rotation, and scale. In the Properties panel, you can edit the gizmo’s transformation fields to configure its Position, Rotation, and Scale. Additionally, like the transformation, [Color](/horizon-worlds/reference/2.0.0/core_color) can be edited in the UI panel or controlled through scripting.

In the **Quests** section, additional properties are available to customize and manage quests. **Displayed Title** lets you name the visual display of the quest panel. **\# of Entries Per Page** controls the number of quests you can see per page.

Properties such as **Panel UI Mode** and **Use HUI Panel** let you configure the gizmo’s appearance and style. **LOD Radius** controls the maximum visibility distance. **Visible** controls the gizmo’s visibility.

For more information on the quests gizmo properties, see the [MHCP creator’s manual](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#quests) .

## Scripting

To set up the script that updates quests results for players in the world, use the APIs:

To display player achievements, use the `displayAchievements` method in the [AchievementGizmo](/horizon-worlds/reference/2.0.0/core_achievementsgizmo) class.

To set and query if an achievement is complete, use the `setAchievementComplete` and `hasCompletedAchievement` methods in the [Player](/horizon-worlds/reference/2.0.0/core_player) class.

Additionally, built-in [`CodeBlockEvents`](/horizon-worlds/reference/2.0.0/core_codeblockevents) are available to listen for events such as when an achievement has been completed: `OnAchievementComplete`.

## What’s next?

Now that you’ve been introduced to the quests gizmo, continue your learning with hands-on tutorials, and more related developer guides:

*   [Tutorial worlds on variable groups and persistent variables](/horizon-worlds/learn/documentation/tutorial-worlds/scripted-avatar-npc-tutorial/module-1-setup)

*   [Tutorial worlds on quests](/horizon-worlds/learn/documentation/tutorial-worlds/scripted-avatar-npc-tutorial/module-5-quest-manager)

*   [Tutorial worlds on persistent variables](/horizon-worlds/learn/documentation/tutorial-worlds/custom-ui-examples-tutorial/station-7-persistent-variables)

*   [Meta Horizon Creator Program’s creator manual on the quests gizmo](https://my-od.developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/quest-gizmo)

*   [Quests, leaderboards, and variable groups](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/quests-leaderboards-and-variable-groups)

*   [Writing for localization on providing description of the quest](/horizon-worlds/learn/documentation/save-optimize-and-publish/internationalization/writing-for-localization)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 