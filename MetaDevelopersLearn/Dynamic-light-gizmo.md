# Dynamic light gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/dynamic-light-gizmo)

The dynamic light [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) allows creators to add dynamic lighting effects such as moving and changing lights. Some common use cases include enhancement of atmosphere and [highlighting important areas or objects](/horizon-worlds/learn/documentation/tutorial-worlds/economy-world-tutorial/module-3-configuring-gameplay#configuring-the-apple-spawners) .

The following image is taken from the [tutorial world](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) called [Economy world](/horizon-worlds/learn/documentation/tutorial-worlds/economy-world-tutorial/module-3-configuring-gameplay) where the dynamic light gizmos are at work. The dynamic light is used to draw attention to the apple.

![An screenshot of the dynamic light gizmo at work](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/505443192_738224338715520_974421412205283361_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=R6JgqldEcsQQ7kNvwFqzwli&_nc_oc=AdmHhIldUUSpteoVM_XeaT6vfMB3r2nToHwpaNdb8wVLXmWiBwrp6F_xeIPSARVmy3o&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=hUHd3jIhf6PJyp8AlrKEEQ&oh=00_AfSn46kxaceD7IAk3T05cWCYlA3zV-c8XUPHSA42yYE4pA&oe=689B972A)

## Limitations

While using the dynamic light gizmo, there are [limitations](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#dynamic-light-gizmo) . For example, the number of lights permitted and its impact on [performance](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/unity-performance-designing-a-performant-world) .

## Access the dynamic light gizmo

While you can access and use gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , this topic focuses on the creator experience in the desktop editor.

*   In the desktop editor while in the Build mode, select **Build** \> **Gizmos** from the menu bar, search for “dynamic light” in the search field.

*   Select the dynamic light gizmo and drag it into the scene.

*   You can now edit the new gizmo properties in the [**Properties**
    
     panel](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) .

## Properties

The dynamic light gizmo is an [entity](/horizon-worlds/reference/2.0.0/core_entity) . All objects in a world are represented by entities. Entities have their respective properties such as position, rotation, and scale. In the Properties panel, you can edit the gizmo’s transformation fields to configure its **Position**, 

**Rotation**, and **Scale**. Additionally, like the transformation, [**Color**](/horizon-worlds/reference/2.0.0/core_color) can be edited in the UI panel or controlled through scripting.

In the **Light** section, additional properties are available to customize and manage dynamic lights.

The **Enabled** toggle turns the light on or off.

The **Color** and **Intensity** fields let you configure the light’s appearance and intensity. **Light Type** specifies the type of light sources such as **Point** (omnidirectional light) or **Spot** (cone-shaped light). **Falloff Distance** specifies the decline in light intensity with distance. **Spread** specifies the spread of spotlight, which is the width of the light beam.

For more information on the dynamic light gizmo properties, see [MHCP creator’s manual](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#dynamic-light-gizmo) and the [DynamicLightGizmo](/horizon-worlds/reference/2.0.0/core_dynamiclightgizmo) API.

## Scripting

To control the gizmo through scripting, see the [DynamicLightGizmo](/horizon-worlds/reference/2.0.0/core_dynamiclightgizmo) API.

## What’s next?

Now that you’ve been introduced to the dynamic light gizmo, further your learning with hands-on tutorials and guides:

*   [Meta Horizon Worlds creator’s manual on the dynamic light gizmo](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#dynamic-light-gizmo)

*   [Tutorial worlds on dynamic lights](/horizon-worlds/learn/documentation/tutorial-worlds/economy-world-tutorial/module-3-configuring-gameplay)

*   [Material asset user guide](/horizon-worlds/learn/documentation/desktop-editor/assets/material-asset-user-guide)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 