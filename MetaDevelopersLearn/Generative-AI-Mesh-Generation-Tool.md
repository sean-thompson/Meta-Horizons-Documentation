# Generative AI Mesh Generation Tool

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/generative-ai-creation-tools/generative-ai-mesh-generation-tool)

The Generative AI Mesh tool allows you to dynamically generate textured meshes that can then be added to your worlds asset library. This tool helps streamline the process of world and environment building by adding generated meshes of varying sizes & complexities. This document will cover how to:

*   Generated small, medium, or large meshes using the GenAI mesh tool

*   Save the generated asset to your library

*   Add the generated asset to your created world

Prerequisites

*   [Horizon Desktop editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor)
    
     installed on your PC

Gen AI Tool Availability & Rates

Horizon desktop editor creation tools with Gen AI are currently only available to users in the United States, Canada, and the United Kingdom (UK) aged 13+. Note that there are daily rate limits per user on content created using Gen AI. Additionally, there are daily rate limits per user on content created using Meta AI. These limits are:

*   Typescript - 1000 requests

*   Audio SFX/Ambient - 200 requests

*   Skybox Generation - 50 requests

*   Mesh Generation - 100 requests

## Generate a mesh with GenAI Mesh Generation tool

To access the Mesh Generation tool, open the **GenAI** panel from the top of your Horizon desktop editor.

![Gen AI 3d model selection](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490357659_695280506343237_5093771878172740662_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=FRE9mzEz48EQ7kNvwG4p2Qj&_nc_oc=AdkwZBWlNWqEmdJCgdBgZM9dv3RHZW84QC11hxx9tktKY-qs-w19MCB9lDNnpvpUHL4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BQwDdyuOKtGHc3Gtq0h-wQ&oh=00_AfQm6xQi1B7VdQNr9Upr7LjqnOWpYkJCZLFIaEz4jc9rJQ&oe=689B9AF7)

Then select the **3d model** option from the available generate options. After selecting the 3d model option, use the following process to generate a new mesh for your world:

*   Use the **Model Size** dropdown to select either **Small**, 
    
    **Medium**, or **Large**. The selected model size corresponds to the tricount of the generated mesh. The tricount is the number of triangles that make up the mesh. The larger the model size, the more triangles the mesh will have and, generally, the higher quality the mesh will be.

*   After selecting your model size, enter a prompt into the prompt field and click **Generate**. The prompt is a text description of the mesh you want to generate.

*   You will be presented with shape options that represent the final generated mesh. **Note**: This is a preview of possible generated mesh. Until you texture and save the model it will not be added to your asset library.

*   Mouse over the shape option you’d like to generate and select the **Texture this model**. 
    
    ![Gen AI 3d model preview](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490300393_695280499676571_3959979982196979589_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=D8qWmABvKawQ7kNvwE3w1w8&_nc_oc=AdmIzv_RN8ETqLrvJYqntKmSv-__iiCEI17r1Qhlt3LPL2EPKclGV8qOuZhjDRDBl9s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BQwDdyuOKtGHc3Gtq0h-wQ&oh=00_AfS9ClJzX1tD0VMKXLcxaizVG5DufcfGJbm9hwJB2KXIKA&oe=689B8A07) 

*   Once your mesh has finished generated, click **Save model**. The generated mesh will be added to your **My Assets** folder in your asset library in the **GenAI Assets** subfolder. 
    
    ![Gen AI textured model](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490607136_695280503009904_2242645863645606216_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=qsI1Ki5wRmYQ7kNvwHZp0h_&_nc_oc=AdmS_UG1sGfNL0Xrq6lsURJ-FL_SObK45vT2GsYqxbBrtUEC4aMdFsiGBFRSurTZNeg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BQwDdyuOKtGHc3Gtq0h-wQ&oh=00_AfQaC8Mp6iarvV4qf_6tLGAZIiYNACAlAzvn0W7TrxqcrQ&oe=689BB1C0) 

*   Your newly generated asset will be added to your assets folder. Once its added to your asset library you can drag it into your world, or double click the asset icon to add it to your world.

## Generate a mesh with Mesh Gen 1.1

Mesh Gen 1.1. offers an alternate workflow for generating 3D models for your world. With Mesh Gen 1.1 your prompt will result in the generation of a series of images, providing you with a range of options to choose from. From these generated images, you can select the specific one you’d like to see a 3D model generated from.

You can enable Mesh Gen 1.1 by selecting it from the **Generation Model** dropdown and selecting **Mesh Gen 1.1**.

![Gen AI Mesh Gen 1.1 selector](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506459548_743560904848530_3665626506441195556_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=ssSOBi-TMEoQ7kNvwEK1nZJ&_nc_oc=AdkhDGeaCGEyc0fHEaXcF01wAF_MBx09J_TrWDb9CHpq38A6bofqpdoiETp27lCNwEY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BQwDdyuOKtGHc3Gtq0h-wQ&oh=00_AfRkcn5hBIKrP5BFmD83CFs1y4TWgMusguvWsKXFTRob6w&oe=689B8508)

After selecting **Mesh Gen 1.1** use the following process to generate a new mesh for your world:

*   Use the **Model Size** dropdown to select either **Small**, 
    
    **Medium**, or **Large**. The selected model size corresponds to the tricount of the generated mesh. The tricount is the number of triangles that make up the mesh. The larger the model size, the more triangles the mesh will have and, generally, the higher quality the mesh will be.

*   After selecting your model size, enter a prompt into the prompt field and click **Generate**.

*   You will see some images generated for you based on your input prompt. You can select one or more of these images to generate a 3D model from. 
    
    ![Mesh Gen 1.1 generated images](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/508175988_743560901515197_9194637043231851125_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=q7QXGdj-7LAQ7kNvwH-Hbpn&_nc_oc=AdnYFNnj2rplCNz2367XQA7wRkfyB-ntO3mhHrmQVB_B8uk4FqAitjks6pTELxj-q-M&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BQwDdyuOKtGHc3Gtq0h-wQ&oh=00_AfRCpn7UMl3cO9_1KNIZ5YNXRV1dX2T_6JHXyLzyDQOtbg&oe=689B8DBD) 

*   To generate a 3D model of a generated image, hover your mouse over the image and select **Generate a model of this** on the image. 
    
    ![Mesh Gen 1.1 generate model](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/506435943_743560898181864_7519101096528438726_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=XZiOQie_MTIQ7kNvwGP_SFN&_nc_oc=AdlNpOXnP5O9DnLOdlNUvMiH5e50bbcq-i5ay8Ml1KrUrsp1GdWFX36OKDnbSjrMjV4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=BQwDdyuOKtGHc3Gtq0h-wQ&oh=00_AfTpvyZ-1YbSgzvQDPzI18-Uph8l-X8KT7voqXjtmJPVHQ&oe=689B8B83) 

*   Once your model has finished generating, you can click **Save model** to save the generated 3D model to your asset library. The generated 3D will be added to your **My Assets** folder in your asset library in the **GenAI Assets** subfolder.

*   Once saved and available you can drag your generated asset from the library into your world to spawn it.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 