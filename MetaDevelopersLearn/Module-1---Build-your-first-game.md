# Module 1 - Build your first game

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/build-your-first-game/module-1-build-your-first-game)

![Thumbnail for the tutorial world](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/499149844_720698043801483_8564527204365994086_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=rJk0h53wlhwQ7kNvwE1r91u&_nc_oc=Adn3RPiiO-wqwdqEv4FlLMmwtAOK6a7Gzv7NAbyZ1Fa0RD1Hsrpbvajug8fOWuadvUc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfRfxGJ97cma5zxhdoAQFsfuP2zbK69eaB4PHUUsBRILww&oe=689BB40D)

Important

This content is intended as a companion to the tutorial world of the same name, which you can access through the desktop editor. When you open the tutorial world, a copy is created for you to explore, and this page is opened so that you can follow along. For more information, see [Access Tutorial Worlds](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) .

In this tutorial, you create a simple platformer-style game where players run and jump through a world as they collect gems.

## Key game development areas

This tutorial covers a reusable and flexible co-op game setup, in which all players work together to collect gems. This tutorial walks through the basics of using the Meta Horizon Worlds desktop editor application to build the world and the TypeScript required to power a game that works in VR and on 2D desktop screens.

Game development areas include:

*   Keeping track of all players in the world.

*   Managing game state.

*   Player and object collision.

*   Dependency injection and direct reference in scripts.

*   Events.

*   Implementing the [Observer Pattern](https://gameprogrammingpatterns.com/observer.html) using the Meta Horizon Worlds event system.

*   Displaying dynamic text.

## Key learning objectives

*   Basics of using the desktop editor.

*   Basics of building scripts in TypeScript.

*   Build a basic Game Manager.
    
    *   Game states.
    
    *   Initialize the game.
    
    *   Keeping the score.
    
    *   End the game and resetting the game.

*   Events.
    
    *   Event listeners.
    
    *   Broadcast events.
    
    *   Entity (local) events.

*   Entity collisions.

## Before you begin

Review the [Getting Started with Tutorials](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/tutorial-prerequisites) ., which includes information on:

*   Tutorial prerequisites and assumptions.

*   How to acquire a copy of this world for yourself.

*   How to use tutorial worlds and assets in your own worlds.

*   Developer tools and testing for your worlds.

## Learning pathways

### Follow along

You can follow along with the steps of the tutorial content by using a copy of the world. After you have copied the world, you can compare the steps of the tutorial to the completed world. **Desktop editor**: To create a copy of this tutorial on a tutorial world from the desktop editor, click **Tutorials** in Creation Home and then select **Build Your First Game**. For more information, see [Access Tutorial Worlds](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) . **VR headset**: To build the world described in this tutorial, make your own copy of the **Build Your First Game** tutorial world, by selecting it from the **Tutorials** tab in the **Create** menu.

![Screenshot of selecting tutorial world in VR headset](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481099414_660734626464492_2046346290266795617_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=eREDZ0i2s3gQ7kNvwG4V-Np&_nc_oc=AdnIFtaSmACIDl8JZnCs8U2IHytDeklM8K-zVXhSL7DwAekX5oJxQtuIy3ri5rtq1Tc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfSj3gwq7fIG-RhwviPvbRIrL0WxJ9k7pGqYvcGHeVSZYQ&oe=689B9813)

### Explore the complete world

You can explore the completed world and review the script and systems that are covered in the tutorial. The finished TypeScript files from this tutorial are included in the project with a file name that end with: `_COMPLETE`.

### Use in your world

Grab any asset from this world and use it in your own project. For more information on how to apply assets or scripts from this world to yours, see [Use Assets from Tutorials](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/use-assets-from-tutorials) .

## Get started

To begin, open your copy of the tutorial world in the desktop editor.

*   Open the **Meta Quest Link** application on your desktop.

*   In the Library tab, locate the **Meta Horizon** application in which to build your version of the world.

*   From the context menu for the application, select **Start in Desktop Mode**.

*   In the **Creation Home** page, click **My worlds** in the left navigation bar.

*   Select your copy of the tutorial template.

*   Your world opens in the desktop editor, and it should look something like the following:

![Screenshot of this world opened in the desktop editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/488833913_692135416657746_8373702403232926749_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=hjKvy7BR1EYQ7kNvwEjM2uJ&_nc_oc=Adm6iCl3f40mbA2WSzFHwed5ZYdi9TpH_-p6DzPujTfudE-w9Q4kb6Rn6XKQvD8eTVs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfTyEvFTZlROmQhiBM74z3IX2KDqdyyvQrZQNMXftNAWNA&oe=689BACEC)

### Build mode and Preview mode

When you first open the world in the desktop editor, the world is in **Build mode**, which is indicated by the Play button in the toolbar:

![Screenshot of the toolbar in the desktop editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489840370_692135289991092_4407548639818964132_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=65ELVkzz8-0Q7kNvwFlFl4k&_nc_oc=Adm9vhGHkn4NUtfaxEMWHdUTcQxy25OwmAJFI931iQ_CeBA4iHBoWG9HrrDS8Xypdk0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfQowmCKUSp42u_tj3ppOl1I1Cq8mhysas8VzDf7MWZ_TA&oe=689BA09E)

In Build mode, you can add, edit, and remove the entities that compose your world. **Preview mode**:

To explore the world and playtest it, click the **Play button**, which opens Preview mode. When you are testing your TypeScript, you must press the **Play button** to start the simulation, which activates and executes your TypeScript scripts. Press the **Stop button** to stop the simulation.

By default, when you press the Play button, you enter Preview mode and start the **world simulation**, which means that all valid scripts in the world are executed. So, you can choose to launch Preview mode as if you were entering it like a player or, if needed, to disable the world simulation so that you can explore it without any scripted activity.

In the toolbar, next to the mode controls, you can see the simulation playback controls. The **Reset button** restarts the simulation as if the world was launched from the beginning. **Note**: Exploring the world in Preview mode is not the same as playing the game experience. It is used for debugging during development, but it is reccomended to test your worlds on all applicable target devices prior to publishing. **Preview controls**:

| Control | Description | Notes |
| --- | --- | --- |
| WASD and mouse | Movement | In Preview mode, you move at a single speed. |
| SPACEBAR | Jump | It’s a good idea to test any required jumping distances in Preview mode. |
| ESC | Leave | Press ESC once to pause Preview mode, which enables you to interact with the desktop editor UI.Press ESC to exit Preview mode completely. | **Note**: You can explore the world in VR mode from the desktop and through the VR headset.

## Game layout

In the desktop editor, you can see that a course for your game is provided. You can change the course to any type of design layout.

![Screenshot of the layout of entities in the world in desktop editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/488846669_692135296657758_2132818553644304944_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=UZjm-yZhqgUQ7kNvwEH2bsW&_nc_oc=AdnamOpaDvJVGJ8KMOWm_waTYBgiutDTqDGT1v8P9fNdWf8BhLpTNh0TI6VrMb6csNY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfRHWWbyp4x16_XoUgUqCVQ0o1vyobwDy3O-fHkssXqYKQ&oe=689B8BAA)

#### Some tips if you change the course

*   Get in the habit of building your maps offset from the origin `(0,0,0)`, which makes snapping easier in the editor.

*   You can drag and drop entities in the Hierarchy panel to reorganize them. Reparenting entities groups them together and retains their positioning relative to their parent entity.

*   Use Preview mode to move around the world to test the user experience. You can customize the world further by creating additional areas for the player to jump or explore.

## Add gems to the course

You should see a single green gem on the course. Create four duplicates of the green gem asset provided in the template.

![Context menu for duplicating gem](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/488938157_692135316657756_2950821048434087044_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=W05wFGZ12-QQ7kNvwE_95u0&_nc_oc=AdnZba30vZ5wgzXVGEywJ4-N-dxMpBmKJgJuIamQQ8rrsPrndi9fv3XXsHLrDxtvDcs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfTgoxDfULFnumtFL3gfS9e0z_PVLQi5gNR8p7tKPJDMQw&oe=689B9A3D)

*   In the Hierarchy panel, search for: `emerald`.

*   Right-click on the emerald entity in the hierarchy:
    
      
    
    a. If the emerald is not in main viewport, select **Focus on selection**.
    
      
    
    b. Select **Duplicate**.
    
      
    

*   The new instance appears at the bottom of the list in the Hierarchy. Select it.

*   Repeat the above steps until you have 5 total gems.

When duplicating additional gems, they will all have the exact same position and rotation as the source gem. You can move the additional gems around the course, by selecting each gem in the Hierarchy panel, and use the **Move** tool to reposition them.

Gems should be placed about chest high on an avatar, so that players can easily run into them. You can also edit the Position properties in the right-hand panel for more precise positioning.

![Screenshot of highlighted gem with movement controls selected](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489903423_692135313324423_5593591894087547257_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=05yQF79HOJIQ7kNvwFnkJg1&_nc_oc=AdlLzkBWmgdZugHEoXUAUYtt0_fXaywr5hffKkaU9l9UvymvEB3qKsurXSa8IflZXlw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfSSy0ozP7Em_ZsepWDJHWVollhkiqklWWzBCAu5XAwtug&oe=689BB5AC)

Example course:

![Screenshot of layout of gems in the world](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480788051_660734619797826_2150466854236932494_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=I0gHOl-Y5tgQ7kNvwELf0rP&_nc_oc=Adm5eYi6vgdh6EWGDLLdoN-pPdGiwffVGiWyOTryO8N-y_Lt9uLhzqkuJ80WoKLIoS8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkS-jcSj_GTwpvnHdC8B2A&oh=00_AfRL1REyAjPpBvW4xLEPsIUgbwJHnmoXlwSrcENLyUCXzQ&oe=689BA86C)

Use Preview mode to test your course.

## Checkpoint

You have completed Module 1. In this module, you:

*   Verified prerequisites.

*   Opened the tutorial world in the desktop editor.

*   Built your layout.

*   Added gems.

*   Tested your world.
    
    *   Switched between Build mode and Preview mode.

In the next module, you can start building scripts in TypeScript.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 