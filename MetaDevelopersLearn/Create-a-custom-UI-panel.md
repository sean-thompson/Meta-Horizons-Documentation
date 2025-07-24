# Create a custom UI panel

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/creating-a-custom-ui-panel)

This topic shows you how to create a custom UI panel. To create one, you need a Custom UI gizmo and a [`UIComponent`

 script](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/api-reference-for-custom-ui#uicomponent) .

## Before you begin

Before you begin building custom UIs in the desktop editor, enable auto-start and auto-stop of the simulation when previewing.

![Preview Configuration panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481946976_667154419155846_1581585323779466962_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=os9S5FbQl14Q7kNvwE9XV_7&_nc_oc=Adn3wkinW768sSfxP8wUKVud0g1o6gug0S4d2ROnxQzH3-aWtQ3i7MKuuOHR_BBKrbg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Hbe8teVrgkRKBR2f4S4bIg&oh=00_AfTCcsBOZuLMv1c38iApwNIUwS8tvvYTlFkUsuZJLTCuOQ&oe=689B9864)

Unlike other physical entities in the world, a custom UI is entirely generated from TypeScript code. If auto-start is disabled when you begin the preview, then no code is executed when you enter the preview. Your custom UIs are not initialized, and are therefore invisible.

## Step 1: Create a Custom UI gizmo

On the menu bar, find the **Custom UI** gizmo in the **Build** dropdown menu > **Gizmos** and drag it into the **Scene** pane. Like other entities, you can control the position, scale, rotation, and visibility of the Custom UI gizmos, both from the **Properties** panel and from scripts.

The **Gizmos** panel is where you’d find the **Custom UI** gizmo.

![Select the Custom UI gizmo](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480602105_661373913067230_2289491615613106605_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=7RzrdAP_0E0Q7kNvwEOdsYX&_nc_oc=AdlZtFSdOfPMMPG0DhTy3887MlzKQgUrd63pCnta3w82Q-ClzV6Lf9sYwZJSPhwiJyU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Hbe8teVrgkRKBR2f4S4bIg&oh=00_AfSkQCZt_Hgjdz6HIoDQBb3c4g_urRvT9bJcGDUf5wwJsw&oe=689B8CB1)

On the far right of the desktop editor, you’d find the Custom UI’s **Properties** panel.

A custom UI panel is represented by a Custom UI gizmo, which controls where and how the panel is placed in the world. You can place multiple Custom UI gizmos in the world.

In the past, creators often placed duplicate Custom UI gizmos in the world and controlled the visibility for each to create custom UI panels that displayed different content for each player. In most cases, you do not need to duplicate Custom UI gizmos. The Custom UI feature allows you to display different content to different players within the same Custom UI gizmo. See [Player-specific custom UI](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/playerspecific-custom-ui/) for details.

## Step 2: Create a UI script

The Custom UI gizmo does nothing unless you attach a script to it. The script controls the content of the panel. Next, [create a TypeScript script using the desktop editor](/horizon-worlds/learn/documentation/typescript/getting-started/adding-an-ide-to-desktop-editor/#create-a-new-meta-horizon-worlds-script-in-the-desktop-editor) . To use the Custom UI functionalities, include `horizon/ui` module for TypeScript API v2.0.0 from the **Scripts** dropdown menu > **Settings** (the gear button on the top right of Scripts menu). The examples here are for TypeScript API v2.0.0.

![Create a UI script](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480522573_661373903067231_3023285926290038565_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=UVbTaUO33tkQ7kNvwHgI4j3&_nc_oc=AdlHAay8quRvxGYzKjp3eL0u88E_liJS3GoPw9PzeCQtPRn4HrBCixvL0DRlxdUCx3g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Hbe8teVrgkRKBR2f4S4bIg&oh=00_AfR2I_YqQbB3wdytPcMWdvITF3JFsyqNZQxNlKDJPKP5gg&oe=689B8EDA)

## Step 3: Create a Hello World template

Write the following code in your script. Notice that the component extends the `UIComponent` class, instead of a regular `Component`. [UIComponent Class](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/uicomponent-class) describes what each line means in more detail, but this template is a good starting point for now.

```
import 'horizon/core';
import {UIComponent, View, Text} from 'horizon/ui';

class HelloWorld extends UIComponent {
  initializeUI() {
    return View({
      children: Text({text: 'Hello World', style: {color: 'black'}}),
      style: {backgroundColor: 'white'},
    });
  }
}

UIComponent.register(HelloWorld);
```

## Step 4: Attach the script to the gizmo

Like all script components, the same `UIComponent` can be attached to more than one Custom UI gizmo. Those Custom UI gizmos will then display the same content.

To achieve [player-specific custom UIs](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/playerspecific-custom-ui/) and heads-up display (HUDs), you do not need to duplicate Custom UI gizmos or scripts in most cases. The framework provides tools for you to build custom UI panels that display different content for different players.

You can find the registered `HelloWorld` component in the **Script** section of the **Properties** panel.

![Attach the HelloWorld script to the Custom UI entity close up](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480666001_661373906400564_4241762125279907481_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=z3kDp7wkzUcQ7kNvwGlu4Dr&_nc_oc=AdkwbK4dwPyfKuRf4Vmlf7nyl5_y8FCdjzM48f4D4EYEwJ5x668vNUzKIUOwBJs8IcA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Hbe8teVrgkRKBR2f4S4bIg&oh=00_AfQAfKasYh-lT_9ClKi0l1V1JDwdRwgCYhpPBhkE6CEzCg&oe=689BAB25)

After you attach the `HelloWorld` script to the **Custom UI** entity, click Play to enter the preview mode. If you haven’t already, ensure you have turned on **Auto-start simulation on Preview entry** and **Auto-stop simulation on Preview exit** in [**Preview Configuration**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/preview-mode#preview-configuration) to successfully complete this tutorial.

While in preview, you will be prompted to press the “E” key when your avatar is within a certain distance from the UI panel. Press “E” to see the “Hello World” panel. **Note**: You can choose the display mode based on your preference in the **Properties** panel > **Visual & Interaction** \> **Display mode**. The following image shows the “Hello World” panel in the **Spatial** display mode. Additionally, you can [resize the panel](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/uicomponent-class#properties-panelheight-and-panelwidth) and place it wherever you like.

![Hello World custom UI panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481075889_661373909733897_3770997712728765389_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=VjkabP2kmlkQ7kNvwF1EEOm&_nc_oc=Adkx64QuAI1wnHL9Lnx0yBqv7iK5ImLR_yLXlubh0IibtDiyMVbozefM0PEmbp30278&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Hbe8teVrgkRKBR2f4S4bIg&oh=00_AfRgRchqhhw-oLTlyqcshtSWPkWZ9Exmzmo9B3_3ZmZNYQ&oe=689B8927)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 