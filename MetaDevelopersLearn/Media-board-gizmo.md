# Media board gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/media-board-gizmo)

Note

You will need to be a member of [Meta Horizon Creator Program](/horizon-worlds/learn/documentation/mhcp-program/welcome) to access the media board gizmo.

The media board [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) allows you to display the top 30 photos from a world. Adding a media board can show players how others have interacted with the world and encourage players to post their own photos to the world. The media board auto-rotates through photos unless a player is interacting with it.

Players in a world can react to media displayed on the media board with the **Like** button, which triggers a thumbs up emote. They can also share their own photos with the **Add post** button. The following image illustrates the description of the media board gizmo.

![An screenshot of the media board gizmo](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452514566_512510187953604_8648481134651688436_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=dH_Ap9pwSfwQ7kNvwHfcZ0U&_nc_oc=AdlezzxshfAVqfVDNIOUB_rP34zF1TsJTFORGYGZcajgeLbbVDP8DP5_71rPep2vmN4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=FVxnVTr1_QkE8M54FBPhpw&oh=00_AfRbLoJn4VOQ86IkRAIFzQY-QEExKY7bbNhZkKExPdvUQQ&oe=689B967D)

Each player sees a personalized set of 30 photos, selected from photos that are included in the approved world posts. Photos from others that the player follows and photos with a high **Like** count are prioritized for the media board.

## Access the media board gizmo

While you can access and configure the gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , the following steps show you how to access the media board gizmo from the desktop editor and add it to the [scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .

*   In the desktop editor while in the Build mode, select **Build** \> **Gizmos** from the menu bar, search for “media board” in the search field.
    

*   Select the media board gizmo and drag it into the scene.
    

*   You can now edit the new gizmo properties in the [**Properties panel**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#properties-pane) . **Note:** There is a known issue where media boards appear smaller than expected in desktop. The size in VR is correct.

## Properties

The media board gizmo is an entity. All objects in a world are represented by entities. [Entities](/horizon-worlds/reference/2.0.0/core_entity) have their respective properties such as position, rotation, and scale. In the Properties panel, you can edit the gizmo’s transformation fields to configure its **Position**, 

**Rotation**, and **Scale**.

In the **Behavior** section, additional properties are available to customize the media board gizmo. **Pinned Page** controls the number of photos that can be listed; up to 30 photos can be listed. **Panel UI Mode** controls the gizmo’s appearance and style. **LoD radius** controls the distance, in meters, that the media board appears for players. If set to 0, the panel always appears. Otherwise, the panel appears when a player is within the specified radius. **Deterministic Ranking** ranks photos by recency rather than likes.

For more information on the media board gizmo properties, see the [MHCP creator’s manual](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#media-board-gizmo) .

## Approve or reject photos

Once you approve a photo, it becomes available on the media board and visible to the public. The following steps show you how to approve photos for a world from the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) .

*   Open the Creation page.

*   Click on **Posts & feedback**.

*   You see a list of posts. Use the dropdown menu on the top right to filter to only pending posts.

*   Pending posts have 3 buttons: **Approve**, 
    
    **Reject**, and **Report**.

*   Select the **Approve** button to makes a photo visible on a media board.

![](https://scontent.oculuscdn.com/v/t64.5771-25/57568685_9616779308338433_7778029375936424794_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=a_JuZmKJOvIQ7kNvwEAx98P&_nc_oc=AdmjAW0JkADHQsk2v1Fk1qdw-rPXiSVSurSmmC1tqKEwFnAsqy2kmbK1Bl6XtZC08Pc&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQXF2xFDQZn4wuC_d1SWbPOFdlxHgf49_7jD-OEeOkMXQ&oe=689BBDB6)

Conversely, to remove a photo from the media board once it’s been approved, follow these steps to reject it from the approved posts.

*   Open the Creation page.

*   Click on **Posts & feedback**.

*   Once you see a list of posts, use the dropdown menu on the top right to filter to approved posts.

*   Click the **Reject** button, which appears to the left of the three-dot menu.

## What’s next?

Now that you’ve been introduced to the media board gizmo, further your learning with related developer guides:

*   [Meta Horizon Creator Program’s creator manual on the media board gizmo](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#media-board-gizmo)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 