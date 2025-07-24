# Use offset pivots

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/assets/offset-pivots)

This topic describes when and how offset pivot is used, outlines the expected behavior of offset pivot in the desktop editor, and ends with a discussion on managing offset pivots and best practices.

By default, an entity’s pivot point is its center. This behavior works well for entities like planets, ice skaters, and spinning tops, but not for entities such as doors, drawbridges, and treasure chest lids. For the animation of these entities to look natural, [pivot](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/object-tools#pivot) points need to be offset or moved.

When you create an asset using a [digital content creation tool](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model#setup-requirements) , you can configure the [3D model](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model) to use an offset pivot instead of a center pivot. As you import [this type of asset](/horizon-worlds/reference/2.0.0/core_meshentity) to your personal asset library in Meta Horizon Worlds, you have the option to [**Preserve offset pivots**](/horizon-worlds/learn/documentation/get-started/create-your-first-world-continued#part-2-import-custom-models-and-write-your-first-script) . When you enable **Preserve offset pivot**, entities spawned from the asset will rotate and scale around the pivot defined in the FBX file, instead of the default center pivot.

![Turn on Preserve Offset Pivot](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489545097_693923539812267_8172185265185112732_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=diWK2E_vzcYQ7kNvwGOws1i&_nc_oc=AdmuKK62Gv1HwoSeIN36ZYkhLbf0Jq7lM-yULqQpey9yIoK3fEoUnQ05mQps3wWkpSk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=5ofgLt5hLZVzrUbvP6kbGQ&oh=00_AfT-HQ0j2O3JN6OSRfW7xV81m447JqmUpg9k7GXeKun5qQ&oe=689B9C72)

Although you can use offset pivots in both the [desktop editor](/horizon-worlds/learn/documentation/desktop-editor/desktop-editor) and the [VR editor](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , this topic focuses on the desktop experience. Additionally, you can also write [TypeScript code](/horizon-worlds/reference/2.0.0/core_entity) that uses the offset pivot for rotating and scaling. **Note**: You can import [single-mesh FBX files](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model) that contain only one pivot offset. Offset pivots don’t support custom [colliders](/horizon-worlds/learn/documentation/custom-model-import/user-guides/collider-visualization-user-guide) .

## Prerequisites

Before you begin, make sure you have the following:

*   [Install and run the desktop editor](/horizon-worlds/learn/documentation/get-started/install-desktop-editor)
    
    .

## How to use offset pivots

In this section, you import a 3D model that already contains an offset pivot to your [personal asset library](/horizon-worlds/learn/documentation/desktop-editor/assets/introduction-to-the-desktop-editor-asset-library) . You then manipulate the entity based on its offset pivot.

### Step 1: Import the 3D model

Follow these steps to use the asset file provided by Meta that contains an offset pivot.

*   Download the [Demo asset](https://scontent.oculuscdn.com/v/t64.5771-25/38974594_480602711643840_7021902764535901297_n.zip?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=McMhltMgN-0Q7kNvwEHgB4s&_nc_oc=AdnjGPDpsXOOQTXTwxMc78vd3L4hX1BLtyf5hzdmk4oI_j7x81t9zpRTXpoYPtE4otY&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQ3s4b2lXmdcT03uiQCj8Bx9t11u8aQLi0vBO1M19zd7A&oe=689B9B8B) . This file is a zip archive that contains a single mesh 3D model that contains an offset pivot, and a texture file.
    
    ![A single mesh 3D model provided by Meta](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461927797_559139473290675_4813403258144594456_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=uR8i4JmSYDIQ7kNvwElw0G_&_nc_oc=AdnIR8ZUoX5zYfVQJdlJPuOPf2ZducKIJDBuYkI3JznhHvyzBG0HQjCXEakteUp1c9c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=5ofgLt5hLZVzrUbvP6kbGQ&oh=00_AfTNrh9cAmzxMUI51NaulIxsVyV0Z_QRN-loM1Yp_32h1A&oe=689BAAD7)
    

*   Unzip the archive to a local folder. Next, import the 3D model to **My Assets** either through the desktop editor or your [Meta Horizon portal account](https://horizon.meta.com/creator/assets/folder/) . The following steps highlight the experience from the desktop editor.
    

*   In the desktop editor, navigate to [Asset Library](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#assets-library) under the [Scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .
    

*   Click on **My Assets** \> **Add New** \> **3D Model**.
    
    ![Import a 3D model](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490513036_693923536478934_4393520325363504919_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=w-3OTzbyOkcQ7kNvwH447jB&_nc_oc=Adlmibv9WPA9pT7iXum7i9IqQ4UONuiLZB5yZzg6UPCtheajqTRaM5uA6uIO8z0TjP0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=5ofgLt5hLZVzrUbvP6kbGQ&oh=00_AfTeO7FZ3ikyTGH3X9i9hshIixzHvB9IOX6i9x9Qq5KiGA&oe=689B8B7B)
    

*   The **Import Model(s)** dialog appears. Click **choose files on your device**.
    

*   Navigate to the folder that contains the unzipped asset files.
    

*   Select the two asset files and then click **Open**.
    

*   Leave **Preserve offset pivots** enabled.
    

*   Click **Import**. The asset appears in the **My Assets** folder.
    

### Step 2: Manipulate entities with offset pivots

*   [Create a new world](/horizon-worlds/learn/documentation/desktop-editor/getting-started/creating-a-new-world)
    
     in the desktop editor.
    

*   Spawn an instance of the asset by dragging the SkateboardBird asset from **My Assets** to the Scene pane. Notice that the pivot is grounded. **Note**: Once the mesh of the custom model is imported, changes to the pivot must be done in a [digital content creation tool](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model#setup-requirements) . While you cannot change the pivot’s position in the Meta Horizon Worlds desktop or VR editor, you can toggle between the entity’s offset pivot and the center pivot as shown in the image below. The setting persists across Meta Horizon Worlds sessions.
    
    ![Comparing center pivot to offset pivot](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489759643_693923543145600_2643000062555377148_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=pWX16AWyUQQQ7kNvwGUuSEm&_nc_oc=Adn8NJ0U7JTeB886bamgVVo9FwxlMo4e66o0wsUndkToTkPsHTEfEPoN9mtDLN6uvxU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=5ofgLt5hLZVzrUbvP6kbGQ&oh=00_AfTuVggBQjjAKbHwvzStwMI-6bmjdEba4XtkM12xbVRpzw&oe=689B920E)
    
    You can also enable the offset pivot in [VR](/horizon-worlds/learn/documentation/vr-creation/getting-started/using-the-creator-menu) as shown below.
    
    ![Turn on offset pivot in VR](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489927670_693923533145601_7120568709072388555_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=hzN8KGRwfScQ7kNvwE8hmMP&_nc_oc=AdmbU99Ar71EPH-Z6p5daLaq7-8eLlZcIDDGK71NWR8hSMdG4yWPfTvuNpgS3m_1jMw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=5ofgLt5hLZVzrUbvP6kbGQ&oh=00_AfSPPUT9swdpgKzB0q-P2L6_Y6d0Efsp9TZV-eii88V2vA&oe=689B8FBD)
    

*   Manipulate the entity based on its offset pivot, including position, rotation, and scale. You can do this in the [desktop editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/object-tools) and in the [VR editor](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) . **Note**: If you need to define custom pivots for entities created in the Meta Horizon Worlds desktop editor, see [Pivot around parent object](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview#pivot-around-parent-objects) for a different approach.
    

## Manage offset pivots

When working with offset pivots, be aware of the following limitations and best practices.

### Preserve single-mesh uploads

You can preserve offset pivots only for [single-mesh FBX files](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model) .

You can try to use a multi-mesh hierarchy, but your results will be undefined. If your entity has a hierarchy with offset pivots, then you must import the offset pivot meshes one at a time.

### Use non-custom box colliders

You should import meshes that have only non-custom box colliders, because using custom colliders produces undefined results.

## What’s next?

Try the following related topics:

*   [Getting started with custom model import](/horizon-worlds/learn/documentation/custom-model-import/getting-started-with-custom-model-import)

*   [Materials guidance and reference for custom models](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/materials-guidance-and-reference-for-custom-models)

*   [Collider ingestion user guide](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/collider-ingestion-user-guide)

*   [Hierarchy panel overview](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 