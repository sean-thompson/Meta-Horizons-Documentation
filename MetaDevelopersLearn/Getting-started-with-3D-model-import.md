# Getting started with 3D model import

[source](https://developers.meta.com/horizon-worlds/learn/documentation/custom-model-import/getting-started-with-custom-model-import)

## Custom model files

A custom 3D model is composed of multiple files, all of them must be specified when importing a 3D model into the desktop editor. The files include:

*   An [FBX](https://en.wikipedia.org/wiki/FBX) file. This is the 3D model file format. It contains the 3D mesh along with scene data such as cameras, lighting, geometry, materials, and animations.
    

*   One or more [PNG](https://en.wikipedia.org/wiki/PNG) files. These are image files, containing textures that map onto the model to make the spawned object look more realistic.
    

For example, you need to import five files in order to import this rifle asset:

![Image shows a 3D model of a futuristic rifle](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/469383086_604977648706857_1533817991015737609_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Pt_kug3cRuQQ7kNvwG15Ig4&_nc_oc=Adka6rZ3T85t9GHeoTBi7Kxio5JNjW3Hw7alU_OYgx4YuRzpuVeVTXNiSVeXsAfsuMg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=tEahqDfMO5UhejX9fRV5-g&oh=00_AfQjIVr9hN9-SS1-LX6giGZFu_oV_G_TkQAkn3D3s4a58g&oe=689BB82A)

## Import a custom model asset

Follow this procedure to import a custom model asset, spawn an object from it, and add it to your scene. **Note**: To complete this procedure, you need a custom 3D model (an FBX file and one or more PNG texture files) to import. If you don’t have a 3D model, you can get demo assets [here](https://scontent.oculuscdn.com/v/t64.5771-25/57572945_551676440543626_8228778286502058757_n.zip?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=-DpaYKb5tGkQ7kNvwEZcYs6&_nc_oc=AdnSsPHGkXyw5HF8l2tyR-fdfg41V1y93G0cyEypLWgFGDdBrashPGI84YZMzDKttzc&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfRo3lk6KJOUZqsgjiEFp4T5IknT-ZE3WNbH4RTBMp0BEQ&oe=689BAB45) .

*   From the Desktop Editor, click the **Asset Library** tab at the bottom of the screen and select **My Assets**.
    
    ![Click on the Asset Library tab to open the Personal Asset Library](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/463982802_573870205150935_1936916611175683589_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=ImzKTcFOmvUQ7kNvwHcBjbc&_nc_oc=AdlW42Pr2a8O8xeahR7nPR1qLpq0U5Gq7_jScE-NBKpaSK009yGzhvtj7J3zH-z2UWQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=tEahqDfMO5UhejX9fRV5-g&oh=00_AfTL_kGQTb_ffXktpLXcSksojuEbZtWJ7H59mn518FChFQ&oe=689B9222)
    

*   Add a new asset by clicking **Add New**, and select **3D Model** from the menu.
    
    ![The Import Models dialog box appears](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/469364005_604977652040190_8339871927361378787_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=ytA1HYpr0ygQ7kNvwG2oEqY&_nc_oc=Adl-VHWB9APSVfU3_C91nKzBeMrElmjnSZJdXMWag3aZHcyThHnpegSxT3ybIXNZnL4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=tEahqDfMO5UhejX9fRV5-g&oh=00_AfS3ZSSO34wq7GBGB8DiZL6vgs9JpDfgHyYLnCtFK93blQ&oe=689BA06A)
    

*   Select the asset files to import by clicking **\+ Choose files on your device** on the dialog window that appears.
    

*   In the file picker window, select the 3D model file and associated texture files; click **Open**.
    
    ![Select the five asset files](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464310803_573870025150953_4833471769077242766_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=AgIPcM1ohSkQ7kNvwFxq-3C&_nc_oc=AdlOlzLH3Jq1HIJK0i9Xzl2XXm7AbIWOQIsemuz4tBEu9vGAkdu4SYwaG5JTnbH4KKE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=tEahqDfMO5UhejX9fRV5-g&oh=00_AfSN6dpik7nNI6NO6siaQnAYvjmTYvqwN5SldMhf3ZXOkQ&oe=689B9E68)
    

*   In the dialog box, click **Import**. The following asset icon appears in your **My Assets** folder when the process is complete.
    
    ![This is what the rifle asset looks like after you import it](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464292127_573870045150951_3415127998518177098_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=-Z8Bb8UGUgUQ7kNvwEwTL8K&_nc_oc=Adll28D0FONaWkAuMS-TRhSWGwYRfHQIAKm0a5zFfshBqL9_0xRx6vxQpF7RmYiAU2g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=tEahqDfMO5UhejX9fRV5-g&oh=00_AfTplJxNCk8e-qCMPtWqZ1L6UgTI6kL--axNQbrYd2rBXg&oe=689BB7C3)
    

Spawn an instance of the asset by clicking on the icon for the asset, dragging it into the scene, and dropping it anywhere in the scene. A rifle object appears in the scene, and in the hierarchy.

![The rifle floats over the pedestal](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475232756_641654861705802_4132254507512158168_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=-_E2v3LSiTQQ7kNvwG6eR8r&_nc_oc=AdnvhjQhDGd2ttE_Du6mM4F3flIN7Rmce-pijIwyrbabWO8Z2CO4yeqEfmDprl_s4Is&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=tEahqDfMO5UhejX9fRV5-g&oh=00_AfQptzXWNQErHoMUC_wnLXGoiMJs3u-IgDquHOe5L30ZVQ&oe=689BA1D7)

## Custom model workflows

In this section, you’ll learn about three workflows associated with custom models.

### Creating, saving, and importing custom 3D models

There are several requirements for creating and importing (ingesting) custom 3D models. There are naming conventions for files, specific file types, and texture types. For more information, see [Creating a Custom Model](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model/) .

### Using static lighting to light a custom 3D model

Objects with built-in lighting can not be used in custom model worlds. This can be circumvented by setting up static lighting on a per-object basis using a static lighting gizmo. For more information, see [Static light gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/static-light-gizmo) .

### Add collision to a custom 3D model

Your world’s performance degrades if you build your world with very detailed, complex 3D models. To improve your performance, Meta recommends that you add a simple collider to your 3D model’s FBX file, which turns it into a collider asset. You can define custom collision shapes in the FBX file. When these colliders are imported into Meta Horizon Worlds, they become collider entities. Collider entities are a new type of entity that are used only for collision. You can use the following types of colliders: **Box**, 

**Sphere**, **Capsule**, and **Mesh**.

A bonus mesh collider is available in the desktop editor. Although it doesn’t perform as well as the other colliders, it is more flexible and can conform to more complex shapes.

For more information, see the [Collider Ingestion User Guide](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/collider-ingestion-user-guide/) .

## 3D modelling resources

To learn more about 3D modelling, follow these links:

*   [Glossary of 3D Terminology](https://www.inf.ed.ac.uk/teaching/courses/cg/Web/intro_graphics/glossary.html)
    

*   [3D Modeling Tool Resources](/horizon-worlds/learn/documentation/custom-model-import/3d-modeling-tool-resources)
    

*   [Custom Model Import Best Practices](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/best-practices/)
    

## Known issues

*   Custom model worlds don’t support spawning objects at runtime from assets that contain primitive shapes or static entities (entities with motion set to *NONE* ). If you attempt to use such objects in your custom model world, you’ll break lighting and visuals, and it will impact your world’s performance.
    

*   You cannot convert a primitive asset world into a custom model world.
    

*   The desktop editor does not support custom shaders.
    

*   When you publish your custom model world, it takes anywhere from one to two minutes for it to be cached. Caching ensures that subsequent visits to your world happen quicker. While your custom model world is being cached, you can still access it and load into your world, but you’ll notice that the load time is noticably longer.
    

*   If caching fails, you’ll receive an email to let you know that your custom model world load time will take longer than normal. To fix this, simply re-publish your custom model world.
    

To receive the notification email, you must enable [Meta Quest > Email Preferences > App emails > Meta Horizon Worlds > Redcommendations](https://secure.oculus.com/my/emails/) .

*   You can spawn objects from 3D custom models into a primitive asset world, but you won’t be able to publish it. A selection of primitive assets is available to use and publish in your custom model worlds.
    

*   You can add primitive shapes (by clicking **Build > Shapes** ) to your custom model world, but only for greyboxing. That is, you can’t use primitive shapes to build your entire world. You can always use custom 3D models to build your world after you’ve laid-out your design.
    

## What’s next?

To learn more about Meta Horizon Worlds, try the following:

*   [Create your first world](/horizon-worlds/learn/documentation/get-started/create-your-first-world/)
    
     using our step-by-step tutorial.

*   If you have issues when running the desktop editor, see [Desktop Editor Troubleshooting](/horizon-worlds/learn/documentation/desktop-editor/help-and-reference/troubleshooting/) *   Learn about the desktop editor with the [Introduction to the Desktop Editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor/) .

*   Learn about the other tools available by reading our [Tools Overview](/horizon-worlds/learn/documentation/get-started/tools-overview/) .

*   Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs/) to learn about our program benefits.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 