# Snap destination gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/snap-destination-gizmo)

The snap destination [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) is a helper tool used by creators to designate specific locations where players’ avatars can snap into place. When players use teleport movement, the aiming circle will automatically snap to the center of the gizmo when the area covered by the gizmo is detected.

The following image shows the aiming circle in [VR](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) when the **Movement style** is set to **Teleport** in the Worlds app settings.

![A screenshot of the aiming circle in VR](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/511130115_750518717486082_3937306918986985171_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZQ3aCRb96-kQ7kNvwFiSl0N&_nc_oc=Adk02O5fJrvxtlh4Ffw584A5mxrbfrCZlQ8snCvZ6jvgD_sU_sQS8toHA1-MCTIhdy8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lLtJpG-Cp7HY6_oVMA-A2g&oh=00_AfTIGDzigoAObzXCAehaRS6Um7pnVA95mnXy0W8o-B2MAw&oe=689B98BE)

## Access the snap destination gizmo

While you can access and configure the gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , the following steps show you how to access the snap destination gizmo from the desktop editor and add it to the [scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .

*   In the desktop editor while in the [Build mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) , select **Build** \> **Gizmos** from the menu bar, search for “snap destination” in the search field.
    

*   Select the snap destination gizmo and drag it into the scene.
    

*   You can now edit the new gizmo properties in the [Properties panel](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) .
    

## Properties

The snap destination gizmo is an entity. All objects in a world are represented by entities. [Entities](/horizon-worlds/reference/2.0.0/core_entity) have their respective properties such as position, rotation, and scale. In the **Properties** panel, you can edit the gizmo’s transformation fields to configure its **Position**, 

**Rotation**, and **Scale**.

**Apply Orientation**

 controls whether the player’s final orientation will be aligned with the gizmo’s orientation. **Note**: To validate that the snap destination gizmo is working, visit the world with the snap destination gizmo in [VR](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) . Ensure to set **Movement style** to **Teleport** by going to the Worlds app’s **Settings** \> **Gameplay** \> **Movement style** \> **Teleport**.

When players use teleport movement, the aiming circle will automatically snap to the center of the gizmo when the area covered by the gizmo is detected.

## What’s next?

Now that you’ve been introduced to the snap destination gizmo, further your learning with more developer guides:

*   [Meta Horizon Creator Program’s creator manual on the snap destination gizmo](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#snap-destination-gizmo)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 