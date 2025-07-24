# View modes for debugging

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/getting-started/view-modes-for-debugging)

Debugging view modes in desktop editor can help you debug your world. Its features include:

*   Wireframe viewing options that give you visibility into the geometric complexity of your meshes.

*   A collision view mode that helps you understand how players will be able to interact with objects in your world.

*   An overdraw view mode that helps you see where the same pixels are being drawn more than once.

## Opening in desktop editor

To open the view modes menu, select the view icon on the right side of the toolbar.

![The debugging view mode icon](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/485353085_677084098162878_564880857810169754_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=QYa4VcCrrqsQ7kNvwGq9TT2&_nc_oc=AdkXcEzz622ENcCSvZMYcbB2BJ2Ne4AxTKJEoB3N8-HV0v2acjWdN-XshIw-0bwbP0c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfSgs5Y0msIeAkI_h4A9ru2tGnnuuuYifBV1SvSVlY4KUg&oe=689BA26B)

Hovering your cursor over each option reveals a description of the view mode. See [Available view modes](/horizon-worlds/learn/documentation/view-modes-for-debugging#available-view-modes) for further details. After selecting an option, the view mode will be displayed inside the dropdown button. Hovering over this dropdown button will also show you the active view mode.

![List of Available viewmodes](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484836232_677084111496210_6923534349643550921_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=VNCUykw3zqoQ7kNvwF9wywS&_nc_oc=AdkpbM5K6Kcu1oyS8Or_0QYq-rJTdcUfvh2N_7c5mkOvbVvsXeVRz-Qp8muaGVWpBxI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfRw15nzus3hATCCNXyt3_JjGLApqwIGMwUECanO_mJiBg&oe=689B85D0)

### Opening in VR

In VR, first [Enable the Utilities Menu](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/enable-the-utilities-menu/) , then open your wearable and select the desired view mode.

![](https://scontent.oculuscdn.com/v/t64.5771-25/75348041_964519652195117_6384169750030954787_n.gif?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=pEPP9fp5kwYQ7kNvwFzDOmv&_nc_oc=Adkp64StfZQTMCOQOozGtbWDw7mDecSjWqLdcWq9lGJw_L_wInj_a07KrtIebPWLNJs&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQg-_4PbFNaLomP59b8vZytBbW-PBnCR-Nv1pvxtmP8eg&oe=689B863A)

## Available view modes

| View mode | Description |
| --- | --- |
| Shaded | - Texture only.- This is the default view that shows meshes with their textures available. |
| Wireframe | - Wireframe only.- Use this to view your world’s geometric complexity. It allows you to see through meshes for debugging unintended overlaps between objects. |
| Solid wireframe | - Wireframe over a solid material.- This option places a solid material underneath the wireframe, it’s useful for displaying objects that are apart and distinguishing which objects are closer to the camera. |
| Shaded wireframe | - Wireframe over the object’s texture.- Use this view to understand how textures are affected by their underlying mesh geometry and debug texture issues that may be caused by the meshes underneath them.- Note: There is a known bug in the desktop editor where jumping to Preview mode while Shaded Wireframe mode is active causes the player to pass through geometry. |
| Collision | - Shows object colliders.- Use this view to see which objects have colliders. You can also use this to optimize the performance of a world to disable collisions on objects that players can’t reach, reducing the overall complexity. |
| Overdraw | - Shows pixel overdraw.- Use this view to see where the same pixels are being drawn more than once in a scene so you can better optimize your world.- See the Overdraw view mode section for more information. |

## Keyboard shortcuts

These numeric keys provide shortcuts to the different view modes:

*   1: Shaded

*   2: Wireframe

*   3: Solid wireframe

*   4: Shaded wireframe

*   5: Collision

*   6: Overdraw

## Wireframe view mode

Wireframe view mode helps you see the geometric complexity of your 3D models. You can use this view mode to assess which 3D models should be simplified to make your world more performant if you’re running into performance issues.

### Use wireframe view mode to optimize your world

Wireframe view mode comes in three variants:

*   Wireframe.

*   Solid wireframe.

*   Shaded wireframe.

For reference, the screenshot below displays a scene in the default **Shaded view** mode:

![Default shaded view mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484854812_677084104829544_7156692161690434146_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=PYU15aShhvQQ7kNvwGlrpUL&_nc_oc=AdmdOwBVPDNIxT9P9TIbZlSg-DBPIpSlXizoFh7TaH2dKpDwzsQ82WPsILqOYrJj4hg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfQi_avtpPWYchPLvjPvx2rDmce9yr4RwUfT51Pbu1t9EA&oe=689BBC22) *Shaded (default) view mode.* **Wireframe view**

 mode allows you to see through 3D models to get a high level view of your world’s geometric complexity and identify unintended overlaps between models in your world.

![Wireframe view mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/485027199_677084101496211_3942768371206233632_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=Mdb1wCHS5cIQ7kNvwFnMui1&_nc_oc=AdmVvJleOEM2X7hmVWu3dtyyQ98keeIZgPTPx8A14APo06IvFUG_waJpltJ6VXwDaHU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfQkgorPstDrgGrPyYbXPv4G2cae5aH805OVu1j4ck8KQg&oe=689B959E) *Wireframe view mode.* **Solid wireframe view**

 mode places a solid material underneath the wireframe. Use this view mode to help you tell objects apart more clearly and distinguish which objects are closer to the camera while in wireframe view.

![Solid wireframe view mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484850704_677084091496212_497250801397507062_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=wm-wyizixh4Q7kNvwH6_BBS&_nc_oc=Adn4jvr8zvaiHxUsSZ2wybkUWG-3yH_P_Mcm9FEXbyYIrNz-CUyRSjKPJ4cVsGRx6aA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfTRtau1ireMP-TvN1JUeS3MQ05sGNaNnfeFLknZWWj-DQ&oe=689B9117) *Solid wireframe view mode.* **Shaded wireframe view**

 mode shows the object’s texture underneath the wireframe. Use this view mode to help you understand how textures are affected by their underlying 3D models and debug texture issues that may be caused by the meshes underneath them.

![Shaded wireframe view mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/485768707_677084114829543_6632284219993419295_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=NMPrMwOAXCEQ7kNvwFri9Ok&_nc_oc=AdndpFaRxz6ksrfp-SioWgNGnNByRcy7Zf936kSg4fhOj7ShNbe5OQT9WCnJ3n0a19U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfRzfUAbRAL82143mFQpOB64Bf4EBhzSb0Jcbzhz9BrZnQ&oe=689BAADB) *Shaded wireframe view mode.* ## Collision view mode **Collision view** mode helps you identify which objects in your world have colliders. Use this view mode to optimize your world’s performance by disabling colliders on objects that players can’t reach or resizing colliders only to where they are necessary.

### Use collision view mode to optimize your world

In collision view mode, colliders are visualized using a semi-transparent colored material.

![Collision view mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484831925_677084094829545_4062895164199937649_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=lFRcve4LmxcQ7kNvwHCD2bg&_nc_oc=AdkFHeC9d_Xis75RbZsWoWx3p0EOdxdo5QI2LyMGOGNMP5RE9seW_KZH9qyL8xLFHYQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfR9BK7ltHKDYE8Ybtpf7MHQ2UNVnUZ2G0fkhT1iwlRw6A&oe=689BB900) *Collision view mode.* ## Overdraw view mode **Overdraw view** mode helps you see where the same pixels are being drawn more than once in a scene so you can better optimize your world. Turning on overdraw view mode shows where meshes overlap so you can change, remove, or reposition geometries to make your world more performant.

### Use overdraw view mode to optimize your world

In overdraw view mode, you can see where geometries overlap the most in your world by looking for the areas that are most opaque. Each occurrence of overdraw is a place where unnecessary pixels are being drawn. You can optimize your world by modifying your meshes and optimizing your layout to minimize overdraw.

![Overdraw view mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484810609_677084108162877_6307321041192439066_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=36uMM4tygogQ7kNvwE0zzS3&_nc_oc=AdmlUmcv1pzoWwAU5F3Lm2RoLulKavT2ShOlf3WYWIh-ICh-4t3g__VfBtPbEp15rGQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=CiQBKVQo5CBRhCrixrVdYw&oh=00_AfQBY39K1xWKTdBwrZdpEulyWbKmdAqT6CtUFlZJSkGH8A&oe=689B900F)

*Overdraw view mode.*

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 