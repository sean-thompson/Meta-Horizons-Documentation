# Meta Horizon CMI & TypeScript API 2.0: Import Images & Add Texture Animation

[source](https://developers.meta.com/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/meta-horizon-cmi--typescript-api-20-import-images--add-texture-animation)

## Introduction

#### Creator Skill Level

All levels

#### Recommended Prerequisite Background Knowledge

No prior skills are necessary, but knowing a little about Blender and TypeScript will be helpful.

#### Description

Learn how to bring your virtual worlds to life using custom animations and visual effects. You’ll discover how to create animated instruction boards, add custom VFX, and even make an animated fireplace! Your creativity is the only limit.

We will start with the basics, such as importing Custom Model Import (CMI) planes with image textures. Then, we will explore various texture options, including transparency methods and importing UIO textures for animation.

You’ll also learn how to use two prewritten scripts to add animation and interactivity, even if you have no prior experience with Typescript.

#### Learning Objectives

By reading and reviewing this written guide you will be able to:

*   [Import CMI](/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/meta-horizon-cmi--typescript-api-20-import-images--add-texture-animation#image-imports)
    
     images with or without transparency.

*   [Use and or write typescript code](/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/meta-horizon-cmi--typescript-api-20-import-images--add-texture-animation#step-5--create-scripts)
    
     to create animated textures.

*   [Billboard](/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/meta-horizon-cmi--typescript-api-20-import-images--add-texture-animation#step-7--billboarding)
    
     an animated texture to create a unique 3D-like effect.

## Image Imports

When bringing in materials you are unfamiliar with, the cheat sheet below is a quick way to look up the naming conventions used for importing the most common material types.

If you are new to Custom Model Imports (CMI), don’t worry, we cover how these work in the next couple of sections. The long and short of it is that in Blender, the material must have a name that parallels the name of the texture PNG you upload with. A simple example would be a mesh, with a material named “MyTexture” in Blender, and uploaded with a PNG named “MyTexture_BR.png”

### Image Importing Cheat Sheet

*   **Image.fbx**
    
     (Standard Image)
    
    *   Upload with file named “Image_BR.png”
    
    *   Named “Image” in Blender

*   **Image.fbx**
    
     (Metal Image)
    
    *   Upload with files named:
        
        *   “Image_BR.png”
        
        *   “Image_MEO.png”
    
    *   Named “Image” in Blender

*   **UnlitImage.fbx**
    
    *   Upload with file named “Image_B.png”
    
    *   Named “Image_Unlit” in Blender

*   **UnlitBlendImage.fbx**
    
    *   Upload with file named “Image_BA.png”
    
    *   Named “Image_Blend” in Blender

*   **TransparentImage.fbx**
    
    *   Upload with files named:
        
        *   “Image_BR.png”
        
        *   “Image_MESA.png”
    
    *   Named “Image_Transparent” in Blender

*   **MaskedImage.fbx**
    
    *   Upload with file named “Image_BA.png”
    
    *   Named “Image_Masked” in Blender

*   **UIOImage.fbx**
    
     (Animated Image)
    
    *   Upload with file named “Image_BA.png”
    
    *   Named “Image_UIO” in Blend

## Texture Swapping

If you are already familiar with CMI and Typescript, this brief summary shows you how to upload texture assets, which can be referenced from your Typescript “props” as PropTypes.Asset, and cast .as(TextureAsset).

Don’t worry if this is your first time, we will be diving deep into both of these topics throughout.

### How to Upload PNG Textures

At the time of writing (June 2024), uploading PNG textures can only be done through the Horizon Desktop Editor. The name of the image does not matter, but the image must be a PNG.

In the images below you can see screenshots of the Meta Horizon Worlds desktop editor. From the “Assets” tab you can click “Texture” and then in the right image, you can see that you are able to upload multiple PNG images. We recommend first creating a folder to upload and store these images, it is much harder to move them after they have been imported.

![22 Horizon - Select Folder Add New Texture.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452968581_512510194620270_3962294350470992074_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=q28Ma_M5pIAQ7kNvwEhZHmx&_nc_oc=AdkhcFXLzDdpYjpEdA-RugBSWgA6cd4sRsJi0lvuSsknLshz2VPftm81ZsxQhoPvgG0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRZk1S-70lx0I_7BwkzIznN_Vxm-nb-elyjSWeTl1KyDQ&oe=689B9C9C)

![24 Horizon - Import All PNGs.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653578_512510044620285_6379585956399160296_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=v3DylAVc6poQ7kNvwFju13J&_nc_oc=Adm-D0wFT7bG8dYIHtNnI7UYMuDjZGEUGz_7zvVckhZJTWCH2bYmNYMwesxzIkfKILA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSu4Hac3Wiw8BBpxpNZse0yK2GHhtbyLn17Eh-qAuzulg&oe=689BBC4F)

### How to Swap Textures

Here is a short example of how to swap textures, noting that this only works on CMI meshes uploaded with a UIO material/texture.

```
const texture = this.props.texture.as(TextureAsset);

if (texture) {
this.entity.as(MeshEntity)?.setTexture(texture);
```

## Step 1: Creating FBX Files

In the first step, we will show how to create FBX files for standard, \_Masked, and \_UIO material types. The process is similar for \_Unlit, \_Blend, and _Transparent.

Once you have opened Blender, select and delete all items.

![01 Blender - Delete Hierarchy.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452673104_512509954620294_1064153443481861995_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=gx5MyQ_BLtoQ7kNvwHALlmp&_nc_oc=AdluIHxKFbBJNH9n_MTwp48282Q_zEdtwksZNuOgZwZJY3oeB35eX4eTOUm107C_exk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfS9tBLZLc3TPk_Oc8bNiW6x2tGow75yy6pfFDsVmIjNPg&oe=689BC62E)

Then we’ll create a mesh plane via Add>Mesh>Plane.

![02 Blender - Add Mesh Plane.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452597170_512509924620297_9030051662676405660_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=7YWC774See0Q7kNvwEZoqpG&_nc_oc=AdkBFDEzrILjm49JeIZVeD7Sj-w9ly4IHjIy_cA5dm1OGYsPjxZnSj46EPseLCLxva0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTuVgsr5e4POTtssVuxg3ri8NqngRSj-uXUYeZ-vzyMww&oe=689BA565)

Next, with the plane selected, click the ‘red beach-ball-like’ material icon on the left. Then, click new.

After creating “Material.001,” we can rename it “Image.”

![03 Blender - Material New.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452814563_512509981286958_8049382712676840349_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=wrs9UoX2DGEQ7kNvwEw4OSe&_nc_oc=Adkp0jEj7BGPTFpH1fQmXxeHXVm6t2MHqpqF1VLpyslgYaTMohocfCK2ilaTV_2GcHc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfR4g4JcC4opU_Ju7-XxTjn7p68_0h9iELm-2-pSypjNMw&oe=689BB8EE)

![04 Blender - Rename Image.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452819243_512509901286966_2206396220220413926_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=ez548R4_BY8Q7kNvwEBYpL6&_nc_oc=AdmsqCpLH6_lZzrp8e5s9G_Q2bn6K2XvG3cICVSpxeUN9VDjoaLo3d4LGBNLPUzsYE4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSBPBf1YIivwXw8lElZQ5rkPHvnn78RoInU3pAWTAO7lQ&oe=689BAB62)

This is a simple name, with no “_” underscore, used for CMI FBX objects being imported into Horizon. Note that most any name can be used, but the PNG texture uploaded with the model must use that name plus “\_BR.” For instance, ours would be “Image\_BR.png.” If your name in Blender has underscores, everything after the first underscore will be ignored by Horizon unless the underscore corresponds to a specific material type, ie. _UIO, which we will see later in this step.

Next, we will export as FBX, via File>Export>FBX. Make sure to give it a good name, we will use “Image.fbx.”

![05 Blender - File Export FBX.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452916233_512509864620303_2779347807224869433_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=Fj2V7iKIVT4Q7kNvwGqYef0&_nc_oc=AdkdLeM7blD8gcOnjRRcQ6CCtMSsr_nZeH0_gu2F6SvE7NXaqraU21MlBcxVhuWBOU4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSwxc2oVEKhYrkRTEFWr4J_8NSryh_MNUpktvhclJ_Klg&oe=689BC390)

Now that we have created this simple plane, we can upload it as many times as we want to Horizon with individual PNG images named “Image_BR.” I recommend saving this in a folder to use whenever you want to import an image into Horizon. 

![06 Blender - Save And Name FBX.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652224_512509771286979_6031989145017839875_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=gitObrflqmMQ7kNvwEFWrn2&_nc_oc=AdnV1Ghj9KcaeNif93b1DiS2pWEgvhnCdGCMOhyARQXMG2zpz9FMyt-aOD2TcIMWBdQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTkH7SMRLWDGH-Cm7SJjK6HCZcV3nPRC9sg-Yr81FNfVw&oe=689BC22D)

Back on the properties panel of our Plane, we are going to rename and export it two more times, one named “Image\_Masked,” and another named “Image\_UIO.”

Masked is used for images with solid areas of transparency (e.g., logos, icons, etc). UIO also uses masking, but allows the mesh to have the texture swapped in Horizon.

![07 Blender - Name Masked.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452863715_512509734620316_4491289245265288581_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=gViQNxTMU8MQ7kNvwFpKyPG&_nc_oc=AdmA1mSQcw_DrRUA1gJedP5scEudS5GDokF60-oBmK12A3CZLc59egrm77pYT-kz6aU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTuYfDm41Z1LnQxX0IzxVeP5s_0PgAMmBlJCspPWnATxg&oe=689BAF78)

![09 Blender - Name UIO.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452683821_512510081286948_2595619572129583607_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=qX2ShYkiDp4Q7kNvwFqRKia&_nc_oc=AdmHPSZON9VAA-uOrHRsRKnu7P-p28G5C5ctEhUboQ4QjDam1SGAlGQjwXLmnBw4wjU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSpqbvkU_kVivTWfMmdHtCP2VkMEuWA9fg04wnXMLjnDw&oe=689BA525)

The exported names of these FBXs are not required to match, but I found that these names made a lot of sense for our use case. For _Masked, I named the file “MaskedImage.fbx,” and for the UIO image I used “UIOImage.fbx.”

![Screenshot 2024-04-19 at 11.11.10 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452898941_512510074620282_8089196613872825284_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=SsiuOS1eiOIQ7kNvwFXuYUc&_nc_oc=AdkPEpjLbX5OhehBADuWPEtSh9VccN4t7F6YNSfoa6uvLWrJHCf-ukzOIe5Lrro7QnI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRyJ9eSsjO7EIAfml8H-YzX0qwPsTK578EanK-i21Otlw&oe=689BA8D1)

![Screenshot 2024-04-19 at 11.11.21 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452554819_512510067953616_4081317241237303944_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=Cs39CZDTrYEQ7kNvwFRmyT3&_nc_oc=AdkHDCHGrh_BNK9gcQ24eCmZPCyz4P4FypwHn1I3xfqfeTlkg9Qe6NGERhN7dW_HNq0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfT_OZmEQN8Xk1jQbw6R6WiU3Wx1guePIgw4SHBESubWzA&oe=689BA613)

Similar to “Image.fbx” and its corresponding “Image_BR.png,” these can be used for any 2D image. If the image is not perfectly square, you will need to adjust by scaling the plane in Horizon.

Repeat this process for \_Unlit, \_Blend, and _Transparent. I named my files “UnlitImage.fbx,” “UnlitBlendImage.fbx,” and “TransparentImage.fbx.”

### Various Material Types

In the image below you can see the various material types being applied to the same PNG fire image. For MEO and Transparent they need to be uploaded with a secondary file which will be seen and discussed in depth in Step 2.

What we can see from these images is that four material types support transparency and three do not.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653333_512510071286949_6198600653867134572_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=aRFlfnnluJMQ7kNvwEBwWJ1&_nc_oc=Adl6eYTmer-2XWsdVcwYlTaB3Ye7R8eFQwm3KFYIQYXRUWBGZ3ZBNgjAdaosHh6VR3E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSreGZ6pSq5xkmNTYpVviQrqpOhFYV7v_hh-PaV_AsIJQ&oe=689B985D)

Here is a brief description of each material type:

#### Standard Image

*   Basic texture, nothing special, and is easy to use.

#### MEO Image

*   Using a secondary PNG, the RGB channels correspond to Metal, Emission, and Occlusion (MEO). Notice that if E & O are set to 0 the texture is not visible. Try playing with these values to get the exact look you are going for.

#### Unlit Image

*   Light and shadows are not applied.

#### Unlit Blend Image

*   Unlit, but supports transparency using the alpha channel of the PNG.

#### Transparent Image

*   Using a secondary PNG the RGBA channels correspond to Metal, Emission, Specular, Alpha (MESA). This means you can get a metallic that is also partially transparent! It also means that you have to make sure the alpha channel correctly masks out your texture, in this case, it does not, hence the partially transparent square.

#### Masked Image

*   Uses the alpha channel of the PNG to mask out the image. Note that this is masking, not transparency, partially transparent pixels will be dithered, meaning every other pixel will be opaque or clear. For real transparency use Unlit Blend or Transparent material types.

This is an example of dithering.

![pasted-image.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452704315_512510077953615_83611763970977192_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=5ooeeJg4J-gQ7kNvwFHcVBA&_nc_oc=Adm5KWA9YRJlTP7SQiMH-KeJytkHwgQ5OPCqMbds0GVn3FZrvx82mSiTmTb_MdnG4f0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQVnY7Ix4dAyvGMgRr9y3iZ51NKFL52Kr35aFxGbw0ZJw&oe=689BB99E)

#### UIO Image:

*   User Interface Optimized (UIO) images can be animated, meaning to have their textures swapped out. They are also rendered in more detail than the other texture types to perform better as user interfaces, ie. for use in high touch point areas.

#### Creating Secondary PNGs

Transparent and MEO images will need to be uploaded with a secondary PNG, named Image\_MESA.png, or Image\_MEO.png respectively. You can use a variety of tools to make these PNGs, we won’t be going deep on that subject in this Written Guide, but we will look at a simple example using Blender.

Start by opening the “Texture Paint” workspace:

![Screenshot 2024-04-19 at 8.53.37 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452907674_512510061286950_115269541411199578_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=1kIuRIXQg-AQ7kNvwEc-DB0&_nc_oc=AdlBP9QiEs2K8oaYnWtj9uOAqShy8g0bdX3V2qdEGrRxX36EfMZmhk11iJLb0qMKbGM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRn3sX5D3F0RwHw3z12-8fa4yc5yKdQNGBXm2aUcmxMqA&oe=689BA32E)

Then click “New” to create a new image, and from there select the Color property.

![Screenshot 2024-04-19 at 8.56.04 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452577881_512510057953617_5245386781112144432_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=Dg_p2mka424Q7kNvwHOdk1f&_nc_oc=AdlBHp1Rc61wHlqIIukAKUgI7BRRtBCmd24r5LaLpiVR7BPxf6rsNRIAU57z6dq7VzE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfR2wyvOih-z1uI4OKVr5FuLjwacm2LTawSV2O3BNzls3A&oe=689BB028)

![Screenshot 2024-04-19 at 8.56.47 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652809_512510064620283_8540244349186137340_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=OGx4dlMZn8sQ7kNvwGipzRU&_nc_oc=Adkps2u2xQbRGUMT4S77ym22z4jvTOhIUj5xamUEPG_jS4mEN880sDt6vWbsVtB9dIk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSpCodwhsziHrRiaDcHw0mm7j_6R3neXv1zP6j6ncp7kA&oe=689BA7DC)

Then select RGB at the bottom, you can then type in the exact values you want for the MEO or MESA channels. In this case, I have set all channels to 50%.

![Screenshot 2024-04-19 at 8.57.03 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452916207_512510054620284_1744802443120394456_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=ILmB7oxoMvAQ7kNvwEDNV9l&_nc_oc=AdllwupNcx0Zxc3cH7u4XZA6Xizx5AQh9pAVAA4yPxEI14iYsiwhRGmPfijIQhA04mM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRVKIuwjaGLOVvWMmEazuOd4nr1P7IJF_qheGp1wqVP8g&oe=689BBED9)

![Screenshot 2024-04-19 at 8.58.00 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652384_512510051286951_6288220246956715927_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=0tLhqmGu0dAQ7kNvwG_K0e1&_nc_oc=AdmxOgZc7j5lHRw6Uy1eohzUQ_4dHlet74ar6klXngGPX9HbNFHw9Yw-HXx1QiPxXR0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRDxe-q3B7RpGXQfakViDQxNTkFkn4RZvwhXYGo86xz-g&oe=689BB486)

Remember that RGB correlates to MEO. For example, red is how metallic, green is emission, and blue is occlusion, and the same is true for MESA.

| RGBA | MEO | MESA |
| --- | --- | --- |
| Red | Metal | Metal |
| Green | Emission | Emission |
| Blue | Occlusion | Specular |
| Alpha |  | Alpha |

Next, to finish creating the image, we can click “OK” (in some versions of Blender the OK button has a different name). Then click Image>Save As> and save the image as either Image\_MEO.png or Image\_MESA.png depending on your intended use case. For practice, consider trying both.

![Screenshot 2024-04-19 at 8.58.28 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452413439_512510047953618_4137326271119080615_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=0j-4zjVGQ3sQ7kNvwHFtPuN&_nc_oc=AdkhPBbrt79IjKBeB8LvRD73TDmam3aI0lHNli4N-ZRXFGDdMa2Zvbi5O5Qr5oMv1wE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfR9hutQ2e49FnECBKATeFVzjbHQhDDjmcgKOU1yXpUL5A&oe=689BA8AC)

![Screenshot 2024-04-19 at 8.58.42 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452929981_512510041286952_8941302965582273418_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=5HPquMG9d88Q7kNvwHGEIX6&_nc_oc=AdnXklYvxbpIY38Xf36_q-PKS7Nn9hcOVwj51M9daEnVvPiTHQ_u_gKk8VWwVsAC4c0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQ3i48NOoMWLB3Coy6AcrwQFSn54yW2zSWH3EGtij6inA&oe=689B9613)

![Screenshot 2024-04-19 at 8.59.39 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452691797_512510037953619_5827144605064287682_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=XNunk3C6dsQQ7kNvwGXN2ew&_nc_oc=Adka0PslxlKaIh2leMgAYp2gBRYksRoiHwN3pxCSTVgWcLlUC7ft9CRj-cJYRpHlLcg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQIS28bPRB2gFCwBJhZMovRBCn5ZODVaRDnRodLBSR3XA&oe=689BB41A)

You have now created a secondary PNG, great work!

Sometimes when creating transparent images you don’t want them to be evenly transparent across the entire texture. In that case, you will want to consider using the “Erase Alpha” or “Add Alpha” brush tools.

You can adjust the radius and strength to determine how wide and how much of the alpha you want to erase. I erased three lines in the secondary image, using 100%, 50%, and 25% strength from left to right. Because the image was already half transparent, 100% and 50% had the same effect.

![Screenshot 2024-04-19 at 9.17.39 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452885117_512510034620286_9198152519515217659_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=WefWL2MdImQQ7kNvwGazUj9&_nc_oc=AdkcWf14fXZC6Wnm2hel_G8Ue2e8KKK3-IgeWkdr3QaHe0RuAT-Cq0Ty3GWDnWkHerA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQkC7RbhGB8A9ejSM5umbyZ715kpL4QjIItYOdCtjZmww&oe=689BC263)

![Screenshot 2024-04-19 at 9.20.46 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653014_512510031286953_1113735815860416145_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=DNiOH7ytkMMQ7kNvwGvyeOH&_nc_oc=AdnlJe52wGg1uFhJRABGH0wLbsd_Thw67RelU1Ko6pav2EaDZGGyhcu3ZEB8UpGYlSk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQ2H-ARGAwMmoSNkU9R2O3C2f6-kFedDprPZw7lJpLTsg&oe=689BA078)

#### Mentor’s Note:

There are a large number of software options to choose from, but if you want to use Blender, consider opening the texture, painting over it, and then saving it as a new PNG. Here’s a brief example of one way you might do this while preserving transparency.

Start by opening the texture, then select the saturation brush effect tool. Then paint over your texture to make it all the same color without affecting the alpha channel.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452578204_512510027953620_7672824023604347554_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=-kCULDRZHdEQ7kNvwHf5_Pr&_nc_oc=AdkDJzONoUPul4xHo7TLEf40NI-kSoBPDN3utVZOCAz4dMusKQ067zb8jJyIfdZVBsI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfT7v6x5_Y8rQkk5nnyTni4wM2PvhhIVxnJanZdlUwbkJg&oe=689BCA78)

![Screenshot 2024-04-19 at 9.26.48 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653578_512509964620293_5448085797043372349_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=pEaEveDUCwcQ7kNvwEMS2lY&_nc_oc=Adln3OEjmmWtpYVbEHqUs0jqAuM4onEiTvZPYGuD2Dr29_oKunPJxtux5zul4YC6xOU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQBTLHCFjrcytWZegKABHg0OExdNu7oD1zcmXzqTb_hTg&oe=689BC37A)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452518323_512509967953626_7006945869471042038_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=Sw2fBhFnNPMQ7kNvwFeCALP&_nc_oc=AdlbXXmzZD5QHZu3ao_WqhHWtnWEpWaW8tLr5GDquk4layWN48efAdYOsrIK2pa3YxQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQMdP86ORaDZ5D3qxTXwUu6Eyx0nz7MxhNdXFZS5tESIA&oe=689BC53F)

You can then select the dump bucket tool, and adjust the color RGB values to the MEO or MESA values you want to use. And change the color, and thus the MEO/MESA properties of the image. Then just save the image as before, ie. “Image\_MEO.png” or “Image\_MESA.png”

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452933713_512509961286960_6507830893434825526_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=i8vjT_rK6qcQ7kNvwH6GnUW&_nc_oc=Admz1Ed1K4NAjEfTAMQ9jrz5yNInrhVWHmjpfZLylBPuDPysNe5e9oY7ZWPFpelRBlw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRLuJ_iIkKqdzTOh7N8g6e8Nb8H94Y-vFz-peIc_WEsMg&oe=689B9740)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652035_512509957953627_1509299483219844935_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=STr1tHLxJccQ7kNvwE0D_wi&_nc_oc=Adlu2kuelTc8IVj8qjHZoiDAMlT622k9wswHEFnZmwLyAjh7Q51JrcezOeUtA65jhao&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQzS8OzxdF5GvKE8oiAbEs_6l1ZLf7g3tx3H59K5L8NkQ&oe=689BBA3F)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452934280_512509947953628_7533721349325358428_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=j5xDBSAkv_cQ7kNvwHlyV7l&_nc_oc=AdlrVCpKK0tx_t2nI-nYnfWxoL-CNyVHNZ9UW3u8lsNw6kyHkWDaaxiz32h-i-eCWhU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRyrj_lPapZHufKOueJNO_gJFs0tc-i2vXkdVoTxE_3Uw&oe=689BA7A7)

## Step 2: Prepare PNGs

In this Written Guide, we only need the \_UIO FBX, which we exported as UIOImage.fbx. UIO textures need to be uploaded with a \_BA PNG, which we will need to name “Image_BA.png.”

![Screenshot 2024-04-19 at 11.06.55 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452520063_512509951286961_8039903915903876142_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=gxTBL-HTRKUQ7kNvwGItYSV&_nc_oc=AdkoM5JLFGwX8sKSCOmGnCHNJ3UEP-kbWx8Fw4IWsyIVDY2RHiCRiS7BzKVf4wcFlpM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSf0dEhk-O0JaSilFPE7g7UIjSWez2NODo-RXW9_Ovp7A&oe=689BBFCA)

For other texture types, refer to the “Image Imports” section. Try uploading one of each of these to your asset library to familiarize yourself with the process and various texture types.

Then upload the UIOImage.fbx & Image_BA.png files together using either the Horizon desktop editor or from the web portal. From the web portal, press import, and then select the two files.

![Screenshot 2024-04-19 at 11.02.04 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452932907_512509914620298_8416274368174123809_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yy-3qnBObpsQ7kNvwH33RYd&_nc_oc=AdlzO0G06W351GRnY3z3Q-QBHPE1xw1IXxD0ME0WcCNPRxDVEBvKmX7Sdwj9vJjLPrY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQLkMOMXRq3t_krpKV6UqRFp6ImOtYSBN_LyS6vvEhGMA&oe=689BC58E)

![Screenshot 2024-04-19 at 11.01.05 AM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452716174_512509917953631_1260850758204712021_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=U9xP67L1PXMQ7kNvwFCHy9E&_nc_oc=AdncvGJ0Txqb_YLq8AfxALrI2__fzddHMWaGtWXBh5z7Vzg5h11p84hebsLjqSTyH8M&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTQB3xcQZQPg6WXZz6DQ2yfuuZ_4UKSBHUx49ggTHZKXQ&oe=689BA551)

You will also want to have a series of PNGs to animate. We will upload them in Step 3 using the Desktop Editor. Please note that at the time of writing (June 2024) PNG texture assets can only be uploaded using the Desktop Editor.

![23 Horizon - Add All PNGs.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452830425_512509941286962_2286961765036510195_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=StdIFarR1pQQ7kNvwFID_oi&_nc_oc=AdkTdvl74ldCq3dQWQpTMbGwvzZJ6x3X6CU-1ec7HYECqOhenbCWXgiBd0IHr9H03iE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTMP_XxaAW5Y3laTDoW8fgaEF5tN6O4llftA8gRANn-7Q&oe=689B9CFF)

### Desktop Editor Setup

For the best experience, we recommend creating a new world in the Desktop Editor as you follow along with this tutorial. Select “Custom Model Import,” and then click “Create.”

![13 Horizon - Create New World.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452514554_512509937953629_3385446684682933545_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=jZWsnYQABhQQ7kNvwGwD71A&_nc_oc=AdmAzTF1ayOAiyEqVPKlyFqQQrsgifD05_ij4L88CjAX3HlixeCYHkRwitbDsXcUh7Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfR8hV-z-adFZCaUThx4SEUN24GyOEEJ_F53FNviCbSYMg&oe=689BC336)

Once you have loaded in, at the bottom, select the “Assets” tab. Then click Add New>3D Model>. You can then select the two files, presuming you didn’t already use the web portal to import.

![14 Horizon - Assets Add New 3D Model.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452698500_512509944620295_8761892053068618025_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=vSjG2kqZ1xoQ7kNvwE8HJkf&_nc_oc=AdmzQYmrhyVrKCuoWSGpfjLvdJqnJvKKpvcRo-GT5nfOhXOVN9iJjgQMeFJ6nrvSXaM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRLOZZ8ThkrGg8Ob3w7YK5BlGZys_g0HgMH9Ftqh5G96w&oe=689BAFA0) **Pro Tip:** Create a folder first so that you can organize these files.

![21 Horizon - Create Folder.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452969006_512510024620287_7145889613842616136_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=_swybpzzpw0Q7kNvwHgKrW0&_nc_oc=AdkewAWrqkhIsAU48qcqECZS2Mo2Xq6n3P3at2MkfVv1ZKTZk6rNe4U0HT7YsjBd-tg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQcHyj1eb-Zl4Jk63pKI0VU5RlxsPyc2NMX84ATXf7ozw&oe=689BC437)

## Step 3: Review Assets

Bring out all uploaded assets into your world to review that they look correct. Make sure to set the UIO Image in a notable spot as we will be using it for animation.

![Model Examples.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452520302_512509931286963_1392348710732713706_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=8yzLmfcTK2EQ7kNvwEdf1Ss&_nc_oc=Adl_X4gn5vKNy8fHIVCPe3Z1RksRRMlejQtTr_KrQXL9UxuSJB-eYxThTEEb8UWxsKs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRX_9U_DfIqOyo167rbmpSPQOIssoqZ2VgSrjYjuiBMQw&oe=689B9B5D) **Note:** You don’t need to do all of them, just the UIO is required, but you might find it helpful to test the other texture options.

From left to right in the image below: \_BR, \_Masked, _UIO.

![16 Horizon - Drag Images Into World.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452698500_512509927953630_2391688165484220586_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=SraNsK6RveAQ7kNvwH0cRQ-&_nc_oc=Adlki4wt2rTpMUxXUHQKvjNJ9QUiyqJnE_3gQPhDvuKdrg_k38drSTr63su2eJOUykE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRwu5ONbghGQPUQyW9nTDh-g0WpBKFgVxM35XwfhF_idg&oe=689BBC62)

## Step 4: Animation PNGs

Similar to how we uploaded assets via the desktop editor on the previous page, we can also upload PNG texture assets.

Select “Texture” from the “Add New” drop-down, then select all of the PNG animation frames you wish to upload.

![22 Horizon - Select Folder Add New Texture.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452942546_512509921286964_7427347511941929464_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=TLg9u-FJ83UQ7kNvwFmupcY&_nc_oc=AdnbZdoUvAJFPRsHV55uTp0ujSIHMXYVIdmR9gOwLThGWXeBJ2-WQ1syjab98o5Dvp8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTMl__XyzJY3s3D2ezZVsHk5MAry7tA0DiNDHjJokJ03Q&oe=689BBC5C)

![23 Horizon - Add All PNGs.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452886177_512510021286954_7252073352601237353_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=a08T-FonGpwQ7kNvwGfU7k3&_nc_oc=AdmX4g__7rwbM7GDFuVxUeXxU8OH2hGGaWYU8UmIDymB2azlzIw2aMqGPZTtAq1uS2E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfST0ljKh1pxyBW1funSnvEL6teiWK5habup_GMyPyEmzg&oe=689BADC8) **Note:** The names of these images are not required, but it is recommended to name them in a way that makes it easy for you to identify the order in Horizon later.

Next, click Import. This will upload them into your selected folder. Unfortunately, they are not ordered when you upload in bulk like this, which is why naming is so important.

![24 Horizon - Import All PNGs.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452578170_512509934620296_9067343352172927240_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=97-5YeaIP3wQ7kNvwG8RYUU&_nc_oc=AdmxjHEif302ZxDgoB2ZQR6a7GdKkhEWwQyFUJPpppdOcAHH9s-HoBTY4eNmZ0Cyiko&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRAtpuu_caIO_6mSWSXmdbfXiD3Tfr0zZe2Ff8PqdkeoQ&oe=689BC79C)

![25 Horizon - Select UIO Object Attach AnimatedGIF Script.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452813675_512510017953621_1399693691768195627_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=K5IETKvLxFwQ7kNvwEiMh8n&_nc_oc=AdlUYwfYmowtc04awyV7HKIwceI7_TwWpGbpaZn9M8ouXSxl9Qn2MWxcfUmPTtJDIx8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfS3nAJtS164Zpw3Bljz7oHlDL_Ab2aIbbjdMdWZKBJlng&oe=689BAE4C)

### Typescript 2.0 Script Setup

We are using the Horizon Typescript 2.0 API, at the time of writing (June 2024), this is the default.

If your world is currently set to 1.0, or another version, you can change this from the script tab by clicking the gear icon and then Script Settings. There you will see the API Version drop-down and can select 2.0.0, then click Apply.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452968830_512510014620288_2686261352574634183_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=4WG3wHYna9wQ7kNvwF51Vq1&_nc_oc=AdmVU8JVucTyh2LdlDA80IZ1g1HtE1TAXTH7G5xiRgn-fT8R6438Ucy3FTV3En7b7PA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSDaBAZkcOnQLwTev2LBPvoJkonqzOr4iC_7U3zB3Koww&oe=689BB98A)

### AnimatedGIF.ts

You can copy and paste this code into a new script, or download the code as a file by clicking [here](https://drive.google.com/file/d/1L2RWLL8h75ezou6xoWUApNjr-aaH-2_Z/view?usp=sharing) . Then drag the Typescript file into the scripts folder (Scripts > Three Dot Icon > Open Scripts Folder).

```
import { Asset, Component, MeshEntity, PropTypes, TextureAsset } from "horizon/core";

class AnimatedGIF extends Component<typeof AnimatedGIF> {

  static propsDefinition = {
    //Adjust the speedSeconds default here, or for each animation individually from the properties panel
    speedSeconds: { type: PropTypes.Number, default: 1 },
    texture0: { type: PropTypes.Asset },
    texture1: { type: PropTypes.Asset },
    texture2: { type: PropTypes.Asset },
    texture3: { type: PropTypes.Asset },
    texture4: { type: PropTypes.Asset },
    texture5: { type: PropTypes.Asset },
    texture6: { type: PropTypes.Asset },
    texture7: { type: PropTypes.Asset },
    texture8: { type: PropTypes.Asset },
    texture9: { type: PropTypes.Asset },
    texture10: { type: PropTypes.Asset },
    texture11: { type: PropTypes.Asset },
    texture12: { type: PropTypes.Asset },
    texture13: { type: PropTypes.Asset },
    texture14: { type: PropTypes.Asset },
    texture15: { type: PropTypes.Asset },
  };

  //create texture array, starting index of 0
  textures: TextureAsset[] = [];
  index = 0;

  //This value is set in start using this.props.speedSeconds
  delaySpeedMs = 0;

  start() {
    //Add Textures To Array In Correct Order (Skips Unassigned Values)
    this.addTextureToArray(this.props.texture0);
    this.addTextureToArray(this.props.texture1);
    this.addTextureToArray(this.props.texture2);
    this.addTextureToArray(this.props.texture3);
    this.addTextureToArray(this.props.texture4);
    this.addTextureToArray(this.props.texture5);
    this.addTextureToArray(this.props.texture6);
    this.addTextureToArray(this.props.texture7);
    this.addTextureToArray(this.props.texture8);
    this.addTextureToArray(this.props.texture9);
    this.addTextureToArray(this.props.texture10);
    this.addTextureToArray(this.props.texture11);
    this.addTextureToArray(this.props.texture12);
    this.addTextureToArray(this.props.texture13);
    this.addTextureToArray(this.props.texture14);
    this.addTextureToArray(this.props.texture15);

    //Value can be changed from the properties panel, maximum speed of 100x per second
    this.delaySpeedMs = Math.max(Math.floor(this.props.speedSeconds * 1000), 10);

    //Create meshEntity variable to make sure the script is attached to a MeshEntity
    const meshEntity = this.entity.as(MeshEntity);
if (meshEntity) {
      //Create looping event with setInterval
      this.async.setInterval(() => { this.loop(meshEntity); }, this.delaySpeedMs);
    }

    else {
      console.log('AnimatedGIF: meshEntity returned undefined (is the script attached to a UIO CMI MeshEntity?)');
    }
  }


  loop(meshEntity: MeshEntity) {
    meshEntity.setTexture(this.textures[this.index]);

    //update the index and loop back to 0 when reaching the length of the array
    this.index = (this.index + 1) % this.textures.length;

  }

  addTextureToArray(prop: Asset \| undefined) {
    if (prop) {
      this.textures.push(prop.as(TextureAsset));
    }
  }
}

Component.register(AnimatedGIF);
```

### TextureSwappingTrigger.ts

You can copy and paste this code into a new script, or download the code as a file by clicking [here](https://drive.google.com/file/d/1ZCo3ZCAAEOzGzJRaCRmtJ4lxLyoxSk8y/view?usp=sharing) . Then drag the Typescript file into the scripts folder (Scripts > Three Dot Icon > Open Scripts Folder).

```
import { Asset, CodeBlockEvents, Component, MeshEntity, Player, PropTypes, TextureAsset } from "horizon/core";

//This script is attached to a trigger gizmo
class TextureSwappingTrigger extends Component<typeof TextureSwappingTrigger> {

  static propsDefinition = {
    //Make sure to reference the UIO MeshEntity on the trigger's property panel
    uioEntity: { type: PropTypes.Entity },
    startingIndex: { type: PropTypes.Number, default: 0 },
    texture0: { type: PropTypes.Asset },
    texture1: { type: PropTypes.Asset },
    texture2: { type: PropTypes.Asset },
    texture3: { type: PropTypes.Asset },
    texture4: { type: PropTypes.Asset },
    texture5: { type: PropTypes.Asset },
    texture6: { type: PropTypes.Asset },
    texture7: { type: PropTypes.Asset },
    texture8: { type: PropTypes.Asset },
    texture9: { type: PropTypes.Asset },
    texture10: { type: PropTypes.Asset },
    texture11: { type: PropTypes.Asset },
    texture12: { type: PropTypes.Asset },
    texture13: { type: PropTypes.Asset },
    texture14: { type: PropTypes.Asset },
    texture15: { type: PropTypes.Asset },
  };

  //create texture array, starting index of 0 is assigned using this.props.startingIndex (adjust from props or on trigger property panel)
  textures: TextureAsset[] = [];
  index = 0;

  preStart() {
    this.connectCodeBlockEvent(this.entity, CodeBlockEvents.OnPlayerEnterTrigger, this.triggerEnter.bind(this));
  }

  start() {
    //Add Textures To Array In Correct Order (Skips Unassigned Values)
    this.addTextureToArray(this.props.texture0);
    this.addTextureToArray(this.props.texture1);
    this.addTextureToArray(this.props.texture2);
    this.addTextureToArray(this.props.texture3);
    this.addTextureToArray(this.props.texture4);
    this.addTextureToArray(this.props.texture5);
    this.addTextureToArray(this.props.texture6);
    this.addTextureToArray(this.props.texture7);
    this.addTextureToArray(this.props.texture8);
    this.addTextureToArray(this.props.texture9);
    this.addTextureToArray(this.props.texture10);
    this.addTextureToArray(this.props.texture11);
    this.addTextureToArray(this.props.texture12);
    this.addTextureToArray(this.props.texture13);
    this.addTextureToArray(this.props.texture14);
    this.addTextureToArray(this.props.texture15);

    //Update to default texture on world start (checks for out of index starting value, adjusting if necessary)
    this.index = this.props.startingIndex % this.textures.length;
    this.updateTexture();
  }

  triggerEnter(player: Player) {
    this.updateTexture();
  }

  updateTexture() {
    //Create meshEntity variable to make sure the script is referencing a MeshEntity
    const meshEntity = this.props.uioEntity?.as(MeshEntity);

    if (meshEntity) {
      meshEntity.setTexture(this.textures[this.index]);
    }
    else {
      console.log('TextureSwappingTrigger: meshEntity returned undefined (is the script referencing a UIO CMI MeshEntity?)');
    }

    //update the index and loop back to 0 when reaching the length of the array
    this.index = (this.index + 1) % this.textures.length;
  }

  addTextureToArray(prop: Asset \| undefined) {
    if (prop) {
      this.textures.push(prop.as(TextureAsset));
    }
  }
}

Component.register(TextureSwappingTrigger);
```

## Step 5: Create Scripts

If you have downloaded the files, you can open the scripts folder by clicking the three-dot icon next to the gear icon, and selecting “Open Scripts Folder.” You can then drag the download files into that folder. Alternatively, if you’d like to write the code, you can create two new scripts, one named “AnimatedGIF” and the other “TextureSwappingTrigger.”

You’ll then hover over the newly created script and on the right side click the three-dot icon to see the drop-down, allowing you to select “Open in External Editor.”

![18 Horizon - Create AnimatedGIF Script.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452908886_512510011286955_6071772640735723234_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=AB_qp3CAF6wQ7kNvwGWCMEk&_nc_oc=Adn_eGwqbc0lL3Fd4GOsn7XbEoIJm9yZmCj6SgGWxt63NdwvrNexE4VEWuwNUeyl3Nc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfT-Fn1iL5IXLJyLXrjMLMMOx3fgFcykrrOkYwGrqD0MLg&oe=689BBEDF)

![19 Horizon - Open In External Editor.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452934389_512509997953623_1096257128825943521_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=-jWutCO2RPcQ7kNvwEf-tyU&_nc_oc=Adln0fG1LL10sFb7prMn8x1vvrmKa57M0vIT2BtuUh-SaQlAhMz3m17kvvcDSt2e-h8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRQagwpr_P-JN0R6gVeEErW4rI1671XsUVaaSxE1QNuCQ&oe=689B9BCB)

From the external editor, you’ll be able to paste the scripts seen on the previous pages or write it out by hand for practice writing Typescript code. You will want to make sure to click “Ctrl + S” to save, then the files will compile. Please note that this tutorial doesn’t cover writing Typescript, so if this is your first time, we recommend copying and pasting, or using the downloaded files.

![20 VS Code - Delete Default Paste AnimatedGIF Script.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452952740_512509994620290_6613449436146433136_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=sO8pvP4F13wQ7kNvwFHHMnr&_nc_oc=AdlbANT5EnvegPZ7iciYUTvgXEEf_8OEonCU-s7o7bhYZSANY6PKtbOjFGkvpPyQ_ys&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTMrGWmRgwmZal4crXdjEMA1FHW3OFTzOHaXzy6Evk1qA&oe=689BC4F4)

![38 Horizon - Create TextureSwappingTriggerScript.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452683821_512510004620289_3602977530773515663_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=F4Ps6qmLwqcQ7kNvwEkAZwd&_nc_oc=AdmoclfkezBaSXKNjb1ZfvbiIdm4hz_iPWakkmzWEutm8Fv4Qot_ZRRowhUM7U8FGGo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfROa1diiZd7g5B7K58vWQcJpCoFoUy0vLQ6Xrli-wzdYQ&oe=689BA474)

## Step 6: Animated GIF

Before we get started, make sure to click the square stop world icon, this is a good practice when working on scripted objects as it reduces the chances of bugs and errors.

![27 Horizon - Stop The World.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452615549_512509971286959_3679470934818076750_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=IIGo69Jc77EQ7kNvwH7TpjI&_nc_oc=Adm8d7Um2uvXZ1hcYlXaPlGkWu3Fiz58r-0zKTIU1tI0UTac0DdWTFoi6io7PLCC_Ec&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTp7kodCCm3tniW-lg9DXbLS2GIxNVVgowZbFrW3NNq8A&oe=689BBDEE)

Selecting the UIO Plane will open the properties panel on the right side. At the bottom of the properties panel, you can attach a script. We will attach the AnimatedGIF script.

![25 Horizon - Select UIO Object Attach AnimatedGIF Script.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452893310_512510007953622_6953964120795560456_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=7iA9bi28fsUQ7kNvwErUUv7&_nc_oc=AdmUlfSDMkdbd0u8yPy5UE14sPdaMi3oG3T7fHU9YZCUm7_zNayq-ob-NlqjETo_R1c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTRd0vT4M0iYg9xFv_tzBGhvsySeXXRgyQVLvdDFt-6eA&oe=689BB569)

With the script attached, we can now drag the assets into the empty texture slots in the correct order.

![26 Horizon - Reference All Texture Assets To Correct Index.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452597104_512509974620292_7381418665732884630_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=EPaSrIEJobsQ7kNvwEg8f_W&_nc_oc=AdmplQuzSdpj9VKZ6t1v4cJz8ostS4FWaEVrxp3fWjDUGeEuunS12rmvkuIwVfYdP80&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSpSIVsMAvIVVtsna7_OjjxgGQYKRdHCjtl56QDvNn_dw&oe=689BB35F)

![28 Horizon - Not All References Required Change Speed.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452934376_512509991286957_335261093369493818_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=cstt_mesX_oQ7kNvwEr9RqG&_nc_oc=AdmdjQo0UPGxtUmw2KpsTBK8RMJT7HEXzri0fIKm4RZxESoh6VoS1iWckzetmlhK3IE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSfEt_D2HhJgY_TOujlu1ko0jnogGZZhHhexOXM5D363g&oe=689BA049)

With the texture assets referenced, we are almost ready to test the script. Notice that not all texture slots need to be filled out, the script we wrote and are using is intelligent enough to ignore these.

Before we test though, we should adjust the speed parameter to better match our desired animation style, in this case, I used 0.2 seconds.

Now let’s click play world!

![29 Horizon - Play World.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452532621_512509987953624_4411056457549309049_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZZF8-lkkgXoQ7kNvwHKNKAM&_nc_oc=AdlqC_TPmTkCgyekl_omlZjijJlVn0VW1WywHG-Ho8wRlQ-Aa03-T2puIeMDwEQGJFM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQvDItPQuQmb7FaHt9oIra8Te6d51ZYgSBZ0FH0djqwUQ&oe=689BADCB)

The speed was a little slow, so we’ll adjust to 0.1 seconds. You might have also noticed that the first play through the loop had some hiccups due to needing to download the images, but after it played once, it was smooth.

![30 Horizon - Adjust Speed To Your Liking.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452933994_512509984620291_3491567733690113088_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=5NLtdiP7PoYQ7kNvwG5hkut&_nc_oc=Adl1mJFvPbTd2_sDeJ3A7SOEcs-dZpJte2kyy6pEaXi20ozk7kubHK9SlXnxpmvSKnY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTGFQhtgRVd7fzhKdQrYuoXTOYQ0y92ld6vYJewC3TZuw&oe=689BA6FB)

![35 Horizon - Billboarded Nyan Cat.gif](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452540279_512509977953625_2643885165784093538_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=s0yc-avqThgQ7kNvwEl1041&_nc_oc=AdnAG6jlesQfjoC2Gdc2pztTaWdVsY962nBHURKTl4OL7oRUuH4pRPtskdNmXCX8ZQM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRqsvPMO3aSXrngqiq8eUcqNn7SH-od17oFmxKxlWNBkA&oe=689BBD67)

## Step 7: Billboarding

This looks good, but only from one side, it would work great on a wall, but what if you want it to float freely? In that case, we should billboard our GIF!

As of the time of writing (June 2024), billboarding can only be applied to grouped objects, not singular planes like this, so we will need to duplicate (Ctrl + D), and then group the two GIFs. After grouping we will delete the extra GIF.

Note: You can select two objects in the hierarchy on the left side by holding shift or ctrl, and when you right-click the selection will have an option to “Group selection.”

![31 Horizon - Group With Some Object.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452853527_512510001286956_2716518458353739131_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=yc4Y8hdGnZ8Q7kNvwE9lOz-&_nc_oc=AdmUUoeHbq0NYQ8CEQssbGt6DV7fduU9XDbHYReshU30wqObjNyhOwCxiuhPIH-9rdk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfROLeAhOEZ45AJA8UOn0Kl1pBEFtb5TJykMEH-jk_6UZg&oe=689B9A19)

Afterwards, we can drop down into the group from the hierarchy, and then right-click to delete the extra plane.

![32 Horizon - Delete That Object.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452415046_512509911286965_3425181708830011765_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=gMdl-jj8r1AQ7kNvwHKZBeO&_nc_oc=AdnOwXWxr69S0SUiNq-fPqUgjLScBiNRCRve1Noxkp8L_Q7AzaUljH_e5OhnP9EM2yU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfThiSRYxCgsloqMtZzIBnYD6PSZtSeTJ1Tbqy8xzsGEjg&oe=689BB6A3)

To apply billboarding we will select the \[EntityGroup\] from the hierarchy. On the right side properties panel, set Motion to Animated, which will reveal the Billboard property. You can then select Lock-Y or Freeform from the drop-down.

![33 Horizon - Select Group Set Motion To Animated.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915492_512509907953632_8557229846459868426_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=lLIjOPCPnVIQ7kNvwHoNGHG&_nc_oc=AdmgVMAbKYey16qWWIr7sRi0MSN5VPY4wMH9KbBy8c8WcNesHP8aQ-gOiC9MR8RGjvU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRx6oAqRRum2Iyl1iVTifrbK5YwoqTPXysU5ajQb2Vc1Q&oe=689B9E2F)

![34 Horizon - Billboard Freeform.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452513071_512509904620299_6429956925647591739_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=UImLbBVVRlsQ7kNvwHMcTY-&_nc_oc=Adkf2dh_TB8RlYhJmGX45qv95xvGw-18DF-Q5LCoVBErEtsBYbp2XohrokGNxzq54hk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQMluQbOVNsFcu3n0fhTzc4nHvIC20wXIdTWZKhl3V0RA&oe=689BA8CB)

Now start the world and run around in preview mode!

## Step 8: Texture Trigger

This script will allow visitors to change the texture of your UIO mesh, one texture at a time. It will run on a trigger gizmo, so let’s start by pulling one out. We’ll also need to be able to see the trigger in preview mode, so let’s grab a cylinder to use as a placeholder for a button. You will also want to bring out a new UIO asset. We can then position everything in our world.

Select the trigger, then attach the script to the trigger gizmo from the bottom of the right-hand side properties panel.

![39 Horizon - Bring Out A Trigger Gizmo.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452615830_512509897953633_5127349402886952232_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=KxK0JWICyKMQ7kNvwHMV6GX&_nc_oc=Adn_J_yu29uz7EpVTZAUrvY44xCH1kJ4ODISZ3ZRSwBY0JRKYpHnU7k7QmH2J-6BTbU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQVRWhdOYGfNKJ5l8rlIbgF4pHtbDkpSM9QXBYdFLjc_A&oe=689BC833)

![40 Horizon - Bring Out A Button Shape.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452752337_512509887953634_7522440812087672101_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=PQGJEIiZJ5YQ7kNvwH-TfIh&_nc_oc=AdlRvShoIY20Gp75evZsFsE6SNHHSZo3oRzSBQyGbkqYYhcXSIUH22-z6Yy4ylAJdcA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfR5jXwZcd90-ZVfG6t3sdRIcDcnimMHG_jJ1H_vYHbi_Q&oe=689BB527)

![41 Horizon - Adjust Scene To Your Liking And Select Trigger.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452916233_512509894620300_8243052218315123329_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=v5iOcAdohEEQ7kNvwGZ47Pl&_nc_oc=AdnoGEwOV-MGzfhww6_4X_zf8-syBUIBVJ1wvrc3rOdwdAbRl2xRywcW5Ms7Ob0L5BI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfQKTGMMeDMoXcoMw_96B5jf8Y_3twaOlngtHG3cy8gPPw&oe=689BB4CD)

![42 Horizon - Attach Script.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452628926_512509891286967_3053857877730824769_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=K_mwJgp1P3QQ7kNvwH0GJSR&_nc_oc=Adm0Eq-C5Mb4HTnOAN4mwS78aiUJPw0ox2cHNsi6X158jgkUkDR4oEQqOlBcjlYm-wc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTaLMw9SHjvu2HedyqOu5iWSzOqk2rcges9Xh7MoEPpSA&oe=689B9D02)

Select the UIO plane, and give it a good name so we can better identify it.

![43 Horizon - Rename New UIO Object As NyanCatFrameByFrame.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452888016_512509881286968_98449028924003563_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=IRAdAJCuxVoQ7kNvwECXc0n&_nc_oc=Adm9zVn-0bms76-mO3Q9zYmdhS2OWJyNl_TBKcPpEZPJ5rDVC9b5feaBDIFTd80krlA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSthSoqzT0zdaLp9ua_7CPtSUmlsI8f8hNI_2UpaBN5DQ&oe=689BAEF3)

Select the trigger gizmo again, and now we are going to fill out the uioEntity reference. Clicking the empty pill slot will give us a drop-down, and we can even type to search for our UIO plane.

![44 Horizon - Reference NyanCatFrameByFrame.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452413127_512509874620302_6306166632729951456_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=H6sSs5rQplYQ7kNvwHYsY2W&_nc_oc=AdnYUfRS773Lwi6X2NjAsrhBO-Gdc8fgzPmJqj02kaH11TfBBFxH58-zR61ACZyuEbU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfToCfu0E5ejMvNNr7gs8k7MkyCwLgFHP4XQ0EhTD13Nug&oe=689B9607)

After filling that out, we still need to reference the texture entities. We can do that the same way we did before for our GIF animation.

Once it is all filled out we can test. Note that there is an optional startingIndex property. You can use this to set the texture you want the UIO plane to start with. But, it only works if you have no gaps in your references up until that index (otherwise the values will be off by 1-2 or so).

![45 Horizon - Reference Desired Frames Optionally Change Starting Index.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452415063_512509871286969_397156706064990581_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=_njd240quZ4Q7kNvwGGxfd8&_nc_oc=AdmDdqhgQzpDe4DnwOHwIFldV4E_jooRWMwSV8UCZxeqP6VXocST53oHXNIZaqJbsnw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfS6AToUIzwodNxtJdTnZ02zdEfOptwfAm8DKalE-PWAnQ&oe=689BCAFD)

Going into preview mode, you can now jump up and down in the trigger to test that it changes the texture, moving forward one frame of the animation at a time. This would be great for an instruction board, or anywhere you want users to be able to customize their experience (ie. a skybox, wall art, etc).

![46 Horizon - Jump On Button To Test.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452663326_512509884620301_5661988945403216671_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=hfr02QSs9lwQ7kNvwFC-GNT&_nc_oc=AdlNWVbykN-WqdI9DCDCD7iMbybbrLQCLBcO3CKOHe41P0Gj22AR6KzuCKUvxLw_o8s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfSLMpvMpeDdyuWlFv_ByMQL0OsUtq8EkypRaEdMYC-0LQ&oe=689BAD65)

## Step 9: Add More Textures

If you need more animation frames than the default 15, it is relatively easy to add more to the script.

You’ll first want to create more texture asset references on the properties panel. In Typescript we often refer to these as “props.” An easy way to duplicate is to click on the far right of the texture15 line of code, then Copy and Paste (Ctrl + C and Ctrl + V). You can paste as many copies as you would like. Then rename them, incrementing the number upwards.

![36 Horizon - Duplicate And Rename Props To Add More.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452587750_512509877953635_1060541854433685900_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Mnobf-pOjGYQ7kNvwEai8OC&_nc_oc=Adl0iNmenc8ilgNl8CfgvL441ZOGcqDaVz6JkLuP_ug7ymR8lloaoVpPQOUCf8YOmEw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfRo-f1bN1BAdwdgOTXI2S3Nb1V8snGu8bXn5Ms_4eIcVQ&oe=689B9C9D)

Next, we’ll need to add these to the “textures” array. Note that in Typescript an array is similar to a list in Codeblocks. While learning Typescript you’ll find a lot of terms from Codeblocks have similar but different names. For instance, you’ll often hear objects referred to as Entities, this is because Object is a type of data in Typescript.

Next, we’ll duplicate the addTextureToArray line for each new prop added, also renaming to match all the new props.

![37 Horizon - Duplicate Add To Array And Rename.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452916434_512509867953636_5718596235244147160_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=Q_v10T7XLb4Q7kNvwEUulSn&_nc_oc=Adnm43OJD3F_3_wpDn_LCRFGTT0PHx-o9S6z8i1feqC6hFXzXMgqxpIM2reIxGjNC-g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfT49xXVFa3bnCX3bLGbnDB1zahekq4X6kVizSg_YMWu8g&oe=689BAC83)

A couple of quick things about this “addTextureToArray” function: we call a method or function, these are similar to events in Horizon Codeblocks, but different because they happen instantly. They also require parentheses “( )” to be called, otherwise it is just a reference and nothing happens.

Inside the parentheses is where we put parameters. Below you can see we receive the parameter “prop” which is either an Asset or undefined. It might be undefined because we don’t have to fill out the texture on the properties panel. We account for this using an if statement to check the truthiness of the prop.

![38 Horizon - Create TextureSwappingTriggerScript.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915631_512509861286970_8320013039747796277_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=RWefG3oZ8xQQ7kNvwEHGEzu&_nc_oc=AdnsrbcaXsRrT2vBqpGPhI4yGIat7pv10jsXV3cKyofCuv9YR6UN3Np6dTePhw-ub0c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=7xYilm5EklyZa7SFBIXLjA&oh=00_AfTcLZKEueV6Btmq5jt_KxsKRwwyq3KzDXlRJIONw5TUJg&oe=689B9570)

A lot of this will feel like magic early on, and that is totally okay! Over time it will begin to make more and more sense.

There is a lot to learn in TypeScript, so if you have any questions about the code or want to dive deeper into how it works, be sure to ask in Discord, or check out some of the other Typescript resources!

## Extended Learning

Below we have provided some CMI and Scripting challenges for you to try implementing on your own. These require some outside knowledge, and we encourage you to ask questions in Discord if you get stuck or are unsure how to complete these or book a 1:1 mentor session.

### CMI Extended Learning:

#### Novice

Using the “TextureSwappingTrigger” script allows visitors to customize their experience in your world (ie. custom textures, pictures on walls, etc).

#### Intermediate

Create a fire. Either using a 3D model with an animated texture, or a 2D plane plus billboarding.

Tip: Some fire animations only look good on a billboarded 2D plane. For a 3D model, consider having intersecting planes floating above for the wispy elements of the fire.

#### Advanced

Try anything with a 3D model rather than a 2D plane. If you accomplish this, share your success in Discord!

## Scripting Extended Learning

#### Novice

Build a button using the “TextureSwappingTrigger” script so your visitors can adjust a skybox or some other texture, allowing users to customize their experience in your world.

#### Intermediate

Create a grabbable object that when you press the A or B button swaps the texture. This could be as simple as a colorful bouncy ball with various texture options.

Tip: Our trigger script uses “onPlayerEnterTrigger,” you’ll want to use a different codeblock event, when you backspace the current event name and the period and retype the period, you will see a drop down list for all codeblock event options!

#### Advanced

Add custom VFX. Think muzzle flashes, sparkles, smoke, or if you put the animation on a 3D object (ie. a cylinder), you can attach it to a player and make custom player effects like leveling up, taking damage, healing, etc.

Tip: You’ll want to have a way to run the animation X# of times. And either an off texture (ie. 100% transparent/masked), or set the visibility to false when not being used.

## Further Assistance

For any questions or further assistance, creators are encouraged to join the discussion on the Discord server or to schedule a mentor session for personalized guidance.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 