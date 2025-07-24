# Asset Templates

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/assets/asset-templates)

An asset template is an asset that has the type “Template”. You can create one from a complex object in your Hierarchy. Asset templates work just like legacy assets (like a 3D Model), except that they include powerful change propagation and versioning features.

Like legacy assets, asset templates can include:

*   Multiple objects in a hierarchy, with a root object and child objects.

*   Properties that define behaviors. For example, grabbables, and objects with physics.

*   An attached script component.

But in addition to these features, asset templates also support the following:

| Feature | Description |
| --- | --- |
| Change Propagation | When you need to update all of the entities spawned from an asset template, you don’t have to update each instance by hand. Instead, you can update the asset template itself, then publish your changes, and they’ll propagate to all of the instances.This synchronizes your changes across all of the worlds where you used that asset template. |
| Property Overrides | Allows you to customize asset template instances by overriding inherited property values.If you want to apply those changes to all of the other instances of the asset template, you can push them back to the asset template, and then republish. |
| Versioning | Each time you publish a change to an asset template, it creates a new version of that asset template. This version information is added to the version history of changes.Keeping track of the version history lets you revert to any previous version of the asset template. |

> **Note**
> 
> : Meta Horizon Worlds Asset Templates are similar to 
> 
> [Prefabs in Unity](https://docs.unity3d.com/Manual/Prefabs.html)
> 
> .

## When to use an asset template

Asset templates are useful when you want to reuse an asset multiple times in your worlds, and you want the ability to update all of the instances in one-fell-swoop.

You can create entities from your asset template, and when you make changes to the asset template, you publish them, and the instance entities are updated. This makes it easy for you to update all of the instances in all of your worlds, using just one operation.

## Example

Consider a scenario where you want to create a forest in your world, and you want to create it using many instances of the same tree.

Now imagine that you need to update all of the tree objects. If you’d created the trees from a legacy asset, then you’d have to manually replace every tree in your forest with an updated one. This could be a lot of work!

But if you created the trees from an asset template, then you could update all of them at the same time just by updating the asset template, and then publishing the changes. The changes are then pushed to all of the instances of the asset template in your world.

## Compatibility & Recommendations

*   Asset templates are compatible with anything that can be spawned into the world.

*   VR support for asset templates is limited. Overrides to instances of assets done in VR can only be applied to the definition via the Desktop Editor.

*   We recommend using only [File-Backed Scripts](/horizon-worlds/learn/documentation/typescript/filebacked-scripts/) (FBS) worlds for the best experience and full functionality. **Non-FBS scripts are not fully supported.** Without file-backed scripts:
    
    *   If you add non-FBS script to the template definition, when editing the template definition you can’t edit the script (it will not show in the script dropdown in properties).
    
    *   If you edit a non-FBS script and/or attach it to an instance of the asset template changes to the script on an instance will not appear as overrides and thus cannot be applied to the template definition and propagated across worlds.
    
    *   If you add a non-FBS to your definition it will duplicate anywhere it’s used in a world.

## Feature walkthrough

This section will go through the general workflow for templates once you are part of the GK. If you prefer this in video form, please see the tutorial video below.

## Creating a basic asset template

There are two ways to create a template:

*   By converting a legacy asset to an asset template. See [Asset Migration](/horizon-worlds/learn/documentation/desktop-editor/assets/asset-templates#asset-migration) section for more information. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452458941_512500697954553_8078786083910498359_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=og2CiJB7GngQ7kNvwElylre&_nc_oc=Adn4PWzgbaSgS2Etf3qZnsqosYINQaBBXEpn3judCxHvhv0gaqakSIAH1W6rVcdex84&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfQDqWnHUwDEOgW2XKTauh_GRLReQEeFrnlsKYpGUUQ6pw&oe=689BB28C) 

*   By selecting objects in the scene and creating a new asset template from them.
    

To begin, first create a basic asset template.

*   Add a basic cube to your scene. You can get it from the **Shapes** drop-down menu. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452893303_512500567954566_2630102149456461559_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=rVPu4m5l6dAQ7kNvwEKnscm&_nc_oc=AdmHrE91-wFRJjVr-nIJSLyUQAtiUN8ICoMyu4v1KxnFZMMSsSAuDnt1SgJl9xGrWcM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfR_H0UoOU0CMA-k6LYEuAvQU9mc2By6onUptNlI7ctU-Q&oe=689BA76D) 

*   Add a basic sphere to your scene. You can get it from the **Shapes** drop-down menu.
    

*   In the Hierarchy, create an asset out of the two shapes by selecting both of them, and then right clicking on them. In the menu that appears, click **Create Asset**, and then enter the asset details. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452863899_512500587954564_4581130950048103563_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=IbA8I-2S4w0Q7kNvwFcV9qR&_nc_oc=AdmvajLCUQqWnMR5NqhIrRVo1HbEW_vUbYVMq-ZkkSTjSPCDYFWnWCHd4YxPEUbKMdY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfQ1bLRdNAx8rT0lm8aiyAPbvwuRjqjKvCXB__X8cp7cmg&oe=689B930F)
    
    You can create the asset as a template or as a legacy asset by selecting the asset type. If you choose **Legacy Asset Group**, your asset will not have instancing, property overrides, or change propagation.
    
    [](/horizon-worlds/images/Asset_Templates_28605826407187_4.png)
    

You have now successfully created an asset template. The icon for the asset template changed in the Hierarchy. This is one way you can tell that an asset is a template asset.

## Editing Asset Definitions

Asset template definitions are edited in an isolated editing view, similar to how editing prefabs in Unity works. To enter asset definition editing mode, follow these steps:

*   Enter asset definition editing mode. Right-click on your newly created asset, and then select **Edit Template Definition**. You can do this from either the Hierarchy, or by right-clicking the asset card in the Asset Library.
    
    [](/horizon-worlds/images/Asset_Templates_28605826407187_5.png)
    

*   Change the color of the entity via the property panel, or add new entities to the objects, then save the asset definition. This saves a draft of the definition. The he change appear locally in your world. To update the definition, you must publish the draft. After publishing, your changes appear as available updates in other worlds. To propagate changes in these other worlds, open the world and accept these updates. You can see more details under **Drafts**.
    
    [](/horizon-worlds/images/Asset_Templates_28605826407187_6.png)
    

*   Next, you’ll be prompted with the option to publish your template. Choose to **Save & publish** later.
    
    [](/horizon-worlds/images/Asset_Templates_28605826407187_7.png)
    

> **Note**
> 
> : Ingested assets must be spawned into a world before their definition can be edited. This is because ingested assets are created external to Meta Horizon Worlds and asset properties are applied to spawned instances of assets in a world before being saved to its definition.

## Draft Assets

A draft asset is an asset that has been updated in the current world, but whose changes haven’t yet been published to a new canonical asset version that can be used in other worlds.

*   To view draft assets in the current world, click on the asset updates icon at the top left of the editor header.
    
    [](/horizon-worlds/images/Asset_Templates_28605826407187_8.png)
    

*   A modal will appear. Click on the **Unpublished changes** tab to see a list of all the draft assets in your world. **Note**: Anytime you edit an asset it’s stored as a draft.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/505490657_741347521736535_8523116864699304202_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=Wp80jN-4qsAQ7kNvwFTKm5E&_nc_oc=AdlsVQugO-OGSTdCSpqmWULvI5A4wrgqZ3wvKn_lVagZDzXMggBGihfvbxn7SQVd0i0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfQN3Rj1l2Yna5sC793T9qBXbUmQo6hLmN0BIWRrjWDe7Q&oe=689B9C85)
    

*   From here you can either discard or publish your draft asset.
    
    *   When you discard a draft of an asset, all asset instances in the current world will automatically switch to the latest major version, as dictated by the asset definition in the asset library.
    
    *   When you publish a draft asset, it will create a new major version of the asset in the asset library.

*   Click **Publish** publish the draft asset. You will be presented with a publish modal. You can optionally write a comment to be saved as version notes with the new version, and then when the publishing operation finishes, a new major version of the asset will be saved to asset definition in the asset library.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452576260_512500694621220_7586723531942177562_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=v1sCqnbwcZsQ7kNvwEP-Cy7&_nc_oc=Adl2AcbSrqiP8g-T6Sq5Dd8R1CQgMuIud_lqOcCJqDonmQBhzp7aWEt-d5hrEzWD63A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfRMviqECdS5FkByfzL4wgNNlU4pM5DBNKIQZB9_M3OrXg&oe=689BB21D)
    

*   Once the asset is published, click on the **Version History** button in the Asset Details panel to see its version history.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452935806_512500691287887_214574099878998720_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=fvn20KsPdTUQ7kNvwHwc3Rc&_nc_oc=AdmKx2Z4T21EL-E3TcM_Sa1gKt5zLjgr0gPqWTYjAeOs3ZkyNW9eg6XklAZVkQXiJpY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfSUYmSb9VBNSqDgh47hYa24_qPLdrtXj9MlbzoUfz-BIA&oe=689BB31E)
    

*   The version history modal will display all of the major versions of an asset. These are all of the asset versions that have been previously published. If you go into other worlds or share an asset with other users, these are the versions that will be stored on the root asset definition. The asset can be restored to any of these versions at any time.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452933022_512500687954554_6151449604564408312_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=6uvynDJ6tpQQ7kNvwEiMohU&_nc_oc=AdkzsRx6Ov-RaNI7nDE5FKmQdnzbEYDCg2g8lRnpd5pxHyRf7uZ2pMhYfTawZzG9J1I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTK4aGM615cQTKDPKV4pE9sKpWW31Y1f-aHALWyCiEUrA&oe=689BBAAD)
    

## Property Overrides

Property overrides enable you to override the property values on an instance of an asset template in a world. It effectively allows you to disconnect individual property values, while retaining a link to the root asset definition.

To override a property:

*   Click on the root level asset template in your world. Review the properties. There shouldn’t be any overrides. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452684749_512500684621221_5369449154585863544_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=Bqo1tVpK8hoQ7kNvwGT4g_e&_nc_oc=Adky7-c-tWjLN0wGCgwaAhMOfFttBe3CjvSUsi4TLJC_aEzQ0phluaO7wNpfkbYxXHs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfSKisWBXY5F0aHZzPc1Ep0uxb2yn1CC74rZcjMbEEkm6w&oe=689BB015) 

*   Now, create an overridden property value. Edit the object to change its color. You’ll notice that the color label has a bold treatment, as well as a blue dot next to it to indicate that the value has been overridden. In the overrides panel, you will see a property override on the object showing different values for the previous and current color. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452757156_512500681287888_1648985213895312295_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=i1rFM8wymlQQ7kNvwH4p63x&_nc_oc=AdkCA4Qy3rwO9yN-sk7CpypEz1uMmxUnHb9z3VJOAUvZPZT3h5L10ltjM0Q13oOlP8U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTLILi7A8v8vaVLH0X2XFVUXR3xirjyZu_L9YaGyHml9Q&oe=689B9CE1) 

*   From the property overrides panel, you can either select specific overrides to apply back to the definition, or apply all overrides. When you apply overrides back to the asset template definition, all instances whose matching properties haven’t been overridden will inherit the changes, and a new draft version of the asset will be created. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452591119_512500677954555_6513963071618982978_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=Wd6ef45CG1QQ7kNvwHpo6_c&_nc_oc=AdnxEHGwXqyADRVeyP5mQub5i2ODJUus8vng_kkFBBXmSNBevqyl92K4Lw8DWScPBB0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTyUlJo_v5eTGcY1f4MWbY7MWoMISUGdGPQAyPHbFQWqw&oe=689B84FE) 

*   It’s also possible to revert overrides. Reverting override values will revert the asset back to the same state as any draft version that exists, or in the absence of a draft version, the current major version of the asset. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652316_512500674621222_1012367075903542989_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=VmGqgDSkSvQQ7kNvwGZzHj1&_nc_oc=Adlem0fGoWQW2mCnPE1KJMpElEFbbH-x9dIUqBA06XBYR4K5c95j_ewTxZ8DP4LzmrU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfQff8kIVcIt8nRkxAyEfYpCJeZEVo8w1MLUagjpA3LCAA&oe=689B9EFB) **Note:** Property overrides persist even when you update the asset. To test this, you can edit the asset definition, add a new shape to it and then exit. You will see that the color of the sphere will remain even after the update!

## Asset Migration

Assets that were in your asset library before asset templates need to be migrated in order to work with the new template format. This is a very easy process, but may take some time for a larger amount of assets.

The following steps will walk through asset migration:

*   You will see a blue icon at the top right corner of an asset card if the asset needs to be migrated. Right click on the asset card, and select **Update Asset** from the menu that appears.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452665936_512500581287898_7545021707173957534_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=J9V1bIW8kH0Q7kNvwFCuRDH&_nc_oc=AdkGLwF6kw3ETP-KZ4PJ-1wz2LoA-rSf_gNRMjUdBkCJvKpgz_es3vCjJ-g4WtoYGsI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTap8jl_Q2raciHqmiBN7lFkdmjpmeVFa6gkrDp89uZpg&oe=689BA7A4)
    

*   Alternatively, you can also click on the folder and update all assets in a folder at once by clicking on the link at the bottom right of the asset browser. **Note**: Ingested asset types don’t have to be migrated, only assets created within Horizon.

## Ingested Asset Types

An important note: ingested (imported) asset types automatically inherit asset versioning. While ingested assets (custom mesh, audio, etc.) are linked, you won’t see the overrides since ingested asset types don’t allow you to apply overrides back to the definition. If you’d like to apply an override to an ingested asset, you can create nested asset templates. These are simply asset templates that are parented to the same root object.

## Unlinking assets from an asset template

Unlinking instances from an asset template removes the connection to the template. The means it prevents the unliked asset from receiving updates from the asset template definition. It also removes the ability to push instance overrides back to the asset template definition.

To unlink an instance from a template:

*   Select asset template instance in hierarchy.

*   If the template has nested templates:
    
    *   Choose **Unlink instance root** to only unlink the parent template.
    
    *   Choose **Unlink instance root and children** to unlike the parent template and any nested child templates.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452934219_512500594621230_5600854580075909703_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=_etX-5Mkhh4Q7kNvwEQmzKr&_nc_oc=AdlV2ZyKoxFPqpYB0-4dBTYBnPsqpPaGMeiAwJ8IZArl5igIOOhNXgAwFDqE8zYlEvQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTlj78wrQJP2XNZzpLdfALPs5AMZqq4xrRu-Ag5zKTsWw&oe=689B994E)

## Attaching scripts to asset templates and updating the definition

You can attach a script to the asset template by:

*   Selecting an asset instance and under properties attaching the script as a reference.

*   Or, right clicking on the asset to edit the definition and then going to the definition properties and adding the script as a reference.

### Attaching the script to the asset template instance

*   Edit a script in the world from the property panel.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452953164_512500601287896_1058603146175003068_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=B-Li8_ztzewQ7kNvwEjeb6C&_nc_oc=AdnjERDevH_EtdIJfOnF3yXHoQe9HpNBmr7TW_dgm6LANHcKg3J6EsiUpO4Wt0XvA_E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfRASm7lW5nnQYY1QDVBd5g4KDG3BYPTRg9QWlTsdPAHQg&oe=689B99CE)
    

*   When a script is attached to an asset template, you should see it appear as an override. You will see a blue dot next to **Attached Script** (above image) and two overrides applied: one for the script and one for motion (shown below).
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652931_512500564621233_8795829224957538121_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=tq7FfrIGRT4Q7kNvwFZLld8&_nc_oc=AdmlDLFgmpoxJzltVWWV2C5-Hj1vE0uixhz1UWVGefwJJRDW7liYpi3OWfmw-1du-sE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTyfCe3YIiAJKoQw0QfnFSVsxRJW9MLBKcBbwSSxWvciQ&oe=689BA2BA)
    

*   Edit the script’s source code by selecting **Open in external editor.** When the script’s source code is updated, this will also appear as an override.

*   Publish the script change through overrides. This will update the asset template definition with the script.

*   Publish the script change through the overrides panel. This will update the asset template definition with the script changes included in the latest version of the template definition. See the note at the end of this section for more information.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652238_512500577954565_6836600478890992788_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=ixwNB6RUQx8Q7kNvwFYubyE&_nc_oc=Adl6tr33thPOEUgIpng3zUW5JVpWROg8kM-JR-DyZv_bFg9gHVnXMICY-_T1L-kcdAQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfTE73vk-wVCfQ_EOUlaMcP1ZQJExZLrjCxvkkxggNiUxg&oe=689BB733)
    

### Attaching the script to the asset template definition

*   Right click on the asset instance (or asset in **Assets** ) to edit the definition.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452951204_512500597954563_4508069784119552394_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=ufL_0GMplnMQ7kNvwFDBRE0&_nc_oc=AdkBQMhx4gp6z5fUD2OEldNe5_8jyOPnGXDGOUc2gO2jQFS3oGEJ5iC37miucXHrcdo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfSgqZW8BbqRMZ1sC1yMETeGQskWHLclBGtLlzdgVtW9Wg&oe=689B85A7)
    

*   Edit a script in the world from the property panel.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452054064_512500541287902_5048148391692387350_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=1WfBU9_5jjoQ7kNvwFT1kc7&_nc_oc=AdleegTw2ODiJ4Q-8yvN__Ko1itNYojJQR6XFoSsOrXx1QlH6d4XqTIbGM5vY_V7EZo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfQ_M43dFxJE4NIg62ayfyk2pVT4EvRLON-rPwEFEaCyEQ&oe=689B8A3C)
    

*   Save and publish the template definition. This will create a new version of the asset that includes the script changes. See the note below for more information.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452757259_512500557954567_7387970478247480678_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=tll8hlB7UzsQ7kNvwGqJIxk&_nc_oc=AdlcTWvUmCNlYJyTn4oodN9rx27rD4spHCttYqhNStllafTJIoz3hzJ2TcOkfNvmRTo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=n6ehPCqYYJJiwUbqT_SfMQ&oh=00_AfSXiaakzHRKxAAVpJZsqYZicwj1jYlu2XOZMzuRrkELdQ&oe=689BA53F) **❗️Important**: When you open a new world that uses this asset template, the script change will be included in the asset templates update. If the script in your world is on a different version than what is in the template update, accepting the template update will also update the script to be on the same version.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 