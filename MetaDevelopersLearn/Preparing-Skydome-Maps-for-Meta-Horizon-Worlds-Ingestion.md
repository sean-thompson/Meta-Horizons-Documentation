# Preparing Skydome Maps for Meta Horizon Worlds Ingestion

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/preparing-skydome-maps-for-horizon-worlds-ingestion)

This section describes the requirements and process for building custom skydome maps for ingestion into Meta Horizon Worlds for use in your worlds.

## Skydome Asset Requirements

To upload a custom skydome, you must build the following art assets, listed below in the supported format(s).

*   High Resolution Display Cubemap ( `PNG` )
    
    *   The high-resolution display map must be an equirectangular/latlong source asset.
    
    *   This asset must be converted to a horizontal strip through your source application.

*   Radiance Map ( `PNG` or `EXR` )

*   Reflection Map ( `EXR` )

*   Fog Map ( `EXR` )

For more information on the requirements for each asset type, please see “Appendix: Skydome Map Reference” below. **Tip**: You can also download a pre-made assets to upload into Meta Horizon Worlds. See “Download” below.

## Limitations

*   Skybox textures must meet the exact dimensions and type as noted in the UI. Using textures with any other dimensions causes failures.

*   You cannot re-upload the skybox textures individually. You must make a new asset or use the Replace Asset feature.

*   You cannot spawn a skydome asset via TypeScript.

*   Reflection Map assets must be in `EXR` format. `PNG` is not supported.

## Import Skydome into Horizon

After you have prepared assets, the following steps walk through how to create a skydome asset:

*   Open a world in the desktop editor.

*   Click the **Asset Library tab** at the bottom of the screen: 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/487315635_686408220563799_5263085594883600351_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ba28QK5wgbIQ7kNvwHLJSAN&_nc_oc=Adnf_y3yM-rIo0uk-9VIEp__l4SjXw98rNIOTtH1aJpyUNnrcBmwlDnV4Ti41l2TGGY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfTg6aaTzhzJS1KXhTnNOaShniPCuGkIDeQsYMm62DD4SA&oe=689B97B5) 

*   In the Asset Library tab, navigate your folder structure to select the folder where you wish to store the uploaded skydome.

*   To begin, click **Add New > Skydome**: 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/488231531_686408263897128_267682368947112974_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=4vQXNwoobukQ7kNvwHNdjkb&_nc_oc=AdnkTgGJzNaC-BiLTCw7c3hNg8EOSHpFuq6ERiLrmynCYPKyHjIWY-5supUjjvR5kAM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfSSdYm9CMO5uErC0ZFeFgjAoGLO8SOoWxsvNTZ_iEk2eQ&oe=689BB2B6) 

*   Select the art assets that you wish to upload for each of the skydome texture types. Please verify that all assets are in the file format and dimensions listed in the window: 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468360191_598700739334548_8198028015957139387_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=KSIcKSSYpzYQ7kNvwEHZhVg&_nc_oc=AdlsI-ylCF_6dBYvIHdZa3f84w-o4ML-FY3onNe1g_8MCvsI3MBA3GEJa_Tcvxomz0Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfSLwEx2seiNIwp1o4C9tqOau9SDGVc6Zfb3s1zbh3pSOA&oe=689BA97D) 

*   Click **Next**. The selected assets are displayed: 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468186265_598700746001214_8715326753450651892_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=Uysn5YkeHDAQ7kNvwEk8rFH&_nc_oc=AdnBPebXLzQI4KWsgJYbY0dtlDnCxcMLcR6CKVOPQrUogz2V4DNbP-cAuwmHtpT6ABo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfS1zYybU5nY77zpVQjIqPPsoWIP0Mgv27iVDBkdI08dfA&oe=689BBCE5) 

*   Click **Next**. Enter the Name and Description for the skydome. To start creating the asset, click **Done**:

*   The asset is created. This process may take a minute or two to complete. Do not navigate away from the world or create a second skydome until the process has completed.

*   After the asset is created, it is displayed in the Asset Lbrary tab in the folder that you selected for import. 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/488180665_686408260563795_2352765188487960497_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=Aa1L5UycGQMQ7kNvwHTLCiD&_nc_oc=AdlyxjPu0Tt1sX_4mRSkD0HtSJDKOBokgDsvM6uZ4Xusek0I9-ddlkno4gfNFUaLvyk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfShAOIH922X0l8dH1-824wmr_yexFokGi46MKLI0HQ6kw&oe=689B9CFA) 

## Deploy Skydome to Worlds

After you have created the custom skydome asset, you can deploy it into your world. **Note**: This process creates a new instance of the Environment gizmo mapped to the custom skydome asset. If you already have an Environment gizmo in your world, you may need to port its settings to the new one that you create here.

*   In the Asset Library tab, locate the skydome asset that you created. Right-click the asset and select **Place**. You may also click and drag it into your world. 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/488538474_686408223897132_1051437652716361373_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=VBCmpqS4mBIQ7kNvwFwFDaG&_nc_oc=AdmEywSoeGaa3QPTvO2hwUrIeNzZFmsGP64I7PyVk9yIL2-KqgGxKO_GkjtKDPj88gg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfSqDqn7Vv1MuD6kW-mhUEXsMYCZTeRPptBSmS18WcqhyQ&oe=689B9CFB) 

*   An instance of the Environment gizmo is created in the world, and the skydome in the world now matches the one that you uploaded. **Note**: Initially, the skydome is displayed at a lower resolution unitl the high-resolution display finishes downloading. 
    
    ![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/487303222_686408197230468_6006533098210667677_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=T69C03XjENIQ7kNvwFmjjWA&_nc_oc=Adm-uV52ZF9q14NMoutn1ChASqYUwNR-4zPVBruySkgxPeJfegWrvna20X1_E5ycg3c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfRwAWf01BYpdlkTrdqYxhlkvOhIHb2OM6kG09AF-pRESQ&oe=689B8804) 

*   Your custom skydome is displayed when you re-enter the world in the Desktop Editor or, after publication, in Visit mode on a supported device.

## Download Example Assets

You can download example assets for building a custom skydome: **Download**: [SkydomeCustomSkydomeTestAssets.zip](https://scontent.oculuscdn.com/v/t64.5771-25/75375772_2364431677244731_586874341463105764_n.zip?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=XYTwnL9TcN4Q7kNvwEWYD_N&_nc_oc=AdnlGcMK-6qB-j-Vyz9PxFxRfKAvxnZwbTeEBiNy1Iow2i__2r_gAP_mWg3DR7dLozQ&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfSWlzOG8GicqHIfGyVB5taEdy6laSRUzaL4NleR-ojfPA&oe=689BB4DA) ## Appendix: Skydome Map Reference

This section contains reference information on the types of assets that you must generate to create a custom skydome.

### High Resolution Display Map

The High Resolution Display Map is a high-res display of the world background after it has been downloaded from the CDN. At world startup, this download process may take a few seconds, during which a low-resolution display map is shown to visitors. **Tip**: During the upload process, the low-resolution map is generated from the high-resolution map that is uploaded. You do not have to create this asset.

This map is just for display purposes. It is not fed into lighting, fog, and reflection calculations.

#### Format **Horizontal Strip**: 6144 x 1024 pixels

![Horizontal strip layout and example display map](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452589609_512527431285213_7230044182276876243_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=6hLSHuSeFdYQ7kNvwGIj8nK&_nc_oc=AdmQCqlezOm8IOwPYhHZKdYj_MipXZx6OgEdrhtm6BxMD2L4PASGvEeIEhpoE_h4oog&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfT7BPdJ_l9IROS0ZCzMlXlQPPexB_kQwdWf3CDHtWptpg&oe=689BA109)

#### Preparing Image Source

The skydome can be drawn or created via any image software: 1. The high-resolution display map must be an equirectangular/latlong source asset. 1. This asset must be converted to a horizontal strip through your source application.

For import, its format must be **horizontal strip**: 6144 x 1024 pixels in `PNG` file format. This format is recommended because it is compresses well and is more performant.

Horizon Unity import settings:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452694607_512527321285224_7673882326822973083_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=O_8dL0Eltu8Q7kNvwFFrW46&_nc_oc=Adn2erUgTwBOc21EITMfU6phYZ8k_9RTx6IIGKgt5jpnEu4CK9-8joI-Xrh8nO2JV2Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfQAJNxh3gunZJr_FsnjZtJ85Q_rD1kHBu0TyZTYqyYxLg&oe=689B8B32)

#### Example: High-Res Display Map

Captured:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452673570_512527417951881_7382506179030491379_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=1JvvE4W9Hf4Q7kNvwHzi1bq&_nc_oc=AdmyglGQhIMdbyk0cqvG8jR-FgNxKX474sXq0LJKwnE57ZPoIhIYmSL1XhhltMiVL3U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfREnovoa0-HKrczzblfpYwUeYz_c_RMd0hR4Fe6H3sj-g&oe=689BB089)

Drawn:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452881671_512527384618551_263665835944063482_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=b8asT56y7-wQ7kNvwGAAxon&_nc_oc=AdkHvpcppSBf3LvwJ-8MwaUoqhCJ0FxbyWQy7n2BqGqUjaOPF_k40Q3an_QVuUJn-u0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfQGwezEGVEDeu0NeaOVXFI_REZEqiNAaohBemIwRRCTOw&oe=689B9073)

#### Recommendations

You can preview your maps using [Unity skybox](https://github.com/TwoTailsGames/Unity-Built-in-Shaders/blob/master/DefaultResourcesExtra/Skybox-Cubed.shader) prior to ingestion to fix any image errors like seams, pinching, noise, and banding. See below.

Pinching example:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452616361_512527381285218_995271016706393099_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=O0POvWwfEKkQ7kNvwHxhysa&_nc_oc=Adl5lsH88eUNVQLUP17BvDcXg56H7y_bgnTTA3EarsvDI1KaQ2wQfQvE1s7JxKIiaXk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfRVehVfUgmaCc-OzOU-QIKm0IX4JfqJBfl88r-R4NJgwA&oe=689BA51E)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452830189_512527367951886_1040209433688152179_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=V_ndAFLcEUEQ7kNvwEF97Z7&_nc_oc=Adn6ugXB2Y9krummfEF4_b2QYCaJNy1OxxsvTmGJkf5bz5cG2Pu00svnkQ5wusxSSwU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfRz60uR_Y9WzIuMi1C4SDDQEPSMzhiklCYkjqzqojbHTA&oe=689BB69C)

Seam example:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452888902_512527284618561_7166563455042073515_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=jfXkjSnNBSoQ7kNvwE9Byyc&_nc_oc=AdkY1h1dP7PscV2_bUTt-PAlRR7E5TfdUkZdCs-7kB-XUbyGIEkBtTiNPRe30952Mdo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfSnMGdJp8X3_ljazgE7iEMfwcnlOrPOcbu9N1yah3t4kg&oe=689BBF2D)

Noise example:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452942918_512527364618553_711412972350669946_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=ICBpN8Do7WkQ7kNvwG7QEmE&_nc_oc=Adl5SvakhqqUEBYsULUu9SUJqBaZZABzXzUryg0xER5YPki2yayUMRJrfdjHC1ZFYKE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfQxUXbP2w1iC8bxUzuGq2kiyw8a_uJoT7EvVriaDsHQmg&oe=689BAAC9) **Note**: Use [Nuke denoise](https://learn.foundry.com/nuke/content/comp_environment/denoise/removing_noise_denoise.html) to remove noise.

### Radiance Map

A radiance map is used for image-based lighting (IBL). A radiance map simulates how the sky lights up a 3D scene. It captures the intensity and color of the ambient light emitted from skydome. The radiance map is used for calculating global illumination.

#### Format

Radiance map is an **equirect** version of the display map.

*   The format is **equirect** 256x128.

*   Radiance map can be either `PNG` or `EXR`. Use an `EXR` file if you have HDR values in the radiance map. Otherwise, use a `PNG` file.

You can create a radiance map based on the display map.

*   Convert a copy of the file to **equirect** format.

*   Resize to 256 x 128.

#### Example: Radiance Map

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452540567_512527344618555_6504198765252610258_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=6Klv9klFaiMQ7kNvwFz1qpG&_nc_oc=Adk2NEIcr9Ml9XhH230s5uPFHwUq6o2bboNTGCQQtJptaTAMvi-m4eVtDkcbMuV6wB8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfS22OSFMKpJuBzZmvKaf8K5Pg0LR0p5eeNaP-eNOlZMcQ&oe=689BA147)

### Fog Map

A **fog map** adds atmospheric particle density to your world. **Note**: A fog map applies color to meshes. It does not apply to the high resolution display map. Fog maps aren’t related to cached global illumination.

For greater distances between camera and mesh, the further away, the mesh is more tinted by the fog map. It’s a non-linear gradual change. **Tip**: In the Environment gizmo, which is created when you add a custom skydome to your world, you can choose to override the fog map by a constant color, which provides realtime feedback on the fogging effect. You can also build a fog map that is composed of a single color.

#### Format

The format of the Fog map is the following:

*   a **horizontal strip**: 384 x 64.

*   A fog map shouldn’t have any near/middle/far ground geometries, just the sky.

*   Fog maps are `EXR` format only. Do not use a `PNG`, which yields poor results.

#### Example: Fog Map

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452514532_512527341285222_4650434737246338516_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=BK6nTsR7_swQ7kNvwG-YaHU&_nc_oc=AdlZ5Y34TMOY73BWsrSe1Fr9-3lippMmE2KXa-wDP1dXtjPvMCKUc0I3voXooK162OA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfTEH4JzDsj77A0BgUl2aYr7ZHTtG4xwezDBJPxZhZDNRA&oe=689B8FC1)

### Reflection Map

A Reflection Map is used for reflection probing and providing view-dependent reflection.

#### Format

*   File format should be a 768 x 256 [convolution](https://learnopengl.com/PBR/IBL/Specular-IBL) mipmaps (8 mip levels) sheet.

*   Use an `EXR` file if you have HDR values in the reflection map. Otherwise, use a `PNG` file.

#### Examples: Reflection Maps

Many skydomes in Meta Horizon Worlds reuse this image because it creates a nice reflection for metallic objects, but it doesn’t represent the world in a physically accurate way.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653302_512527424618547_195787883060786723_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=pIhH0lOdRlsQ7kNvwF_-TXZ&_nc_oc=AdmScyBjKmAPL0wYDQZFuhmO6y-WdLwNVzLUJ-CpnfqZYxPNd57nEwBKvf4D7vnekAU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFYhPL5WdJhdMsiIaW9HjQ&oh=00_AfQh_L5At9cbE6CgCZP53Etm_LTdzbdEcFpcveMuVIPdQw&oe=689B9859)

Ideally, you can create a mip a mipmap sheet from a horizontal strip display map, which is more accurate than using the default reflection map from the above example.

In the above example, the default reflection map has some hot spots which produce a nice shiny look, especially on metallic objects. If the reflection map doesn’t have hot spots, the metallic objects look less shiny than using the default reflection map.

However, to get the most PBR accurate reflection, you must re-capture the world with all geometries and the new skydome, and then generate a [convolution](https://learnopengl.com/PBR/IBL/Specular-IBL) mipmaps sheet based on roughness.

### More examples

Below you can see some example images of the custom skydome assets. **Note**: These assets are not suitable for import. They are provided for display purposes only.

|  | Skydome | Radiance Map | Fog Map |
| --- | --- | --- | --- |
| Daytime |  |  |  |
| Misty Marsh |  |  |  |
| Sunrise |  |  |  |
| Midnight Black |  |  |  |
| Night |  |  |  |
| Overcast |  |  |  |
| Sunset |  |  |  |
| Twilight |  |  |  |
| Winter |  |  |  |

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 