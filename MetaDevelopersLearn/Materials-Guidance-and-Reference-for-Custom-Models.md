# Materials Guidance and Reference for Custom Models

[source](https://developers.meta.com/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/materials-guidance-and-reference-for-custom-models)

A [mesh](https://en.wikipedia.org/wiki/Polygon_mesh) is a collection of vertices, edges, and faces that define the shape of a 3D object. In Meta Horizon Worlds, meshes are used to create objects such as buildings, terrain features, or decorative elements. Materials define the visual appearance of these 3D objects by specifying colors, textures, and other properties that are mapped onto them.

## Defining materials in the FBX file

A material is a set of properties that define how an object responds to light. A material specifies the way that the object reflects, absorbs, and transmits light. You can think of materials as the “paint” that you apply to the surface of an object. Materials can have various properties such as color, reflectivity, transparency, and roughness.

You can assign multiple materials per mesh in the FBX file, and multiple FBX meshes can share the same material. For more information, see [Multiple Materials per Mesh](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/multiple-materials-per-mesh) .

## Filename Criteria

*   Avoid using these characters in your file names -, ., , /, *, $, &

*   Avoid using underscores “_” in your material and texture names, except to designate special tags like _Metal.
    
    *   👎 Dont\_Name\_Like\_This\_BR.png.
    
    *   ✅ NameLikeThisInstead_BR.png.

## Texture and materials reference

### Single-Texture PBR

The PBR (Physical Based Rendering) material for a single texture combines the base color and roughness. Metalness will be set to 0.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BR.png | BaseColor (sRGB) + Roughness (linear) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Single-Texture Metal PBR

Single-texture metal PBR material combines the base color and roughness. Material names must end in “_Metal”. This part of the material name is not reflected in the texture matching. Metalness will be set to 1.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BR.png | BaseColor (sRGB) + Roughness (linear) + Metalness |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Double-Texture PBR

Using two textures gives control over more of the PBR properties.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BR.png | BaseColor (sRGB) + Roughness (linear) |
| Texture B | MyMaterialName_MEO.png | Metalness + Emissive + AmbOcclusion (all linear) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Unlit Materials

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452746741_512510151286941_7543427180543090042_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=Tfsz0pzj7koQ7kNvwHa1Zra&_nc_oc=Adl5ejDnZ0srV-8R02AZGKs5YVJMctW8ehEQcY6RzGVhZJf8kC-z5Sv-zRAwjcXJdG4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfS-jA3KJW-m3RtgiGi8m_0Nk8pO10pRNsYCoAN8f-4qUg&oe=689B9CBB)

Materials that do not receive or cast lighting or shading are considered unlit. The material name in the FBX must end in “_Unlit”. Any extra channels, such as the fourth channel, are discarded.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_B.png | BaseColor (sRGB) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Unlit Blend Materials

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452955733_512510171286939_5181638036183860130_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=Tx04-o74igEQ7kNvwF2Px7x&_nc_oc=AdkPfoh4B8bGagy0-GAavOmYSDaobpSS8A6j_A85eEpAG1ozuZypuBrA9KG7gujfUGA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfTGIjbPEOGnbg7D4jjakaDU9TOo8cYaglJXcW2PZF0OvA&oe=689B8D37)

Blended materials that do not receive or cast lighting or shading are considered blended and unlit. The material name in the FBX must end in “_Blend”. Unlit blended materials do not have any specular or reflection properties.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BA.png | BaseColor (sRGB) + Alpha (opacity) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Transparent Materials

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452522449_512510154620274_2357687186968881662_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=nGCTxVo7dzwQ7kNvwGYaySt&_nc_oc=AdmbGX6d79C_4Mnsp7LVvqTfCBEG527aDlzYPBFhtna4SL1rCid3rROwKbugybgcNMM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfTabJ3IHymv7d3fLJsSasw3Par6ZyXXjoF3Fd9Tv7P42g&oe=689B95B8)

Transparent materials allow light to pass through. A specular channel is used, which modulates specular and reflection amounts. Using two textures gives control over more of the PBR properties. Material name in FBX must end in “_Transparent”

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BR.png | BaseColor (sRGB) + Roughness (linear) |
| Texture B | MyMaterialName_MESA.png | Metal, Emissive, Specular, Alpha (aka inverse of Transparency) (linear) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Masked Materials

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452635163_512510161286940_8652445767142113425_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=Xk4R1y_L7oYQ7kNvwFZGZxp&_nc_oc=AdnhDES6cnVkDXZ5U7992Su5Mlm-woUZaXLfBm_FG8yQxYK85KcZnv93BvS7AdI6vrI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfRo1D_o8fHgJ5xozSDbgpIKUPJ_z0h-5_bQZgZx0MAsjQ&oe=689BBFC2)

Masked materials are used for controlling the mixing of two textures. The material does respond to specular and roughness properties, but is considered fully rough; i.e., roughness = 1. The A channel of the texture drives the alpha, where white is opaque and black is clear. Alpha cutout happens at 0.5 (matching the default for GLTF 2.0 and Unity). Material names in FBX must end in “_Masked”.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BA.png | BaseColor (sRGB) + Alpha (aka inverse of Transparency) (linear) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Vertex Color PBR

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452846268_512510174620272_2366064968037736374_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=JcV6wvNgMdUQ7kNvwHeGLrd&_nc_oc=AdnIuM-mjM1NlIGA16GOgbFiido4FERkmfKj95S5OqdRJjPBmIM1r-qOTdWPCUghiBY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfRe_TM-cShytilUhbQnDofPstSzNAub6FVD1nA17yDT4g&oe=689BAD83)

Vertex colors are RGBA values that are applied directly to mesh vertices. They do not contain any textures. You can use vertex color for:

*   Simple clean objects.

*   Objects that just need simple gradients or colors.

*   Simple landscapes

A material name in the FBX must end in “_VXC”.

### Vertex Color Single-Texture PBR

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452522576_512510164620273_7391129338506219413_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=kzt2ib_t9J8Q7kNvwE-qkzR&_nc_oc=AdlN28a2MC5Bs4yzulj9aPx97Hgwf3F-8_uNzhbk6HEtgzUbuOop-akxI3kWWTVxIUM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfRp7BrUo9qMSEFuTZ4TN3cOtbN0mrWNcnTqSWaUyG_xTw&oe=689BC322)

Vertex colors are RGBA values that are applied directly to mesh vertices and then multiplied with a texture **BaseColor** as input to both GI and shading. You can use vertex color for:

*   Allowing more texture reuse across similar surfaces with different colors.

*   Layering broad color and value changes.

Metalness will be set to 0.

A material name in the FBX must end in “_VXM”.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BR.png | BaseColor (sRGB) + Roughness (linear) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### Vertex Color Double-Texture PBR

The Vertex Color Double-Texture PBR material is the same as the single-texture version but uses two textures to give more control over the PBR properties, in the same way as the regular texture PBR, but applied to vertices. Vertex color is **multiplied** with texture BaseColor as input to both GI and shading. Using two textures gives control over more of the PBR properties

Material names in FBX must end in “_VXM”.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BR.png | BaseColor (sRGB) + Roughness (linear) |
| Texture B | MyMaterialName_MEO.png | Metalness + Emissive + AmbOcclusion (all linear) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

### UI Optimized Materials

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452541679_512510181286938_784385883995309106_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=938C3YZ_LzoQ7kNvwHqpNaI&_nc_oc=AdlppAfo5bkHTVaIjPEvEuUTLvLc8v_b-yQEMac_RCZgD_U88EqF38BU-JrWLH9cN2U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=OOAB7qaQgBL4ta_tfpRSYg&oh=00_AfQXu4bmJq6Se3cm7_HGlTYd8VlV3bi9WSLHRYnJWlhL8g&oe=689BB9F3)

UI Optimized Materials are optimized to provide better quality UI elements (e.g. text, icon) when displayed. These textures are unlit and do not receive or cast lighting or shading.

Material names in FBX must end in “_UIO”.

|  | Naming | Channels |
| --- | --- | --- |
| Texture A | MyMaterialName_BA.png | BaseColor (sRGB) + Alpha (opacity) |

**Note:** *MyMaterialName* is a placeholder for the name of the material the texture applies to.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 