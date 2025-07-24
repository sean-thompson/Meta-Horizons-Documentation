# Manual Level of Detail Overview

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/help-and-reference/manual-level-of-detail-overview)

“Level of detail” describes the principle of having lower-detail versions of models in memory for an object and switching to those lower-detail models when the object is small or far away.

The manual level of detail (LOD) feature in Meta Horizon Worlds lets you use this principle to save GPU costs during rendering. With LOD you can create assets that contain multiple model files with different levels of detail and configure which model to render based on relative screen size. This allows you to create more complex worlds in Meta Horizon Worlds. **Note:** LOD only works in visit mode in worlds with Custom Model Import (tri-mesh) and cached global illumination (GI). In all other situations, LOD won’t be enabled, even if the assets are set up for LOD.

## How LOD improves performance

The current version of LOD is focused on improving GPU performance in worlds.

With LOD, you avoid overshading sub-pixel triangles by switching to a lower-detail version of the model. The tradeoff is that storing multiple models increases memory usage and size on disk. These increases are moderate and configurable based on the size of the additional models stored and how much they’re decimated.

## Prerequisites **Note:** The current LOD feature only works with Desktop Editor.

*   A Windows PC with [Meta Horizon Worlds desktop editor configured](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor/) *   A Windows PC with [Meta Horizon Worlds desktop editor configured](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor/) .

*   [Simplygon](https://www.simplygon.com/)
    
     software installed.
    
    *   This is required to import LOD assets and publish a world with LOD assets.

*   A Custom Model Import world running in edit mode in Desktop Editor to import LOD assets into.

### How to install Simplygon **Warning:** LOD asset import and GI lighting data generation require Simplygon. If Simplygon is not installed correctly, LOD import will fail and if a world has LOD objects, GI lighting data publishing will fail.

*   [Download](https://www.simplygon.com/Downloads)
    
     the installation file and run the installer.

*   Refer to the [Simplygon installation guide](https://documentation.simplygon.com/SimplygonSDK_10.0.1400.0/installation/default.html#download-installer) for installation details.

*   You’ll be prompted to install a license key.
    
    *   For 1P and 2P Studios, please reach out to [Alex Elsayad](mailto:alexelsayad@meta.com) , 
        
        [Deborah Guzman Barrios](mailto:debguzman@meta.com)
        
        , or [Travis Hoffstetter](mailto:thoffstetter@meta.com) to get a Meta license key.
    
    *   1P and 2P studios/creators can use Meta’s license key to use Simplygon under the following terms:
    
    ***NOTICE OF LICENSE RESTRICTION***
    
    ***The license key for Simplygon provided is strictly limited to use for the Horizon World project only. Any use of the license key for purposes other than the Horizon World project is expressly prohibited and constitutes a material breach of this agreement.***
    
    ***The user acknowledges and agrees that the license key may not be used for any other projects, products, or services, and may not be shared, transferred, or sublicensed to any third party without the prior written consent of Simplygon.***
    
    ***By using the license key, the user confirms its acceptance of these terms and conditions, and acknowledges that any unauthorized use of the license key may result in legal action, including but not limited to, injunctions and damages.***
    

*   After installing Simplygon, close all instances of Horizon, Unity, Hubbub or NuDevTools, and relaunch them as needed. If you see an asset ingestion error after closing and relaunching, try restarting your PC. See [Troubleshooting](/horizon-worlds/learn/documentation/desktop-editor/help-and-reference/manual-level-of-detail-overview#troubleshooting) for more information.

## Create and use LOD assets

### Demo video

Here is a demo video on how to use LOD.

### Sample assets

You can download sample assets to test LOD import from the links at the bottom of the page or from the links in the following table.

| Asset Name | LOD assets | Recommended relative screen size setting | Vertex | Texture assets | Notes |
| --- | --- | --- | --- | --- | --- |
| DamagedHelmet | DamagedHelmet_LOD0DamagedHelmet_LOD1DamagedHelmet_LOD2 | .3.1.01 | 1334157632208 | DamagedHelmet_BR.pngDamagedHelmet_MEO.png |  |
| Suzanne | Suzanne_LOD0Suzanne_LOD1Suzanne_LOD2 | .3.1.01 | 79582573909 | Suzanne_BR.pngSuzanne_MESA.png | Ignore import warnings. |
| StoneFloor | StoneFloor_LOD0StoneFloor_LOD1 | .3.01 | 1502266 | StoneFloor_BR.png |  |
| ColumnSetA | ColumnSetA_LOD0ColumnSetA_LOD1ColumnSetA_LOD2 | .5.3.1 | 765747332515 | ColumnSetA_BR.png | Use this asset to clearly view LOD switching. Use the recommended values on the “Recommended relative screen size setting” column. This asset has visual issues on purpose to facilitate the LOD switch viewing. |

## Ingest LOD Assets

### Create a folder

First, create a folder to store your ingested assets.

*   Click the **Assets** pane at the bottom of the editor. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452746635_512510217953601_3114243496821367227_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=nlD8A9xCE6QQ7kNvwGd2Gq5&_nc_oc=Adln5gXEEdVhgK7sJsWsGpgH2yFrz_Pskj4JK9iy6bmGctdqCYMw-d24vOoJoMRlIP8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfSUTVNjV_mGL_Ant1wvny-67nfIdtFc1AwMAJWfgY1XWw&oe=689BBAA2) 

*   Click **Add New > Folder** and give the folder a name. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452933706_512510127953610_2127077901733027775_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=akh3EPjnk6AQ7kNvwFofkMw&_nc_oc=AdkiakD8Nf9oTocGYo44_vnYmqpb_4nV5tb7ZdVcqijwICwfKE1Km7h7qxsT_4Wm67U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfSpzodg41KpzzSUmf6RrO6a4dNH8bIGGGqFkEev7QBLkA&oe=689B92A2) 

### Add your LOD 0 assets

> **Note:**
> 
>  The FBX file meshes for different LODs should reference the same textures.

Start by ingesting your most detailed model, called LOD 0, and textures.

*   Click **Add New > 3D Model**. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476358530_650633064141315_6123901305812892096_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=Q6Gx2mOFyZkQ7kNvwHYKQl8&_nc_oc=AdlHGMYFCccz76mSIVqdfb8p5StKcpB-ezXDfgdvaETbMMwr8WvC8DWL5LQ9BJsHpto&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfTsG5AeE83GolVU381w77CgrgnfFnPW2lYNpdk7qJjQAg&oe=689BAC9F) 

*   The mesh ingestion window will appear. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452672915_512510131286943_16962784959826029_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=6BSaGmodyGEQ7kNvwF1TaRN&_nc_oc=AdnbhZHFFKKqPEBlRYyqNfzara9CbOS7BFbX4B8efrKw3oBznKx9ykhN9we5E7rFU48&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfSogjAyM3j_0_7a19FThWlz3TgPJDCaVdx3PlF07tltwQ&oe=689BB64F) 

*   Click **Choose files on your device**, navigate to the folder with your assets, and select your LOD 0 model FBX file as well as your textures. Click **Open**.
    
    *   To select multiple files, hold Ctrl while clicking the files.
    
    *   If you’re using the test sample assets, select DamagedHelmet\_BR.png, DamagedHelmet\_MEO.png, and DamagedHelmet_LOD0.fbx. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452933706_512510087953614_3767056647331480894_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=YtRUGk8zh4YQ7kNvwEuSXma&_nc_oc=AdmNR4s4gvioA6glxYa8c9IAZcjlft_ZKiw8IJ1huKxGmWvr0yvmbl_bOSUB4YlNR2g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfQB1KzI5gxvNgIbFSir5ZZMjcN4fVv4-dt2UB3WkjVA4Q&oe=689BB357) 

*   The ingestion window should now show the files you selected. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452908638_512510097953613_7636898147610062708_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=KU-hk56vYUMQ7kNvwG6--C3&_nc_oc=Adl4DHy2NA7OXfQ-BeWeJMk89zEHDbVbqBxlgaxb04dPasQAZ8TXZDLdc4L2QCaJjEI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfR4yB4im-I9E3dFh8PejScNgwWFGUrjcBpV9IhB5c1fkw&oe=689B8752) 

At this point, you should have all the files you need to import a fully functional asset with only one level of detail. To add additional levels of detail, you must append more LOD assets to this 3D model.

When you import LOD meshes, they are appended to the MeshAsset containing the LOD 0 meshes. This means they will share the same materials used by the LOD 0 mesh asset.

### Append LOD assets

*   To append more LOD assets, expand the LOD 0 FBX file by clicking the expander arrow. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452946039_512510114620278_3499214126645664613_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=o7m2sKUhItYQ7kNvwEIJjVa&_nc_oc=AdmUOWWHg4bAGIOQq7B1P48ovL9JjkX1HZj9WolfVWF7uqcicFYxDIjugLwIdBYuYTs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfSC4phAAukxpMNOpjjvoKBv9qeTWRE_D2oQaMTRiUVyDw&oe=689B93B3) 

*   Click **Add LOD(s)**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452587898_512510111286945_6432106008314023031_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=oqo8tXORDtQQ7kNvwHEsi3N&_nc_oc=AdnYNaQ0P0yUGlt2jgPYK9Tj1Zhm1Rchl7oFqj80pt8tLQlwr6TRKpTtvctIhHVLVeI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfRoDOG9v6MTtmrrlIHaBR1eU1douTjr0bfAObrhysKnoQ&oe=689BA0AC)

*   In the file selection window, multi-select your additional LOD FBX model files then click **Open**.
    
    *   If you’re using the sample files, select DamagedHelmet\_LOD1.fbx and DamagedHelmet\_LOD2.fbx. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452772355_512510091286947_7590734842067493140_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=JA9wsiQtlTEQ7kNvwGLp2Ba&_nc_oc=AdlM7y2GYUvPJdwMdLvjPu8vzpUdeb2RZVtaK1McpnUOoxA4JiJJuIVbLjNHDwrFm1A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfRV-j6gZWevRlfrYjp2NQJfUhmLF5sXn0vHgwz02WHgrA&oe=689BAA17) 

*   The ingestion window should now also show the new LOD files. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452817871_512510214620268_3811525399855144317_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=jAhKwYkTWbwQ7kNvwGyI3bO&_nc_oc=AdmDQVooiyHg8OYo45YCBDBZ3dtsLNwJ1Wwt-sJ5I3y87Rmno_tNS5gXPSNZyyHXUVo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfR96CtVoUSInw77_J7qJo_9bB4tpJFaBimYNuMhmTZ9eQ&oe=689B87C3) 

*   Now, set the desired relative screen size for each LOD level. The relative screen size determines the threshold for each LOD level as a percentage of the full screen. When the object on the screen is smaller than this threshold percentage, the engine switches to the LOD mesh of the next LOD level.See the following example values for a more intuitive explanation:
    
    *   **LOD 0: .3**
        
         \- LOD 0 will be used when the object is larger than 30% of the full screen.
    
    *   **LOD 1: .1**
        
         \- LOD 1 will be used when the object is between 30% and 10% of the full screen.
    
    *   **LOD 2: .01**
        
         \- LOD 2 will be used when the object is between 10% and 1% of the full screen. - The object will be culled when smaller than 1% of the full screen.

*   Click **Import**. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452520181_512510207953602_2188403874289102963_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=PzKMqi3MxYUQ7kNvwFS642F&_nc_oc=Adm9fRSYzZxeygXKVsyNoqeb0tw40fKhMIJO_wpjPSMpNcSE8QgBc0yZTAg0opzfPsk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfRFV_3p-PnBCPLfAJMYPRmQrNggYykaN0T2JDto7iUSnQ&oe=689B9BF5) 

*   Wait for the importing process to be finished. You may see a clock icon on the top right of the asset icon. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452520043_512510204620269_1030569126414916300_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=X4WYNffJHqwQ7kNvwEEh9Cw&_nc_oc=Adkfcu3lPN2jNXUgg1xCBrz8Y2TQvLRHOg9dERSlXA_4x4XE8lQ2ZiHIk-HJ4M8ZjeI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfTC0lwcSm1TPYRg5br6sYIEYN8w4ybt_AlKfVYQbuTGWw&oe=689BB065)
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452746741_512510201286936_7556625726474085776_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=VV49VdFaJf4Q7kNvwE5KRO3&_nc_oc=AdnEN1uO_bmsmTmUg3dLAGxqkiXKCTp0etvGK7aHkVV5w1n2KFqFU99Odd9iKwpnAFo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfT-pKxQhGr85JnBmvHp3stlHg0Hdbcqdf-fy-0qoFt13Q&oe=689BB9AF) 

*   When the import finishes, a “Success” banner will appear. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653243_512510197953603_4225377072029174481_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=asQwwmspAIYQ7kNvwE9jDEW&_nc_oc=AdldlJvMerSI3ULLTca78QSfD5x1Rmy_N905srmWu6jYXSRn38-Ao7xXhtx_MQtvILw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfTw6t8xzk04JtqBs6RaU0r6LzxT2qM0AUsiKDyLrm9JRA&oe=689BBBF9) 

> **Note:**
> 
>  When importing FBX files containing multiple meshes, the system will try to match LOD meshes to the LOD 0 mesh by node name matching.

> **Note:**
> 
>  It’s possible to import different types of meshes to an LOD if you also add the dependent textures. This can be useful for testing LOD switching.

### Add an LOD asset to your world

To use an LOD asset, drag the asset to the world window.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452578653_512510141286942_8187160058036161687_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=osstlzc0w54Q7kNvwEbakUj&_nc_oc=AdmQPksct8uncySOqQ_AgpfCGePD9mgAB3d6sw3A4hzjIHjWUUjusEPr4NxUDqOjHRQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfTO89P-pCzw5jdJAVAsZhHtwA1uJMKfM9jG4yZprOpkSQ&oe=689B9363)

If the object is too far from the view point, it may have a green color. This is because the additional LOD level GI is being computed in the background and isn’t ready yet. You can move the object around in the world before the GI data is computed.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452513309_512510124620277_672843571951153038_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=_nCbOU3IUOQQ7kNvwGEXJDo&_nc_oc=AdklhR8G9KvQa46KtrYKQDlNMFhpzxPjQG5x6Qu42hRvXSwj_8dU8QTgSIaaz6BL6B0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfRLEFTqfF3bMJkNJLukQ79DLbcO1o6MMELjj1dnRYuS8A&oe=689BB712)

You can verify that LOD is working by moving around in the world to make the object take up different amounts of space on your screen and watching as different LOD models populate.

It can be hard to notice this happening if the relative screen size values are small. If you move far away from the object, eventually it will be culled.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452587746_512510134620276_9189181265092177001_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=C6V89A0gS2cQ7kNvwFBIbrj&_nc_oc=Adkk9zH9KiRnY4ZEKl-pLmn4QjqHsg3ntMugXml9G1o0wWJoJXXpO5fk9y9qdVWSlYE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfTDfwHS1w1enD-Kd-DeU8oulLQ7SbXWrd24RjzLCoYetg&oe=689B9B2A)

You can also see LOD behavior in Desktop Editor’s preview mode.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452590061_512510137953609_1190235246472948998_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=uNm0oUaR6PkQ7kNvwFx9Bpp&_nc_oc=AdmUcwGwKaFUgGvaftamEj4Pc5tNFBijQxrfgV-HeELC_z9VcHKCzCqEdy08KBH2BJQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=m5SPatzw2O2DBS73sMOsuw&oh=00_AfTs92L9vuMNmnSqI3oeI9RpEYdfML0GEXQkAM2B5z4aLg&oe=689B94DF)

### Publish the world

To publish a world with LOD assets, you must publish the world from the PC with Simplygon installed. The web or VR flow can’t generate GI data for the LOD assets, and LOD objects will be disabled if you publish your world from web or VR..

When publishing a world with LOD assets and objects, the publishing process may take longer, between 30 seconds to a few minutes.

Then wait for the publish process to finish. Depending on how many objects and LOD assets are in the world, this process could take anywhere from 30 sec to a few minutes.

## Current limitations

*   The LOD asset has to be re-ingested to change LOD parameters.

*   There’s no LOD property TUI, so after placing assets in a scene, there’s no direct way to tell whether the asset contains LOD meshes.

*   If an FBX file has multiple nodes (thus multiple meshes), all of the nodes will use the same relative screen size value.

## Troubleshooting **If you can’t ingest LOD models, but ingesting a single FBX file works:** This seems to be related to the Simplygon installation. After installing Simplygon, close all instances of NDT, Unity, Hubbub, etc. and try restarting your PC.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 