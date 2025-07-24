# ParticleFx gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/particlefx-gizmo)

The ParticleFX [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) is a helper tool that allows you to easily add visual effects such as smoke, sparks, and confetti, making worlds more dynamic and visually engaging. Some use cases of particle effects include adding game event feedback with explosions and hit sparks, or enhance immersion with confetti bursts and water splashes.

The following image is taken from the [sample world](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/tutorial-prerequisites) called [Chop-n-pop](/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-sample-world/module-1-setup) where the ParticleFX gizmos provide the sparkles around the loot.

![the ParticleFx gizmo is at work in the sample world](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/507682304_743560894848531_5873676846396048984_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=nr9iZ1pH7yQQ7kNvwFJsv4H&_nc_oc=AdkYfg4Wb0HhAxxaqLDYsEt9HDZ7zaZpsomNxxldfjyuuOfO3mikikh_a8RhosDAOY4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Z9gIWGBfQd8LN2bk7Q24vQ&oh=00_AfQ5JOc_V2LTWb13Y3M0vVEiw0-0izqWhsqeL66VeM0tGw&oe=689BAC8A)

## Limitations [Performance](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/cpu-and-typescript-optimization-best-practices) can be impacted if too many complex effects are used at once.

## Access the ParticleFx gizmo

While you can access and configure the gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , the following steps show you how to access the ParticleFx gizmo from the desktop editor and add it to the [scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .

*   In the desktop editor while in the Build mode, select **Build** \> **Gizmos** from the menu bar, search for “particle” in the search field.
    

*   Select the ParticleFx gizmo and drag it into the scene.
    

*   You can now edit the new gizmo properties in the [**Properties panel**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) .
    

## Properties

The ParticleFx gizmo is an entity. All objects in a world are represented by entities. [Entities](/horizon-worlds/reference/2.0.0/core_entity) have their respective properties such as position, rotation, and scale. In the **Properties** panel, you can edit the gizmo’s transformation fields to configure its **Position**, 

**Rotation**, and **Scale**.

In the **Emission** section, additional properties are available to customize the ParticleFx gizmo. **Play on Start** controls whether the ParticleFx gizmo auto-starts the effect when the world starts. **Looping** sets the effect to loop or play once. **Preset** allows you to select from an array of particle effects in its dropdown menu. **Preview** allows creators to see how the effect will look while still in the [Build Mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) . This feature is particularly useful for fine-tuning the particle effect during the building phase. Click **Play** to start the preview. Click **Stop** to stop the preview.

For more information on the ParticleFx gizmo properties, see the [MHCP creator’s manual](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#particlefx-gizmo) .

The following image shows the ParticleFx gizmo is at work in the [Build mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) . **Note**: Once the configuration is complete in the **Properties** panel, you can immediately see the effect in either the [Build Mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) by clicking **Play** next to **Preview** or enter the [Preview mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/preview-mode) .

![the ParticleFx gizmo is at work in the Build mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/508169171_743560911515196_8638356247995966737_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=gj9GE_4WcccQ7kNvwGKhZ6d&_nc_oc=AdmyMHH6kQVUGHH_Vco7wvVOXCSMXTIcssnfcn8iLFd0WM-wH1Bt9j5boog5Sr_jfnA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Z9gIWGBfQd8LN2bk7Q24vQ&oh=00_AfQXUzY1G50gCBRPZZnEJzzInrP6MxXmPd55RWeBseQ19Q&oe=689B9F03)

The following image shows the ParticleFx gizmo is at work in the [Preview mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/preview-mode) .

![the ParticleFx gizmo is at work in the Preview mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506729784_743560914848529_4035407153014293926_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=w_unovJiNRoQ7kNvwFole6P&_nc_oc=AdkjXTar0Y12AfBMbAlB9a1Bo1qaTZkPZU0X5dy8FEvQ0hkOs3ngucJaVAVNR0IJ81w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Z9gIWGBfQd8LN2bk7Q24vQ&oh=00_AfQFYetKTBj1FcRQ3oNtQmSPxY2zguUiejcycKBKoQE1rw&oe=689BC4A3)

## Scripting

The ParticleFX Gizmo can also be controlled using [ParticleGizmo](/horizon-worlds/reference/2.0.0/core_particlegizmo) API, allowing you to play, stop, and configure effects programmatically. For additional resources, see the [sample world](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/tutorial-prerequisites) called [Chop-n-pop module 11 loot system](/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-sample-world/module-11-loot-system) . You can find this world in [**Creation Home**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/creating-a-new-world) .

## What’s next?

Now that you’ve been introduced to the ParticleFx gizmo, further your learning with hands-on tutorials and related developer guides:

*   [Chop-n-pop module 11 loot system](/horizon-worlds/learn/documentation/tutorial-worlds/chop-n-pop-sample-world/module-11-loot-system)

*   [Meta Horizon Creator Program’s creator manual on the ParticleFx gizmo](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#particlefx-gizmo)

*   [Example scripts library](/horizon-worlds/learn/documentation/typescript/api-references-and-examples/example-scripts-library#particlefx-gizmo-example-script)

*   [Scripting using TypeScript](/horizon-worlds/learn/documentation/typescript/typescript)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 