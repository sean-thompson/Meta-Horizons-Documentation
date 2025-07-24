# Debug console gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/debug-console-gizmo)

When you create your world, there are helpful development tools for [debugging and optimization](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/developer-tools-for-tutorials) . One such tool is the debug console [gizmo](/horizon-worlds/learn/documentation/code-blocks-and-gizmos/about-gizmos) , which allows you to debug scripts in real time while you’re in the virtual environment with the headset on. This is often referred to as in-world debugging. It is designed to display script messages with an in-world interface for viewing debug information, making it more suitable for interactive and real-time debugging scenarios. You can see logs and debug information as you interact with the world. In comparison, the standard console displays similar information in the log viewer in the [desktop editor](/horizon-worlds/learn/documentation/desktop-editor/desktop-editor) under the tab **Console**.

The following image shows the [debug console](/horizon-worlds/learn/documentation/typescript/getting-started/the-debug-console) gizmo while you have the headset on, providing an immersive debugging experience. As shown, the **Start world**, 

**Stop world**, and **Rest world** buttons control the executing states of the scripts.

![Debug console gizmo showing debug messages in-world console](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/493597714_723416580196296_8022545866060318316_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=vt9df2pG3xAQ7kNvwE0g305&_nc_oc=Adn93q5n5ABNooXGeKQhqO9sgErOD47_7WHfhc6D6ZOPqzz6R6smVAAQfwSZ9CnGt64&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e8itpNEn0DHtoljHFBQlHQ&oh=00_AfSu1B9a2138eOjeChH3STCJgxDKY0St5NO79rjLiqnKqA&oe=689BAF1C)

The following image shows the debug console gizmo while you are using the desktop editor without the headset. The log messages are also displayed under the desktop editor **Console** tab.

![Debug console gizmo showing debug messages in the desktop editor console](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/499399178_723580280179926_4040817637596418026_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=rcTyqUorGswQ7kNvwEFgRS6&_nc_oc=AdlER-RqPejMO3S7NthdoaK9gijUcNc8UZRn8D0-2MjNMcQivuQ5lmGxsjO_vXc1oK4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e8itpNEn0DHtoljHFBQlHQ&oh=00_AfS77hLFVGLy8CwjnbzfNghVjY2webQSY72gk8uOyb8_ng&oe=689BBD50)

The following sections show you how to access and configure the gizmos so you can start debugging in VR.

## Access the debug console gizmo

While you can access and configure the gizmos in the [VR tool](/horizon-worlds/learn/documentation/vr-creation/getting-started/create-a-new-world-in-horizon) , the following steps show you how to access the debug console gizmo from the desktop editor and add it to the [scene pane](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/UI-panels-and-tabs#scene-pane) .

*   In the desktop editor while in the Build mode, select **Build** \> **Gizmos** from the menu bar, search for “debug console” in the search field.

*   Select the debug console gizmo and drag it into the scene. You can now edit the new gizmo properties in the Properties panel.

## Properties

All objects in a world are represented by [entities](/horizon-worlds/reference/2.0.0/core_entity) . Entities have their respective properties such as position, rotation, and scale. In the **Properties** panel, edit the debug console gizmo’s transformation fields to configure its **Position**, 

**Rotation**, and **Scale**.

The visibility of the debug console is configured under [**Visibility**](/horizon-worlds/learn/documentation/typescript/getting-started/the-debug-console#controlling-visibility-of-the-debug-console) . The options are **Edit Mode Only**, [**Edit and Preview Mode**](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) , or [**In Published World**](/horizon-worlds/learn/documentation/get-started/create-your-first-world#section-4-play-in-your-world-on-mobile) . Be aware that the gizmo is only visible in the Build mode when **Visibility** is in the default **Edit Mode Only**.

![Debug console gizmo's visibility options](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/498317217_723416583529629_2536898422592253740_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=I7wyr1t3UhgQ7kNvwGr5Egb&_nc_oc=AdkmZpN9a21iQXtcmBdTQyhU8McNJ5OIW7osev83eD7C21Blw4GeMgmMq-WUUsMLsao&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=e8itpNEn0DHtoljHFBQlHQ&oh=00_AfQ9GjYRkkHoNYOFsET00sC1yqrrnzEAjtnXXYSizcssKw&oe=689B9BB6) **Note**: The Edit Mode that the Properties panel refers to is also known as the [Build mode](/horizon-worlds/learn/documentation/desktop-editor/getting-started/user-interface/operational-modes) . See also the [Build mode](/horizon-worlds/learn/documentation/vr-creation/getting-started/using-controllers-in-build-mode) in VR.

## What’s next?

Now you’ve been introduced to the debug console gizmo, further your learning with tutorial worlds with completed samples, and developer guides:

*   [Meta Horizon Creator Program creators manual on the debug console gizmo](https://github.com/MHCPCreators/horizonCreatorManual/blob/main/HorizonTechnicalDoc.md#debug-console-gizmo)

*   [Developer tools for tutorials](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/developer-tools-for-tutorials)

*   [The debug console](/horizon-worlds/learn/documentation/typescript/getting-started/the-debug-console)

*   [Roof top racer tutorial worlds on testing tools](/horizon-worlds/learn/documentation/tutorial-worlds/horizon-traversal-sample-world/module-2-overall-game-manager-systems#testing-tools)

*   [TypeScript Tutorial](/horizon-worlds/learn/documentation/typescript/getting-started/typescript-tutorial)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 