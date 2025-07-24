# Text Entry and Formatting Tutorial

[source](https://developers.meta.com/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/text-entry-tutorial)

In this tutorial, you’ll explore efficient methods for importing and manipulating text in Meta Horizon Worlds using TypeScript. You’ll learn the simplest ways to integrate large blocks of text, to format text using TypeScript code, and you’ll even learn how to create text dynamically.

You can use the example code in this tutorial can be used by creators of all skill levels. Don’t worry if you’re new to TypeScript. By the end of this tutorial, you’ll be able to import text, format text, and create exciting, randomized game mechanics that surprise and engage your visitors.

*   Creator skill Level: All levels

*   Required background knowledge: No prior skills required.

*   Recommended background knowledge: Horizon Desktop Editor, TypeScript, VS Code, Codeblocks. **Note:** This tutorial contains TypeScript code that you can download. This code was provided by MHCP mentor Laex05 and Vidyuu team. If you encounter any issues with the TypeScript code, you can contact info@vidyuu.com, or Laex05 on Discord for assistance.

## Learning Objectives

To complete this tutorial, you’ll complete the following tasks:

*   Learn about formatting options available in the Text Gizmo using TextMeshPro

*   Write and edit text using the Horizon Desktop Editor directly on TextGizmos

*   Easily place TextGizmos using the Horizon Desktop Editor

*   Send text & text arrays from TypeScript to Codeblock scripts

*   Request from and send random questions and answers to Codeblocks from TypeScript

*   Receive text in TypeScript from Codeblock scripts

*   Create a “MegaText” script in TypeScript, which can be used on desktop and in headset

*   Write text with formatting in TypeScript

*   Write text with the Vidyuu formatting library in TypeScript

*   Basic ad-lib story generation in TypeScript using string array imports

*   Advanced ad-lib story generation in TypeScript by picking a random story template and random player name

## Text Gizmo Formatting Cheat Sheet

When writing text on the Horizon Text Gizmo, the formatting options listed below are great for creating rich text and style. In the “text” property of the properties panel or using “text.set” in a TextGizmo Entity in Typescript, you can insert these codes to create the associated formats. These work because the Text Gizmo uses TextMeshPro (notably the Custom UI Gizmo does not support TextMeshPro formatting options). TextMeshPro is built into the backend of Unity and thus Horizon. It is what enables these formatting options. It is not specifically endorsed by, or made available by Horizon, but it has been used by creators for years to create stylistic text. Consider downloading [this image](https://drive.google.com/file/d/1YhXm8MMNFZ_b8mO0Ec4fSs75S4uKEN4r/view?usp=sharing) and keeping a copy of it in a convenient location for all your Text Gizmo formatting needs (reminder these are not supported on the Custom UI Gizmo).

The Text Gizmo in Horizon can hold up to 1000 characters. This includes formatting characters. This limit is easy to hit when you want to create rich text blocks. In many cases, it might be useful to use multiple Text Gizmos. The new Custom UI Gizmo is also a great option, but it has a steep learning curve, and creating rich text is a lot more difficult as it uses CSS-like styling (but more on that in a different tutorial).

## Text Formatting Options

*   **Sprites (Emoji)**
    
    *   `<sprite=0> 😜<sprite=15>`
        
         😍 (values range from 0 through 15)
    
    *   `<sprite=”dropcap numbers” index=0>`
        
         (values range from 0 through 9)

*   **Subscript & Superscript**
    
    *   `<sub>subscript</sub>`
    
    *   `<sup>superscript</sup>`

*   **Character Spacing**
    
    *   `<cspace=1>S p a c e </cspace>`

*   **Line Height**
    
    *   `<line-height=0.1></line-height>`

*   **Alignment**
    
    *   `<align=left></align>`
        
         (options for left, right, and center)

*   **Color, Highlighting & Transparency**
    
    *   The easiest way to color text is to paint the gizmo using the paint tool
    
    *   `<color=#ff0000>Red<color=#00ff00>Green<color=#0000ff>Blue</color>`
        
        *   RGB colors using hex values (where 00 is 0%, ff is 100%)
    
    *   `<color=#ff000080>Color With Transparency</color>`
    
    *   `<alpha=#80>Transparent</color>`
    
    *   `<mark=#00ffff7f>Highlight</mark>`
    
    *   Solid Transparency For Windows `<mark=#00ffff7f>[TAB] </mark>` *   Press \[TAB\] on keyboard in Horizon

*   **Italic, Underline, Bold, Strikethrough**
    
    *   `<i>Italic</i>`
    
    *   `<u>Underline</u>`
    
    *   `<b>Bold</b>`
    
    *   `<s>Strikethrough</s>`

*   **Linebreak**
    
    *   `<br>`

*   **No Parse**
    
    *   `<noparse></noparse>`
        
         (show codes like these)

*   **Font Size**
    
    *   `<size=1></size>`
        
         (relative to size set on Text Gizmo)

*   **Equal Spacing**
    
    *   `<mspace=0.1></mspace>`

*   **Uppercase, Lowercase, Small Caps**
    
    *   `<uppercase>UPPERCASE</uppercase>`
    
    *   `<lowercase>lowercase</lowercase>`
    
    *   `<smallcaps>SMALL CAPS</smallcaps>`

*   **Position & Offsets**
    
    *   `<pos=40em></pos><pos=60%></pos>`
        
         (horizontal position)
    
    *   `<voffset=2em></voffset>`
        
         (vertical offset)

*   **Rotated Text**
    
    *   `<rotate=-20>Rotate</rotate>`

*   **Font Options**
    
    *   `<font=bangers sdf>BANGERS SDF</font>`
        
        *   Other Font Options:
            
            *   Anton SDF
            
            *   Roboto-Bold SDF
            
            *   Oswald Bold SDF
            
            *   Electronic Highway Sign SDF

*   **Font Materials**
    
    *   `<font=anton sdf><material=anton sdf - drop shadow></material></font>`
        
        *   Try painting some of these different colors
        
        *   Other Material Options:
            
            *   Anton SDF Outline
            
            *   Bangers SDF - Drop Shadow
            
            *   Bangers SDF - Outline
            
            *   Bangers SDF Logo
            
            *   Roboto-Bold SDF - Drop Shadow
            
            *   LiberationSans SDF - Metallic Green
            
            *   LiberationSans SDF - Drop Shadow
            
            *   LiberationSans SDF - Overlay

*   **Gradient Options**
    
    *   `<gradient=”Yellow To Orange - Vertical"></gradient>`
        
        *   Other Gradient Options:
            
            *   Dark To Light Green - Vertical
            
            *   Light To Dark Green - Vertical
            
            *   Blue To Purple - Vertical
        
        *   The color is sret to white, otherwise the colors blend together:
            
            *   Text painted pale green
            
            *   Text painted purple
            
            *   Text painted green
            
            *   Text painted yellow
            
            *   Text painted white

## Edit Text Using the Desktop Editor

In this section, you’ll familiarize yourself with the Meta Horizon Worlds Desktop Editor. You’ll use it to create a new world, and then you’ll add a Text Gizmo to it.

To complete the following procedure, you’ll need:

*   A Windows computer.

*   The Meta Quest Link (Oculus) app.

*   VS Code. **Mentor’s Note:** I recommend creating a new world to serve as a playground for experimentation before starting. As an example, the image below shows this world is named “Text Tests” with the current date in parentheses.

*   Launch the Meta Quest app.
    

*   In the Meta Quest app, navigate to and start the Meta Horizon Worlds app in Desktop Mode.
    

*   Create a new world. Give your world a name, and then select **Custom Model Import**.
    
    ![Select Custom Model Import](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468198625_595241713013784_8092391770579618737_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=YFU_EWqgo_IQ7kNvwEn6koP&_nc_oc=AdlbeC8k3_-OBrK0HU8y9RgU9aPLqjFWCmidKIb8YKSxqOHphJ8Gy91RWijtJBJ1jYo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRExRKK3pvfig4_ZH6mxmf-sNBBQhXXeEHBCz2vi8dyqA&oe=689BADD4)
    

Adding the Text Gizmo, to a scene using the Desktop Editor is difficult. Meta recommends that you add the Text Gizmos in VR. But writing text in VR is also difficult, especially if you want to add any of the formatting options. If you want to use the Desktop Editor, see Adding text gizmos using the desktop editor.

*   Add a text gizmo to your scene.
    

*   Select the text gizmo from the Hierarchy.
    

*   Edit the text field in the Property Panel. You can also adjust properties, like font size and color, just like you can in VR.
    
    ![Add the Text Gizmo to a scene use the Desktop Editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467769589_595241743013781_7349902689390694342_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=f1aYze3yNrsQ7kNvwE-CGij&_nc_oc=AdlgTnCYVHSzBKTgKZhx0ilacq91FuWKNcFmDIuM0sN0c9pzUmuqUfyuRyOYnZQDBDg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTANleUVDVE7X96J1J0u3Fh7kjr-haPGIyGuj7N6hlmlA&oe=689B99E9)
    

You can use the text field to write text and to copy and paste text into the text gizmo.

## Adding Text Gizmos Using the Desktop Editor

Here are some tips to help you if you want to add a text gizmo using the Desktop Editor.

*   Add a text gizmo to your scene, here are a couple of tips to make your life easier.
    
    ![Add a text gizmo to your scene](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467842483_595241769680445_620494155645858280_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=Z02ozlm5a-UQ7kNvwELDsYD&_nc_oc=Adl0mj1V8v6jzrs51abI6HKYCdTy72wPCUw-_ahsKokMsHN4_4HScv8wgGUWM82zkXQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTmP9wK7e9zgZPFxs5D4GvOodDsDZAD9k3yalnyihOGeQ&oe=689BB176)
    

*   Add some filler text on the properties panel, in this case, in the image below, we have added “Hello World.”
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467879381_595241639680458_9173102621139393361_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=FsLJrx__C5UQ7kNvwHlzXXG&_nc_oc=AdkORXS078mgbhW6y6BzvDqO2W0_4hfCByyn1C3CWCwX4obldNGAN1ZanrOF1QRXRF4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRRBFJ8E6d67H3YmtUGWZ_bU0gqGoq1lzqyUBtc9qyJIQ&oe=689BA98D)
    

*   Then, presuming you have an object you want to place the text up against, click on that reference object and right-click to copy the position of the reference object.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467856751_595241789680443_6078805237931826866_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=RupGxBTLCHwQ7kNvwFizZGt&_nc_oc=Adm-bQBPE_2ypKf2p0wuGdgiSZ8C-le1x1ZAGPkBIyT7mfQgsEDWLsu9ACCQfU1v72U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRCb2Surg0WI7mPtGBy3uquSsuNopZSijNP0v9dZvyIsQ&oe=689BB897)
    

*   You can then click on the Text Gizmo and right-click to paste the position. You may have to repeat these steps to paste the rotation from the reference object as well.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468018101_595241793013776_4213593910410519336_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=gk8IekFBHcAQ7kNvwGA69x-&_nc_oc=AdlnyBtyidADVBvUwxdbWY8uvD95XHLjZ84nZqMUgdU1h4GqpsnuL52l9zsowfjGuzU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQlDvN9jjY6DvEdysVmfeScgzqmYeXjGDoZvnJgW7DiSA&oe=689BB872)
    

*   Then, with the slide tool selected, and snapping turned off, grab one of the slide arrows to pull the text out of the reference object.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467952672_595241726347116_117331172420294193_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Da8GyC8WxwkQ7kNvwHOmRr3&_nc_oc=Adl710ZdtmSS1F3RuIYumFaM3p8_-hbNv2cITnpupuysJQcDFKkY5Ll7L8bBFeVxlQc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQ82VWfucZQE626wpsRRbGCa3QLPx2sN8wcOy_Ol-eYhg&oe=689B9E3E)
    

*   Now that you have positioned the text, it may need to be rotated. If you copy and paste the rotation of the reference object, and it is still off, you may consider manually adjusting the values from the properties panel. Or you can use snap rotation, I like to set it to 90 degrees.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467899374_595241633013792_7017878112968153930_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=VWG0LCjLoQEQ7kNvwGsyI5h&_nc_oc=AdmbKOBTdldZOk0ZxXSqTVVLTQy-o6cBRe2pHtLMklBdxjahQueNqmN2_Kdal3UE_dA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfSZTIqGpP_mdVacjPbIkCJbyh_oALDoDSgkQl1Py0BHFg&oe=689BC842)
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467842237_595241629680459_7331484596920045925_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=WPkm47qiW5oQ7kNvwEd11p8&_nc_oc=AdkhQdCbrvvI_HFESai0ObTGveQnn0pJflJjwt5h9lYSc-nrQI50G9xv0Ozpnp53pSM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfSX3_7qI7Y150E3WGZTFn9S938vCEamSq8H67dEdxYQQA&oe=689BAC02)
    

You should now have your text positioned and can fill out the text and properties to your liking.

## Script 1 & 2: Send String(s) from TypeScript To Codeblock scripts

In this first script, the goal isn’t to cover advanced TypeScript concepts but to simply allow you to use TypeScript code to augment your Codeblock scripts that need more rich text. You’ll do this by sending a string variable as a parameter. This can also be a list of strings. The script calls lists in TypeScript Arrays. It alternates between those terms in this section, referring to them as Lists when talking about Codeblocks, and Arrays when talking about TypeScript.

It’s important to start by noting the limitations of Codeblocks strings and lists. Both are limited to 1000 characters. There’s a maximum of 1000 items in Codeblock list, and a maximum of 1000 characters in a Codeblocks string. These limits don’t exist in TypeScript strings and Arrays. This is why you should consider learning TypeScript. TypeScript doesn’t get around the 1000-character limit of the Text Gizmo, so you might need to divide your text into multiple Text Gizmos.

This tutorial uses the Meta Horizon Worlds TypeScript 2.0 API. which as of July 2024 is the default, however, if you are not in 2.0, you may need to adjust your version from the Scripts tab, select the gear icon, and then Settings.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467842517_595241733013782_2128132337469528118_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=5aH59VWCkAcQ7kNvwHyPDEz&_nc_oc=AdnOs4ViWue3fBtomBc8rb54j3XY4dt2pX2HnvEJRgOzXs1x1aJ3jN-nMrhR9HlF5nc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRTi5tNr3U9hZIrFEYYA41O_fBtw3kHfzQtNXWO4DiGPw&oe=689BA7F3)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467676822_595241729680449_3367236753877387468_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=WRm1TLz42YUQ7kNvwH-pgqP&_nc_oc=AdnPlUJF-a29HOnJZTkabVmrK3F4G3oa2aJkUbXgEuQodVXBi-HLD6zhRVodqST1goI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRACk-YSx_knubalcG9wf0WEhgxmgk_8mNcn-1e1MqomA&oe=689BAE19)

*   If you would like experience writing TypeScript you can create a new script from the Scripts drop-down, in this case, we will name it **SendStringToCodeblocks_Entity.**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467776400_595241636347125_7347996169623556433_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=SpmEwgXoTWYQ7kNvwHeoG7o&_nc_oc=AdnRIZy8Q2da37kR-ZFjnkNHlbaY9Do0z3xb7QEDjVil_o-fUA0uR5CK8pdflOyQUDA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfS8b337ZZb8wseMollv8fZ9JR9b0TR29K7yxhHqkIL_eg&oe=689BA542)
    

*   You can then write the following script out.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467812886_595241736347115_791166171449353852_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=jO4OH-lNM-YQ7kNvwHyk4_J&_nc_oc=AdlXyftIs9KmgVzb7NMv82stsQ1e_drHDONcJR83A7YRQu7YYp5S9V6naov0tF01jjM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQFsBFeKXNJspKCQifo_eu8kok70qGQjUJFabyiu8Wo1w&oe=689B9AC2)
    

*   If you have never used TypeScript before, you should download this script by [clicking here](https://drive.google.com/file/d/1aYxgHRxceWXIJ8epHN01XXvWdzKKZ9s_/view?usp=sharing) .
    

*   Open the Scripts folder. Click on the **Scripts** drop-down, then select the three-dot icon, and “ **Open the Scripts Folder in Explorer**.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467745430_595241703013785_5034482498143521700_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=3z0OYrgFu_wQ7kNvwFLeOTT&_nc_oc=AdlkW_lPS2hjkvBArYRQMM9rO9XM6wwm08fUE2J786HkIaBdSoR50aYRT8nzd_SboJI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfSdNENFJBhCbaVLwyjfq3ii0gP8mQQwYm-yzJzFepjGdQ&oe=689BC1F4)
    

*   Drag the script into the scripts folder.
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468101013_595241763013779_4449412052777928746_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=dfXEqaI0Rp8Q7kNvwECIe4v&_nc_oc=AdlOoDd5pd0RbaoxDKYuY_5JvPoDJrk4Nr8OQyB8yh1RkP7mGJWEjg82NOsqNm1pQQo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTI9JZYMMMsAksRT5iS0xVIF2EXsVtb6kO7FiMNOfhXXg&oe=689BC0F9)
    

As you are writing or downloading these scripts, here is the second script you will want to [click here](https://drive.google.com/file/d/1aRek4QMU_r3GB-YstadaXiTX2IVtH8aY/view?usp=sharing) to download.

Create a new script. Name it `SendStringsToCodeblocks_Entity`.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467993616_595241686347120_1623269506850882067_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=IqxG4R_5t8wQ7kNvwGXCWfN&_nc_oc=AdmPnlIN-1QC_nPGT3vEmTJqYZC0ClYGieeqdeLJusJZnnEcU1BC_efIjxNcZM0oIoY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQOtHjHJyWu0MBYPLeGI67xZvmnt4kFdR3uj8n5w4z7OQ&oe=689BB036)

These two scripts serve slightly different purposes, the first one is for sending a single string, and the second an Array/List of strings. Unlike Codeblocks, not all TypeScript scripts have to be attached to an Entity (referred to as an object in Codeblocks), these two scripts, however, do need to run on an Entity so that you get access to the properties panel, allowing us to reference and send an event to another Entity, one that is running the Codeblock script you want to receive the string(s) on.

With the single string, you can reuse the script over and over, only needing to attach the script to another entity and adjust the “message” being sent from the properties panel. Don’t forget to reference the receiver on the properties panel too (notice in this photo no receiver is selected).

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467821732_595241739680448_6195733651696316672_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=tpVXYzvt6uoQ7kNvwHcMSOy&_nc_oc=Adlf_nvYI026CTjiCLPMyrcN1yXjnjo8xf3HMgSh29dLsbEgk0GdQcuqr_x4l6dN54w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTy1FwhfqaM29q1khGCDmug8A19YJTh20gO5RhhVbgZeg&oe=689BB920)

For multiple strings, you’d need to be more creative with your scripting to reuse the script. So instead, for simplicity, it is recommended to duplicate the script and give it a slightly different name. Note that you will need to have installed VS Code to modify the script (remember to restart your computer after installing). You can then modify the script by pressing the three dot icon next to the script name in the scripts drop down, and clicking “open in external editor.”

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467812284_595241689680453_6429132513994036945_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=Zqk9ufIzKyIQ7kNvwGuINbz&_nc_oc=Adltqq1-vneBHdacOQluLqkUolzkAZ_JKsNmvrlbs4Af4OuHyElzwF1ESaiOCuzh6VM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQ6eX-XMctG0LhMAJE_lfQuw_9dzbSZymJmksCFBX8QcQ&oe=689BAD4A)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467675726_595241693013786_881499020837805569_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=Kb52sLf8XawQ7kNvwFjIZlp&_nc_oc=Adk9rZ-YxmZcP-npnKpR7WnIL_sMOlHVNXUxDgJ6wzw_SLy9oFQ3a2My7gwIp6XaHUo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQqUjLek_m057eGZNJM69eyCuie7ihZnOGEBsKnlvYgsw&oe=689BBCB0)

Here inside VS Code, you can modify the array of messages to suit our needs, adding as many lines as you want.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467699038_595241759680446_1836027078983149650_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=Vqb8G7J4SCkQ7kNvwE2hLLY&_nc_oc=Adkp1CcS9btqfSITQIfFGQPuq9OqY8n5kJAnjy1rIQ495Ko2NuHeWpv6da6QoIHIJUk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfT0jOzVVeKr4LKtLNVb4Lr2NOoihs68GYg5JEAkltpVdQ&oe=689BBBBA)

With these scripts ready to go, you’ll need a Codeblock script to receive the message(s), a very simple script is shown below to demonstrate that it works by printing the message to the console:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467712412_595241706347118_4505531409967578681_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=8QFX2VdsNEIQ7kNvwH1fHu5&_nc_oc=AdkNYUy2mwpqCaJTrG1AYvJrIDaim_LSEsoWynioDmkgd-z3zb9Do6O9NNIrYbU54yY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQliJoe5NfjuHtemhpvrxIl6Kb6jXPfWGQ8vlvSaWT_Qg&oe=689B99A1)

Be sure to attach the scripts to entities. Attaching scripts is done at the bottom of the properties panel. In this case, text gizmos are used to run each of the scripts. If you give them good names, it’s easier to find them in the hierarchy.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467726387_595241696347119_674325849486122084_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=62Q-cyWZbDEQ7kNvwFOW4-_&_nc_oc=AdlbSmTL1SVJArNTi-SoeWVm5X9GaeJ8-UGJTkgcuErDRymCISQSceh5TSRsUtKufNY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTKkShX8KIzPVAl6qejTS_gEombsgPFHSyV9EROV0sjUA&oe=689B9D3D)

You can then drag the codeblocks receiver from the Hierarchy to the empty pill slot (the pill-shaped field in the bottom right corner with a circle-like icon.). **Note**: You can also click on the pill slot to see a list of all the items in our world, and from there, at the top, you can search from the drop-down.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467898774_595241753013780_3884485395764561095_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ai6RiUtVvk8Q7kNvwFvN6v_&_nc_oc=AdmFinNrZJ_9QIVdMAgWf7rKk20F6cI05EFb0t0HkdMb6-ST-3Z1zYkBcIx4lKbk7oo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTAQzTOZVqya0hAASCD3qyvnbdeokR3BeqLW7Dn0RJ25Q&oe=689BBE78) **Bonus Tip:** You can find entities running a specific script by using the hierarchy filter, and selecting entities running a specific script.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467712854_595241673013788_1548314560034761599_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=vSiVUYuFAlwQ7kNvwHbImoq&_nc_oc=AdlFxfy2qb5i4lNW40-jNrw_w7k5i_jpyupnNzNhvj1H094EUKX7wpHCKhE43mzsyQM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfR-753RO7X7tItuRMm0CvDE7y7FuCtl9HpGlk0-yKFcxw&oe=689BC831)

Run the world and see a console message displaying our messages.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467712412_595241709680451_974922764830194410_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=0_T4p1GVIOAQ7kNvwHT4MAm&_nc_oc=AdmvmADCJT4u4w0eELmn971IP6cBSr47D6sSxdh_BZK7BQAsEpFEVwMspxZYbPNwTRM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTXqcy3P3QpmmBwhTwGN7X9zsAQF2K3xtWXEiC7AaUZSA&oe=689B96BA)

## Script 3: Send Q&As From TypeScript To Codeblock Scripts

In this example, you’ll expand on what you learned in the first two sections. Instead of just sending data, now you will allow the Codeblock script to request two pieces of data: a question, and a list of possible answers.

You’ll need to create a new type of data called QuestionData that stores this string question and string array of answers. You might imagine this is a game show, and only the first answer in the array is the right answer, you could then randomly select wrong answers to mix in, scrambling them when displayed to the contestants.

You won’t be diving too deep into this script, which you can download [here](https://drive.google.com/file/d/1sgiIIyd_PrunVMYsv-hAn3cCfHatTf2v/view?usp=sharing) , as it does show off some more advanced features, but if you have managed to do script 1 or 2 in the previous step, you should have no problem implementing this code. **Mentor’s Note:** The “getRandomItemFromArray” function comes from a file that I add to all my worlds, and when it gets updated is shared in Discord. You can download the arrayUtils (created by the Vidyuu team) by clicking [here](https://drive.google.com/file/d/1Wlaru7gyQRTzjov5rACVMsr3lm3pG7PV/view?usp=sharing) . Feel free to ask questions in Discord if you’d like to learn more.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467675376_595241699680452_8898738800974011262_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=mUSu8PI8I-IQ7kNvwEdRFkZ&_nc_oc=AdkJ004tHx2lg88xKgaeBEh0Je9TV3VbNOGR5ZNWtmWXuRblr-4uCjh2GOfEgA0-8Lw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfSFQsL0GbInrMZimShwXXEeptYyxVopW1p-WI6L0iXo6A&oe=689BAAA1)

If you would prefer not to use the Vidyuu arrayUtils file, below is what that would look like. Instead you use a copy of the function from the arrayUtils file, pasted at the bottom of the script.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467811141_595241643013791_6766518816931739561_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=KkRM015PZzIQ7kNvwFCCzi2&_nc_oc=AdmLZyXeak_MbP_-SPieYtOi2DGPmPotzSyh0z5soMwZHXO8w0NZaZFFsKiPK6_RpPA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRQuEwv1OgqimcZB1cV1Prf4v8vl37FAJQCjt3WxnXtsg&oe=689BA08A)

To send this data to a Codeblock script, you created and then used a CodeBlockEvent with two parameters; String, and StringArray. This is received as a string, and string list, as seen in the screenshot below.

Note that this demo Codeblock script, receiver, will also need to be attached to an entity to run, and reference the entity running the QuestionData script. The QuestionData script will also need to reference this “receiver.” For this demo, you get a new question on world start and when received, print it to the console.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468091226_595241766347112_8886608641898299488_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=pxhmmsd9tlkQ7kNvwFmPKZl&_nc_oc=AdmplfQZDwcojEZNOZCpYvansCZtyEHOQeWLd_mOJl-eWZxVx31sCdpHubjsqNa36yE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRNjGglVe6gfPqQ7pPvT_qu8so7dOcfq2zIZrX0hVQFxw&oe=689BC182) **Mentor’s Note:** This is just a taste of what easier text entry with TypeScript can unlock. Really looking forward to seeing how you use this in your worlds.

## Script 4: Receive Text In TypeScript From Codeblock Scripts

Next up we have one last Codeblock integration example.

In this case, you’ll send a message to TypeScript from Codeblocks. You can imagine an event in Codeblocks like this, with a string parameter as the message.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467864826_595241756347113_4361335022965837604_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=kJ_XWmYIqUMQ7kNvwFpQDQA&_nc_oc=AdmuUdEGht1qS9NsEwlt4_rI3dptGnZGoBnulkc9n_Tn85MI1XSoTp9JD_i7z2reGKs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQ-y_yUL9SsZeWkSw36bqdGvZFKUqNM5Yy6c7POw9qomg&oe=689BB8F7)

Then to receive the message in TypeScript, you will need to create a new CodeBlockEvent, which includes a parameter (slightly different from the previous example with no parameters). Then just connect the event like before, and in this case, you will log it to the console to show that it was received. You can download this script [here](https://drive.google.com/file/d/1Q7NFlLBJ6MpjLrh3O5gaYDLdWbrt3ejc/view?usp=sharing) .

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468130683_595241646347124_3219773664877344729_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=_wvcvt1RKPUQ7kNvwHhyrTX&_nc_oc=AdmvQwFP2s7RVaeJaIu88dOZ4Z3TJdxG4OosuvKXArPh6Btd0Aja9w15AOdC3Wq4X-U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTeKYs4X0mGadO4UnN2cb59JWIz9H5cP-i59xC6KjauJw&oe=689BC95A) **Note:** If you are planning to stick with Codeblocks, this is the end of the Codeblock integration examples.

## Script 5: MegaText

If you haven’t used MegaText in Horizon, it a script written by the Vidyuu team in the Asset Library under interactive. It allows you to write text on a Text Gizmo with multiple lines. This makes formatting so much easier. The example below is the same script, rewritten in TypeScript, you can download it [here](https://drive.google.com/file/d/1hKw0YV-o_zjuGbXMPMI1fT1Yo0bfArKs/view?usp=sharing) .

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467806940_595241649680457_6630269722610001617_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=BhTHrx_gGDMQ7kNvwHF_k5R&_nc_oc=AdkXp2Xt8tL-4fjhvFgHjUwQJBrtMpx3iNCGlAZSgx0ot50YMU3dkBYaUf59CrQYEJg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfS_7Y7vKRYs4HrZRkxbu_MMzVNkxJeWotH6hAxkrtAodQ&oe=689B9710)

The biggest difference is that this example only has 16 lines, and the Codeblocks asset has 32. You can duplicate row 20 and 31 to add more lines. Just make sure they are added in order and named appropriately.

To use MegaText, attach this script to a TextGizmo, and on the properties panel you can fill out multiple lines, making it much easier to write large blocks of text, and even add formatting. I’ve always recommended leaving gaps between lines so that you can come back later if you ever need to insert or add formatting styles. You can use this script both in the Horizon Desktop Editor and in VR.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467725469_595241653013790_6628002032060532237_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=ziarkJuESzgQ7kNvwGpN1rJ&_nc_oc=AdnZ5pZFaWWpYXza96Q62GYhhWSZHmNneYQTiH4BFmwL56eBKeT-x0Y9Ev1FakHqm5A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQmy2msX-GpFig8CxWPx4lN34SI81goYtG3blVS8Kvvpg&oe=689B9D9F)

## Script 6: Writing Text With Formatting In TypeScript

In this section, you’re going to write text in TypeScript, and apply it to a TextGizmo that is running the script. You can download this example [here](https://drive.google.com/file/d/1xYVDDff6BSr2_iSX3PDGzo-dfsvUgOq1/view?usp=sharing) .

You’ve defined font and lineBreak string variables. This makes our lives a little easier, by making it so that you don’t have to remember or retype the angle brackets and this also makes our script easier to read. In addition, outside our class, you’ll notice the bold function allows us to easily apply bold to a string.

In start, you define a couple lines, add them all together using displayMe, and then apply the displayMe string to a TextGizmo.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468099956_595241716347117_3872321777488185735_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=VWivJA7sCC4Q7kNvwHO0Ml5&_nc_oc=AdmijewRU9fRkjSIXo-XFraBHH4Gt8Q3EBGbqctJuRiZnp1GZ0tFTk0W5Anx7VCs4V4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTXce67QhZN-G5a1fPrXc5Mt-6fEgQyR38ugP4jmumESw&oe=689BB3A8)

You will need to make copies of this script if you want to have different text on multiple TextGizmos. Note that the name of the script needs to be unique, but the class in the script can have the same name, in this case “EasyText.”

Below you can see creating a new script with a different name, I would advise naming this based on the text they display. Then in VS Code you can copy paste the first script to replace the default script in EasyText2, filling it out with your new text. Notice that when you assign the script, on the left is the script name, and on the right is the class name.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468132793_595241656347123_767351154685953432_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=jJZldP1QlnMQ7kNvwHL0W7I&_nc_oc=Adl2DoAImKdVCqPi9YVfEGiNHQSZOq7wgYwIWfJoWyG76kBi0OYpxLnzYGFvVV0V5Y4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfR7IQ-e5ov2yOMHgMfriUXVjSNyh3aQqBIxNYxc8OMj-w&oe=689BADB3)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467842237_595241659680456_1673158030815762410_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=ClYaCAguCncQ7kNvwFyxRmJ&_nc_oc=AdnyJ7-keiBDH4vov23IWr11vOeFgae2qnDWWWEamMtL_4V9EjF5Bb017xE-OLQC4fc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRQnD-tsue5H-2oEueXRS3_KW_ecbRx4Gw_AByiqScfBw&oe=689B94F4)

This example script has shown you how you can take the formatting options shown at the beginning, and apply them on your own. While this works wonderfully, as a part of this tutorial, I put together a formatting library, which you’ll see in the next step makes our lives even easier.

## Script 7: Write Text With a Formatting Library

This next script for you to [download](https://drive.google.com/file/d/122S7MyeFNDhkZ6oUG7nokfMQmswrgiPV/view?usp=sharing) is from the Formatting Library (written, a Utility script that you can use to make writing text with formatting a lot easier). If you have never used a library before, it is similar to an API, in that it provides you with additional functionality. To use, simply copy the UtilTextGizmo_Func.ts file from the above download link into your scripts folder. You can then use the provided “formatting,” “Formats,” “Fonts,” “Materials, and “Gradients.”

Below is a simple demo, which can be downloaded by clicking [here](https://drive.google.com/file/d/15g5RvlCh2opLGxWfy_KJTelAP1tcLxvj/view?usp=sharing) .

In this example, you imported “Formats” and “formatting” from the UtilTextGizmo_Func.ts file. For the “title”, you have a string that gets three formatting options applied. After typing “formatting” when you type “.” a list of formatting options appear. Including a second list of “specialFormats.” You’ll notice that “Formats.bold” allows the applyFormat function to apply the bold format on your title. “Formats,” similar to “formatting,” also has a drop-down list after typing period.

And then similar to Script 6, you add the title and lines together. In this case, you use formatting to get an easier way of typing in line breaks. And then finally you display the string on the TextGizmo that has this script attached.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467878752_595241663013789_1810103766417245983_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=JBQyVQH4C8MQ7kNvwEpFSdE&_nc_oc=AdnJWWzutljs0Nd1dn_XVM7_Yj0mEpEZ2KdqE9TLCfN67xIHUsXurpP8oORG5GHKV_E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQ7pW9enJTPG3b82GgbNRtJcXlWWILTjgq66Fw_QVZN0w&oe=689B9633)

Using this on multiple TextGizmos will require you to duplicate the script. give it a good name, and then attach the new script to the relevant TextGizmo. This isn’t the only method, as you could have one text manager that has the TextGizmos referenced on its properties panel. So depending on your needs, be creative and feel free to ask for help in Discord.

In addition to “Formats” there are three other enums, which have their own formatting.apply functions you can use:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468159987_595241773013778_2634878764640219240_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=DMiBDyZIVBsQ7kNvwGOFm2L&_nc_oc=AdntG1o0MpBWnDi53QtgPEf2C4Hs50EHCtV2rqRXZsJjeyww24mz_vRr3Yy-Hvokkms&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTT3F4xXGDTUkZzQx8ja6OYrkfwI1AUKn-sUW4TLO7Nug&oe=689BB711)

You can also use these on their own, if you don’t need to clear them at the end, ie:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468151290_595241666347122_8433285314453383764_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=1EagoMrjss4Q7kNvwHebpQw&_nc_oc=AdnRTLGqGSnM4DXhgJ6GU1q6uUs60HCLL4h27F4XmMwlvz3rCmyYIhONgTBlfnjB_5A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfRPScgay1b-KtN-55RwQzyxpwjY3pF_M0AseH5pFimynA&oe=689BC860)

Feel free to dig into the utility file on your own and learn more about how it works and what options are available.

## Script 8 & 9: Ad Lib Story Example

This next section may feel a bit intimidating because you’ll be using multiple scripts. The first script is where all the logic is stored. It is where you’ll spend most of your time. The second script is a data file, storing various strings in JSON objects. The last two scripts are utilities you have already used. They’re the formatting and arrayUtil libraries which allow you to easily apply formatting and work with arrays.

You can download the files here:

*   [EasyStoryTrigger_Entity.ts](https://drive.google.com/file/d/1IwalvBI24Yym2gCxPdjYB40bTGv_i1om/view?usp=sharing)

*   [Story_Data.ts](https://drive.google.com/file/d/12u_sTwv6i0Vla8QmfI_KZDou55sWaV0D/view?usp=sharing)

*   [UtilArray_Func.ts](https://drive.google.com/file/d/1Wlaru7gyQRTzjov5rACVMsr3lm3pG7PV/view?usp=drive_link)

*   [UtilTextGizmo_Func.ts](https://drive.google.com/file/d/122S7MyeFNDhkZ6oUG7nokfMQmswrgiPV/view?usp=drive_link)

Let’s start with `Story_Data.ts`, which is a relatively simple file that creates four string arrays, and then stores them in an exported JSON object called storyData. You can access all of these strings from your main script by importing storyData. You can imagine having as many of these string arrays as you need for your story.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467810576_595241776347111_3861804389282283223_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=uxLldKi1u0QQ7kNvwHGkgwL&_nc_oc=AdmmyJTOOJfownB1j8BarcZBoxKtpPH1ejc5qByZtZjGKabVyI0VXD4Z9A2rntmGe6c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQxIHdtRzU1wEz41aVkaZJh6fzcPgmqvPKke72hQwmRzg&oe=689B9665)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467812778_595241719680450_2622406763657355553_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=SqmQnqxBswQQ7kNvwFIwDgV&_nc_oc=AdlQCS5yYe2BGJowQ7unYWh099ijFtEgYhY1AXzb1BQxvb1rLCSru0fvmA83sI2HDtI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTOLm-fTIxr9dNL9scQZqGywc-3eEWnJx_VENlzLmijug&oe=689B98BD)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467994252_595241783013777_9048662164141849098_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=ed8gvflTCw8Q7kNvwHBPoEc&_nc_oc=AdmsH3AEZ_yobgae75BLM3RFkAVnkodEnezC-JDPG9hJsvdICz9508SWrNknDHtqZ3c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfSgHYpUDaFgMfYcIV-0LqMKrcYLbgXTfVK9sM96hjvZSA&oe=689B9C9F)

You can now see this all come together in the EasyStoryTrigger_Entity.ts script above. The first thing you’ve probably already noticed is that you attach this demo script to a Trigger Gizmo. This allows you to test our script by simply touching a trigger. This does mean you need to reference the TextGizmo, which you do on line 8 in the propsDefinition. You must make sure to fill this out on the properties panel of our trigger that is running this script.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468090494_595241779680444_8145136237204572786_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=l_utYkFfXqwQ7kNvwGUKwMp&_nc_oc=Adk3B_zf37Tcakw9EfH9SQ2MP8jro1oy6pSa2HZF_f5EKbUdLYyQXnkMEnt4NoQGOF4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfSSA2_Mk_s56Xk2YASmndlAVw2u-YEIbQ-aWhpea62ujQ&oe=689BB66B)

In preStart, you connect the OnPlayerEnterTrigger event to our local method. In start(), you load a default story using ‘adventurer’ to fill in as the name for a player. You can see the playerEnterTrigger method also calls updateStory.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467809488_595241723013783_5934371754843220484_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=r0qVBdLORjgQ7kNvwFKdiSV&_nc_oc=AdmjIeEJYslFjqrdU2bx5Zv3zICnh-BPk1Y7OAJrXrczbS8vdWzWCmUHAoT5kHCvlW4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfR0F5CoSRoKIaDworz5x6fe60tiTpfTD3AtmNutze4nJw&oe=689BC80D)

The updateStory method starts by getting a story and then displays the story. Each of these are separate methods shown below. One returns a string, and the other updates the TextGizmo.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467767440_595241676347121_5786752982037091076_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=KUqsIf3XNaEQ7kNvwE6Puax&_nc_oc=AdkWRuFNJhL-80krGXD820djp5aCMSwMZSMVeF4wzHkNH2_IDrq3r4LiVzzSLo2vl2U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfTNrIGHm41ikMoBisOjqSX0QQ6HzzXnTqTfX5CGvu652g&oe=689BBC67)

The getStory method is where all the magic occurs. It takes a name, ie. the player name, and returns a string, which is the story. The first thing you do in this method is set several variables by selecting a random string from storyData, and providing a fallback, in case our array of strings is empty.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468014262_595241786347110_8659952628007533587_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=E5rSqdG5GU0Q7kNvwFoG_Eq&_nc_oc=AdmBGro8rDahd6MVA8YFU_R9uMrYQsUGMC0TsAvGwLs1prr-cU2w5V6LIHuJXD8L-RA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQ_E4N9HyFchoEGtJyN31dX6y6buGoqENLC9aQznZxEWQ&oe=689B9992)

You then use formatting to capitalize the first letter in the greeting. There’s a second example on line 39, which sets the text to be the same as what’s on line 37. This is to show that you can choose the method of writing your story that makes the most sense to you. I personally prefer plusses “+” but the line 39 method takes up less space, and for some is easier to read.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467767655_595241746347114_4754993355373263784_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=lGTIrPLn0U4Q7kNvwGLd0gH&_nc_oc=Adm8vvjqWa7oM7LfqQjE7AOo2fjDwKIzNVxiNqheP2Vn5sYKzzwtY5s3kkG4Bija_2w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfT6nWWN0jABLFtgkfD9db3LSS23R3Tq5BlCXzJuTO9gjQ&oe=689BB663)

Now that you’ve calculated the story, you can now return it.

Display story is similar to what you’ve done earlier in this tutorial, except you added a check and console log if the text property has not been referenced or doesn’t reference a TextGizmo.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467826529_595241679680454_2219293768184138846_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=USioHU6Xk90Q7kNvwGcGpN1&_nc_oc=AdmzXJ0eQHxDD3P4JDrbET_umJg5M81GMBO75vZDGzqDwkgFXXnNtmDD3tLTiyWK5uo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQUU0Rx3LpIVPF_nuJJdU01rZgPkAtRhL-4w8NyN2I4fw&oe=689BBD36)

From this, you can extrapolate to create your own custom ad lib story. If you have questions or need help, don’t hesitate to ask in Discord.

## Script 10 & 11: Random Ad-Lib Story Example

In this section, you’ll elevate your ad lib story generation by randomly selecting a story and player. To do this, you’ll continue using the Story\_Data and utility scripts. You’ll add to it with an AdvancedStoryTrigger\_Entity script, and an additional import called storyFunc.

You can download the new files here:

*   [AdvancedStoryTrigger_Entity.ts](https://drive.google.com/file/d/1Mosj6KW_46cb35YyNTZDurvWIDH14rFw/view?usp=sharing)

*   [Story_Func.ts](https://drive.google.com/file/d/17696gjxbix-GYvL62mpGsrx7TaTRHFKA/view?usp=sharing)

Let’s start with something familiar, looking at Story_Func. This is similar to our data file in that you have an exported variable, but instead of storing string data, it stores an array of functions. The creation of storyFunc declares itself to be an Array of functions that take a string parameter and return a string. This is just like our getStory method from script 8. In fact, line 10 is the same method, but as a function called story1. You can then duplicate this for as many stories as you want. Just make sure they are included in the array on line 5.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467995338_595241669680455_5348008257830303167_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=wtyy7p0XddwQ7kNvwEHzEME&_nc_oc=AdngUhWr4fiJn1PLPoILjT7V4Nbn0aSMeJKPIuI42Lx-nNLbnvbKMckRoGidK6DDT6s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfT9BieQceuo7jtarK_UndKyTPqzjCQQDOFptxYftDnB2A&oe=689B9987)

Next, you can take a look and see how this is used in the trigger script. The first difference you’ll notice is that you have an array of activePlayers, and in preStart you connect PlayerEnter and PlayerExit world events. Seen below on lines 23 and 27, you add players to the activePlayers array using push, and remove them using the arrayUtils removeItemFromArray function.

The next major difference is that in the playerEnterTrigger, you now select a randomPlayer and update the story using that player’s name.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467993359_595241749680447_7898377454591025856_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=yxHCCAG08NUQ7kNvwGEA7Rd&_nc_oc=Adn-rEAIWA259FLUOFfPsi7qGaja1Y6F54XN9XJjB5n93RJYKt9uCWml6L-M6Y1dvT8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQw8HW_aYac9NWGV3jLKZVH9sMbjhRUPru3PFkvL8oqaw&oe=689BC96B)

The next change is inside of getStory. You’ll get a randomStoryFunc from the array of storyFunc. If it is defined, then you’ll use it to generate a story. Otherwise, the list of functions may be empty, and you’ll log an error to the console, returning an empty string.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/467952894_595241683013787_5146014287776986293_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZHqW0tvCMUcQ7kNvwGgr3_j&_nc_oc=Adngglp2uPnJcg15lQd4s3dxMg30qTyBkhau3b2WIRl0VmqjDdsMnfLG2iUU46uqnXw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=8GfSOSN2n2llrql2C6cAng&oh=00_AfQlVLXrsiZzGxCg9LgaoRPq-72OTw0gKVqJBmXtR9Ekxg&oe=689BA287)

And like that, you can have as many random ad-lib stories as you want.

## Extended Learning

Below are challenges that you can implement on your own. The Advanced task might require some outside knowledge. We encourage you to ask questions in Discord if you get stuck or are unsure how to complete any of these. **Novice** Fix spelling mistakes and add formatting to pre-existing large blocks of text in TextGizmos. **Intermediate** Write your next large text paragraph using TypeScript and the provided Vidyuu formatting library. **Advanced** Integrate a randomly generated story into one of your worlds.

## Further Assistance

For any questions or further assistance, creators are encouraged to join the discussion on the Discord server or to schedule a mentor session for personalized guidance.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)