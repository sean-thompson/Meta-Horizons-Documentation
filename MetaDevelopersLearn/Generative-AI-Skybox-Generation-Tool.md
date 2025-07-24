# Generative AI Skybox Generation Tool

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/generative-ai-creation-tools/generative-ai-skybox-tool)

The Generative AI Skybox Generation Tool allows you to dynamically generate skyboxes for your created worlds. This tool helps streamline the process of world and environment building while also allowing you to iterate on the generated assets. This doc will cover how to:

*   Generate a skybox in Horizon and its associated styles

*   Export the asset(s) to your asset library

*   Download the asset(s) to your local machine

## Prerequisites

*   [Horizon Desktop Editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor)
    
     installed on your PC.

*   One or more 3D models imported into your [personal asset library](/horizon-worlds/learn/documentation/desktop-editor/assets/creating-importing-viewing-and-spawning-assets#importing-assets) in Desktop Editor.

Gen AI Tool Availability & Rates

Horizon desktop editor creation tools with Gen AI are currently only available to users in the United States, Canada, and the United Kingdom (UK) aged 13+. Note that there are daily rate limits per user on content created using Gen AI. Additionally, there are daily rate limits per user on content created using Meta AI. These limits are:

*   Typescript - 1000 requests

*   Audio SFX/Ambient - 200 requests

*   Skybox Generation - 50 requests

*   Mesh Generation - 100 requests

## Skybox styles (models)

The skybox feature offers different models that can be used to establish a style for your generated skybox. Below are the currently available skybox models generated with the following phrase: “A view of a nighttime sky with an aurora. rolling snow-capped rocky hills barely visible far out in the distance.”

*   Skydome - A traditional skybox featuring wide open reflected horizons and realistic rendering 
    
    ![generated skybox in the skydome style](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484843258_675614044976550_7641456277170156748_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=dgqjhjC348wQ7kNvwFxx306&_nc_oc=AdktB5xv262JkqK59qrWS67QU4KL983miaejxnBsWKpJUsn-yV6gSeV-62XgoDJf5I0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bbjA1tkg8BuaPqTyIGZ_UQ&oh=00_AfST-ybO2amV5Gc-HkvCjTkKPjLcYqkLADO3vfL_IfstFg&oe=689BB3A6) 

*   Photorealistic - Photographic realism with good visual fidelity 
    
    ![generated skybox in the photorealistic style](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/485160468_675614048309883_7846075386437929284_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=o2Ls2cNfLngQ7kNvwE_-jq9&_nc_oc=AdkMPw8cnFMgq_tCT2Q6bY5jdDEz5OP-QGZIeiUY-nmi0lxd0EDUQ4Msd-7Bh0fnUB0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bbjA1tkg8BuaPqTyIGZ_UQ&oh=00_AfTd3NKYKM_AohHB7up8LMwlgXbDZ8P8bkL3TshPtv9Dhg&oe=689BAEEF) 

*   Digital Painting - Digitally illustrated concept art

*   Open World - Pastel paintings of beautiful worlds 
    
    ![generated skybox in the open world style](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484265621_675614038309884_6466651506436893979_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=l-waLrqTNt4Q7kNvwHkJFSr&_nc_oc=AdkD_BM7gOAMgSrrzqE7EOJ38lpsaRHk-bz8gsWbM7skjy_UVMYlUP5rjX21L9CSPWQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bbjA1tkg8BuaPqTyIGZ_UQ&oh=00_AfTrmxMrsZy2Pa3wt91WJ2WHlx2Y1X2ugd6L_LqlVlpnxw&oe=689BAAD2) 

*   Anime - Bright and cheery Japanese styled animation 
    
    ![generated skybox in the anime style](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484725101_675614031643218_6452299790829256071_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=xmEwte880YQQ7kNvwHhyoCh&_nc_oc=Adlq67EtTSqZWQ4_vc-0ymCybt0fr-ITYf3V1qny_G4bi-3ZwhU3SnWF4hxkLyllnNU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bbjA1tkg8BuaPqTyIGZ_UQ&oh=00_AfS0aEX4y23yPMN3M_8BVh0eWVG9Pu1QuOciZHSGsjXq2g&oe=689BA34F) 

*   Comic - Cel-shaded illustration style with clean lines and bright colors 
    
    ![generated skybox in the comic style](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484918867_675614041643217_5716770861462679951_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=e79ti_dD2SQQ7kNvwGtLGct&_nc_oc=AdkXDyZBWIi_KrvtLuV8hDFELytCI6WfztE76mNB1VHmynX1Zs_uXdQ8TWMUG6NodKk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bbjA1tkg8BuaPqTyIGZ_UQ&oh=00_AfQ4MxoGJES2laEAMjBKiDF_EsgZ5rEkjC-VeQ0ttEV8Yw&oe=689B92ED) 

## Generate Skyboxes for your world

To generate a skybox for your world, use the following process:

*   Select the GenAI icon from the toolbar, then select Skybox.

*   Enter a prompt into the prompt field and select a style to base the generated skybox on. The Horizon GenAI tool will then generate several skybox options based on your input prompt and selected style.

*   Once the options are generated, select one of the generated options to create a preview of the skybox. You can use the **Style** drop-down menu to select one of the six available styles for your generated skybox.

*   Once your skybox options are generated, select the option that most fits your created world.

## Save your generated skybox

Once a skybox has been generated for your world, you can save it to your asset library.

To save to your asset library, hover over your generated asset and select the **Export to asset library** option. **Note**: You can also download and save your generated skybox to your local disk using the download icon.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 