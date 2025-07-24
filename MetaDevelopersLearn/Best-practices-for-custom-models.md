# Best practices for custom models

[source](https://developers.meta.com/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/best-practices)

## Performance information

Currently, custom model vertices increase the geometry complexity, but the limit might be tuned differently based on performance feedback. The amount of textures being used is currently not shown anywhere or capped. Visibility into this will come soon.

## Topology

Open edges are supported. Horizon doesn’t use double-sided shaders, so if you are creating objects with two sides, such as leaves, you will need to create polygons that face both directions.

### Modeling for vertex baked lighting

Horizon’s lighting solution (RTK) uses vertex colors to add lighting information to the scene. When modeling with this in mind, it becomes easy to visualize and control where light and shadow appear on the finished model once baked. The fidelity of the applied lighting is directly related to the density and placement of vertices.

It is important to plan your topology to support different lighting scenarios. Identify which parts are in shadow, and how that shadow transitions into light.

### Topology for GI artifact handling

| Topology creating GI artifacts | GI artifacts fixed with topology adjustment |
| --- | --- |
|  |  |
| Topology on custom models will sometimes produce artifacts when GI is calculated. This will cause extremely dark vertices when imported into Horizon. They will occur when a vertex is close to or snapped to another vertex or edge on a different contiguous mesh. | To remedy this when working with multiple contiguous meshes, place vertices toward the middle of intersecting faces. The image below shows an adjusted model, and no GI lighting artifacts. | **Problem** The top example shows how vertices can define light and shadow:

*   The Mesh on the top does not have enough vertices to define which areas are in light and which are affected by ambient occlusion.
    

*   The cubes on the end lack the vertices in the middle of the faces to assign a shadow color to it.
    

*   The center bar’s end vertices are inside the cubes, placing those in complete shadow. With no verts to interpolate into the light portion, the bar appears as if it is completely in shadow. **Solution:** The meshes in the bottom example solves this problem by adding in a vertex in the center of the cube sides where it intersects the bar to define the shadow. It places support loops on the center bar to define which area is in the light.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452945192_512500654621224_1117938882276573410_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=DeqfUyKNacIQ7kNvwGMaLTW&_nc_oc=AdnibukmybUa_gg9f8v1e7VMpNgRbY4gzpYUqtWFfNf6P7m9Bfrz7B7c4bfLe4dJFf4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfRXSZCh4jYCN-tdoB4mxlGdLkvmokru35YWashYzl-TEg&oe=689B9DF1)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452816787_512500667954556_7310310293534084824_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=hrhQlP2qw40Q7kNvwExQM2K&_nc_oc=AdlE10_BRsF5GuCKu7tpB58xpmHhrJR478qTBxiQJ8OE3JXa4vg1jFXbK0oSkXjtFb8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfQ_kBuykGkLEdvkQOlD_peUjGiy11Mr43Bsbk7i61gPtw&oe=689BBEBE)

## Scale

Build objects on real-world scales. Make sure that when you export your FBX, the units are set appropriately. **Houdini** \- Check “Convert Units” on the FBX export ROP. **Maya** \- There is a known scale issue where models will come in at the correct size but will have their transforms set to 0.01 scale.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452816154_512500651287891_9110139022826988635_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=wOwFzix73awQ7kNvwFMuOLI&_nc_oc=AdkhKHAWlXrkKsF3gfknIElgidZ5W7zP5Lx9om8PjZa8IuijlKcqiRBsBRCvV_G88JY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfTHZsuuAC9n_QgvZreLlf-Htzeje6r8aaf2m0-VlhHwsA&oe=689B8D1F)

## Pivots

When exporting a set of objects, we recommend setting their pivot correctly, centered at the bottom of each piece, or aligned in the same way that you would for a well-prepared game asset. **Tip**: currently, pivots will all become centered in Horizon, but this is something we plan to change in the future, so setting up your pivots correctly now could make these assets more useful in the future.

See the [Fallout 4 Modular Level Design](https://youtu.be/QBAM27YbKZg?t=422) talk for pivots, standardizing, and more tips around this.

## Remixability

Consider breaking your asset into pieces if those pieces would be useful for remixing.  However, if you aren’t planning on remixing an asset, it’s better optimized as a single piece. **Maya** \- Prior to exporting from Maya, you should group your kit, then arrange it in a way that is convenient to see and access all of the items in your kit. We recommend that the history is deleted and the transform is frozen.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915469_512500647954558_2366646221517633934_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=Fy8O3OvXAtUQ7kNvwHhlnfY&_nc_oc=AdmEfpLrvJaIQRnvK5dm52K7bsoWdJYNkf7mVsmDJvpqjj_Zsby2ldxpm98RPKsh9Jo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfQJ-AmslW0GeDyl5YLySf5T3JFHUMRzgCXiXNf5d7mJQA&oe=689B8E56)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452555349_512500607954562_5062833201515023605_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=NBC46WTq5cQQ7kNvwGhnOB3&_nc_oc=Adld3-bR0lPRAFkNbp9Ph5_43ZGYIVFBlmqWoE6Fbv88PAcneG-t8aBVJgFTMYTPBzE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfRGPyuwBSD75H2KwAwKK8Cy8hKI2GiAk3_tgjQ6bkTKzw&oe=689BB7B8)

## UV padding

Because we use the lowest mip size for coloring the bounce lighting information, there is a possibility that closely-packed UVs with strong color differences could cause incorrect color bouncing. If you have UV islands with strong color differences, you should use extra UV padding between those islands.

Minimum padding you should use for **large color differences**:

*   512 textures use 8 pixels.

*   1024 textures use 16 pixels.

*   2048 textures use 32 pixels.

## Texture style

Because the Quest 2 screens are high resolution, you can get extremely close to object surfaces. This makes it challenging for textures with fine details to remain good-looking when you are very close to them or they are very large. We recommend creating textures with less high-frequency detail, a style which holds up well in VR.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452704033_512500644621225_6271284546319336980_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=gEFIjd9SmmMQ7kNvwGciUQD&_nc_oc=AdkbVO-O8Nx6eOhvBDwGscLOsogt7qxfF8pKleES2l2WaIo_0J0voQTb44AJwsekZIM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfR7_0nShsfJLd4Uc5ciRrH9bJVfs9G520eLkmaIc_zdsQ&oe=689B9737) *High frequency detail.*![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915469_512500637954559_2669172308057156383_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=XeWbJZ6yu4IQ7kNvwHWfzZ9&_nc_oc=AdlA0xfPYQr_RNxbogyRoFLyDncVsa6Amj98z4lRqFP0C2m-BxelkPwA1Y4Mm_5Rj-o&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfRjLmo2tJNMqMIyOU20uxvkT-mRi1yNcKvSyZM2QVJB7w&oe=689BBBB9) *Lower frequency details look better close up in VR.* ## Model baking

Model baking is a common technique. Keep in mind that we currently do not support normal maps, so use geometry to convey information you typically might put into a normal map.  Using geometry instead of normals works very well in VR and gives you nicer kitbash piece intersections when laying out worlds.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452589309_512500544621235_5986002142499223076_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=yPLHsvbgaC8Q7kNvwFORili&_nc_oc=AdnicVf-jGvKoS9TLMwAJcY2HJAEIJcsLdBopVYHChLYQR1ZTP4KZdNYd-zdI2vosXs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfST9jcX839yGAByDd_G6u0SbRGFV6x_kQjIWKEt12Nn3A&oe=689BC3A1)

## Trim sheets

One of the best ways to optimize your textures is to use what are called trim-sheets, also known as artist-authored texture atlases. These are tiled strips of re-usable texture information that is assigned with UV coordinates onto different parts of the model.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452414106_512500551287901_1941084852038364963_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=cU2edmhBMFkQ7kNvwFo5u8q&_nc_oc=Adlwd37p0FagzcXBYVpQms17gjqOlw9T_1z447ynZhCLRIz75LO4kHg6PmwxdGu4v7o&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfRFWZ-grNMkhJ2nZjxrIiTF65la43XXptVsDPkjJm7OXA&oe=689B9ECB)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915713_512500664621223_893951861776114436_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=WNJbHTapGd4Q7kNvwFbsfin&_nc_oc=AdlcvCmb544I26IMHisdDDinYKb6tuhWtJX10r6j0fYypFEyWUg1aGaQaiPOF-RfvcY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfQek3j8nmaHZuaQmGLxUUT7GvDdfOnpveoaEuM786oXQA&oe=689B9262)

## When to use the Metalness Channel

Examples showing basecolor + roughness compared to basecolor + roughness + metalness. 

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452917873_512500657954557_8219246528713603699_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=5ZS_KzKnHEgQ7kNvwFM9eP_&_nc_oc=AdmvK2C3ivHqT4N-zn1yWFnsFCxYfJ-8i8LdfQlaVDVDFdQ-t2JF33lUD_uRyb2d6WE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfSfj0wBeHS6t1rELyK7PKHmA6ErrAW48EPexBsmAgbCDA&oe=689B94F0)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452684750_512500661287890_5145557696178384622_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=I9J8HdEpD_oQ7kNvwGWKibA&_nc_oc=AdlPocXVbRCNO4e9KmGtiZgmc4fxpGzcWsacGRbbUc_B0GOdgJiHE3_Gtmkly2bbkKk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=wV_TABV-sGb2-7wQ0WP-wA&oh=00_AfS_AcjF3e2Ce38GrsOnn8nj_y6bNcfoEPo6B0clL4M11g&oe=689B97E5)

## World budgets

### Runtime world budgets

It’s important to consider the world limits when designing assets. This will enable you to effectively allocate the total number of assets required for creating your world, and develop a comprehensive asset plan.  These limits are view dependent however there is no occlusion culling meaning the world limit can often approach view limit.

|  | Approximate limits for a gameplay heavy world | Maximums, when you have a more static world |
| --- | --- | --- |
| Total Vertices | 600,000 | 1 Million |
| Draw Calls | 150 | 250 |

### Travel time world budgets

These limits are designed to keep world travel times in check, especially for visitors with lower internet speeds.

|  | Download time | Download time |
| --- | --- | --- |
| Unique Vertices | 200k | 400k |
| Texture Megapixels | 40 megapixels | 80 megapixels |

1 megapixel = 1024 x 1024. (example 4 Megapixels = 2048 x 2048)

More megapixels means more time to load the textures, which may impact world travel times or take the world longer to look fully loaded. 40 Megapixels = 25 MB (ASTC 6x6).

### Generic asset recommendation

|  | Polygons | Vertices | Texture Size |
| --- | --- | --- | --- |
| 5 m3Object | 2000 | 1000 | 2048 x 2048 |
| 1 m3Object | 1000 | 500 | 512 x 512 |

This is a very general recommendation, and artists should adjust as needed.

## Model specification

A 3D model is made up of Mesh + Textures + Materials. **Note:** See [**Materials Specifications**](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/materials-guidance-and-reference-for-custom-models/) section for channel packing.

### Mesh recommendations

|  | Recommended |
| --- | --- |
| Formats | FBX |
| Naming | Avoid using these characters in your node & file names - .,, /, *, $, & |
| Objects | Multiple meshes per FBX file supported |
| Polygon Count | 12K recommended maximum, 400K maximum vertices. |
| Hierarchy | Flattened in Horizon* |
| Pivot Points | Centered on import* |
| Animation | Importing animation is not currently supported |
| UV Channel | Only UV channel 0 is used to map textures onto the mesh |
| Normals | Vertex normals are imported |

*subject to change in the future.

### Texture recommendations

PNG - 8 -bit per channel

See Material spec below for channel packing.

Horizon will support any power of 2 textures up to 4096 x 4096

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 