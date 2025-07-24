# TrailFx gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/trailfx-gizmo)

The TrailFx [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) is a tool designed to simplify the addition of visual effects, specifically trailing effects to moving objects in a virtual world. When the TrailFX gizmo is active, it creates a visual trail that follows the gizmo as it moves. This gizmo is intended to enhance the visual effects, making worlds more immersive and engaging.

## Limitations

There are [limitations](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#trailfx-gizmo) to the TrailFx gizmo. Using it sparingly to avoid [performance](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/cpu-and-typescript-optimization-best-practices) issues is recommended.

## Access the TrailFx gizmo

While you can access and configure the gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , the following steps show you how to access the TrailFx gizmo from the desktop editor and add it to the [scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .

*   In the desktop editor while in the Build mode, select **Build** \> **Gizmos** from the menu bar, search for “trailfx” in the search field.
    

*   Select the TrailFx gizmo and drag it into the scene.
    

*   You can now edit the new gizmo properties in the [**Properties panel**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) .
    

## Properties

The TrailFx gizmo is an entity. All objects in a world are represented by entities. [Entities](/horizon-worlds/reference/2.0.0/core_entity) have their respective properties such as position, rotation, and scale. In the **Properties** panel, you can edit the gizmo’s transformation fields to configure its **Position**, 

**Rotation**, and **Scale**.

In the **Visual** section, additional properties are available to customize the TrailFx gizmo. **Play on Start** controls whether the TrailFx gizmo auto-starts the effect when the world starts. **Length**, 

**Width**, **Start Color**, 

**End Color**

 and **Preset** control the appearance and style of the TrailFx gizmo. The **Preset** dropdown menu allows you to select from three types of trails: **Default**, 

**Simple**

 or **Tapered**.

**Preview**

 allows creators to see how the trail effect while still in the [Build Mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) . This feature is particularly useful for fine-tuning the visual aspects of the trail effect during the building phase. Click **Play** to start the preview. Click **Stop** to stop the preview. **Note**: For more information on the TrailFx gizmo properties, see the [MHCP creator’s manual](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#trailfx-gizmo) .

The following image shows how the **Preview** property works while you’re in the [Build mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) . Once the TrailFx gizmo is configured with a simple trail in colors of purple and green, click **Play** next to **Preview**. You can [move](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/object-tools#move) the gizmo manually to see the trailing effect.

![The TrailFx gizmo configured with a simple trail in colors of purple and green in the Build mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506212074_739691291902158_3023337851867814073_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=O46Ci69PrywQ7kNvwE-iF0O&_nc_oc=Adnt0tE6JaqCjttvI2x6WaPonf8-P9TAAnqmAuDSY_oDtr25CDXEVz0IGQ55DQLDAJA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=gv5X03R2xSenIpInZ5fJ5A&oh=00_AfRRuDf2MGib5Dlp1TbTTzWK-1ftD0yN-g7whR8DWoMJLg&oe=689BA7C9)

The following images show the TrailFx gizmo at work while you’re in the [Preview mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) with **Play on Start** turned on. The shape and the color of the trail are configured as **Tapered** with colors of purple and pink. **Note**: To reproduce what you see in the image below, create a world by first following the [Batting cage tutorial](/horizon-worlds/learn/documentation/tutorial-worlds/batting-cage-tutorial) and then add a TrailFx gizmo as a [child object](/horizon-worlds/learn/documentation/desktop-editor/objects/object-grouping) of the ball in the [**Hierarchy**

 panel](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview) . 

[Adjust the position](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/object-tools#move)

 of the TrailFx gizmo so that it appears to be trailing the ball.

![The TrailFx gizmo configured as the child of the ball in Hierarchy](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506050919_739691298568824_5981076667099177757_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=8XNYafhujA8Q7kNvwEL3Dbf&_nc_oc=AdnQkkYyNWhvlGzPTZwbBP2cO7sLMArlz_u2QnsQcbDrX3CbUln2L_eI5EXhij4SMag&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=gv5X03R2xSenIpInZ5fJ5A&oh=00_AfSLJMwZ2Ryg6WuLih0N3xq24sIJcE3f5qp8ivb8TgwNTA&oe=689BB65D)

![The TrailFx gizmo in the Preview mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506407852_739691295235491_2590837823088924789_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=YkuSDhaCFwMQ7kNvwG4u-OR&_nc_oc=Admw4re7NradzmIVUNscryMA-0_Wg7gFlFmIu5COyEvn46bGhlY6Gcr7z2Gqk08jwaw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=gv5X03R2xSenIpInZ5fJ5A&oh=00_AfSaQIxcAkB2KQ8kSN-WWy1Ghi2WzqcCIABJSI7X5U-Nag&oe=689B8D6B)

## Scripting

To customize the TrailFx gizmo through scripting, see the [TrailGizmo](/horizon-worlds/reference/2.0.0/core_trailgizmo) API.

## What’s next?

Now that you’ve been introduced to the TrailFx gizmo, further your learning with related developer guides:

*   [Meta Horizon Creator Program’s creator manual on the TrailFx gizmo](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#trailfx-gizmo)

*   [Batting cage](/horizon-worlds/learn/documentation/get-started/batting-cage-tutorial)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 