# Asset pool gizmo

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/asset-pool-gizmo)

The asset pool gizmo is a powerful tool for managing objects that should be granted to each player in your World. It automates spawning and assignment of asset template objects to players as they join your World. This is necessary for objects that should have different states per player.

This gizmo is perfect for creating the following in game objects or features on a per player basis:

*   HUD and UI

*   Starting items

*   Particle Effects

*   Stats

When using something like a HUD asset, the asset pool gizmo to assign a HUD to each player in your world without needing to create a new HUD per player. Implementing the asset pool gizmo allows you to focus on designing gameplay experiences without writing custom code to manage player-specific objects.

## Asset pool gizmo overview

![Asset pool gizmo overview](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489995807_695402086331079_7384783171554118115_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=tAXv7q_axEgQ7kNvwGirv9l&_nc_oc=AdnJqIOB4lkhJWvsxXYg0P6SP2djvhYrFTxeZPoxZgLWKjFKZNEL4_Jaq6PZFbk--cE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfT7CARwYGH9_hkskho7j3xSoq1H4ZzGM7E21KDKXD5W2A&oe=689B9BA3)

*   Each asset pool gizmo manages a single asset template and pools it to be copied as child objects for players.

*   You can add additional asset pool gizmos to use additional asset templates for as necessary.

*   The asset pool gizmo is able to be used within asset templates.

*   When an asset template is assigned to the gizmo, it will automatically create the pool of prefabs based on the maximum player count setting.

![Asset pool gizmo overview 2](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490684843_695402099664411_1002739092788578019_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=wXjs4Nvay-MQ7kNvwEJEbXg&_nc_oc=AdkVIPjbFTqdFS8uh-3QhhgTxyz_G-S35tMY0z_TjNChhQaBMOf1KfxwHJxq7C1Rl18&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfQdu6wdH6f2F4b-q47vEWlBs0_s-u2J1LD9xL1WxhNW1w&oe=689BC13E) **Note**: When deploying the asset pool gizmo in a [non-FBS world](/horizon-worlds/learn/documentation/vr-creation/scripting/use-file-backed-scripts) , avoid connecting asset templates that contain scripts. When the asset pool gizmo spawns the asset template, the scripts will be spawned as separate instances that must be maintained.

## Use the asset pool gizmo

To get started using the asset pool gizmo you will first need to have an asset template available that you plan to use on a player-specific basis. This can be an asset template you created or one that was shared with you by another creator.

Access the asset pool gizmo via **Build Menu** \> **Gizmos** \> **Asset Pool**.

![Asset pool gizmo build menu selection](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490468445_695402096331078_966460998750896256_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=i2NhA1IKBOwQ7kNvwHP6Udr&_nc_oc=AdmixAFLjhXAy7MLfJCtERZCg1BZ3JzSDbE_vZNL3i3YFL14tqZ8LhvRrCImU9mJcIo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfSth4WBTyXkcYfcvuOO6bONE4NdO9mw6ZuE3oK-aeFWLA&oe=689B8E94)

Once the asset pool gizmo is added, you can set whether to **Auto Assign to Players** and set the **Asset Reference** for the gizmo.

![Asset pool gizmo properties window](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490472555_695402092997745_8711514918910792195_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=SDljUGe38lAQ7kNvwFmrYmR&_nc_oc=Adn9x-BrGSISGK-ObSGC1QzTjTsGBgd1kkEIWdCcFvkIPj7Z3FNSJ-pPDhLsd_Vyvpw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfR6V3IGaD6RAyu3HkX_4mCjNiP6Q-iXpzLgb5wYX7rSzw&oe=689B9E75)

Once the asset pool gizmo is added to your world, use the following process to manage it:

*   Navigate to **Player Settings** in the top left menu and adjust the **Maximum Player Count** slider for your world’s expected max player count.
    
    ![Player settings maximum player count slider](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490846189_695402082997746_3845879378303484171_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=LjPQ69k-2pkQ7kNvwESzfdv&_nc_oc=AdkXemDyJhYcjlT3-7IESMK82P3FdWdMfzcqcDxv61bk4ZfZswR94lis-uJPpEVnkTM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfSSZgxKic1aEQxDAt7m3b0FDXlnLTM3Y9amjN-_kpeysg&oe=689B9821)
    

*   Drag the **Asset Pool** gizmo into your scene.
    

*   Locate the **Asset Template** you plan to use in your **Asset Library**.
    

*   Drag and drop the **Asset Template** into the **Asset Reference** field of the **Asset Pool** gizmo.
    
    ![Add asset template to Asset pool gizmo](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490019384_695402089664412_6707460485052179724_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=rvHsHMdzRgQQ7kNvwErNggR&_nc_oc=AdnS4UQIiLjhpIk6HDo0zBoiQ9ushy1ffJmZy3Rh112qF32eTvZ7XlCQyzdvGLXlZyQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfTLRItTLpuyEtnl-QqeevJShVkqzB198RdnMPh9ix9E4w&oe=689BA183)
    

*   Use the drop down menu in the **Asset Reference** field of the **Asset Pool** gizmo’s properties window to search for your asset.
    

*   The **Asset Pool** gizmo will automatically create child prefabs equal to the **Maximum Player Count** setting.
    

*   If auto-assign is enabled in the properties window, players entering the world will receive a prefab from the asset pool.
    

## Example scripts and assets

Example #1: `UpdateOwnerName.ts` This script can be attached to a mesh object with a child Text gizmo. When an owner is assigned to the object, the text gizmo will update with that player’s name.

![Asset pool gizmo assigns an object to a player and displays the player name](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/501528384_729175769620377_8693007284531093059_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=NgGnVwC0aZ4Q7kNvwHHPQJb&_nc_oc=AdmUudhA18nyUsJcr9Fz2ju8i8mrpeD0TuB4GDX1Rgyrh0a-65hFxx-7GmwYPHag7SQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfQ0gr6ufQw9v6HKFwBngXXOs38KC9OUK1diG2jZ2z2VWQ&oe=689BC5D2)

```
// Import the necessary components from the 'horizon/core' module.
import * as hz from 'horizon/core';

// This class will control the behavior of updating the owner's name.
class UpdateOwnerName extends hz.Component<typeof UpdateOwnerName> {

  // Defines the properties, `ownerNameTextEntity` will be set to an Entity.
  static propsDefinition = {
    ownerNameTextEntity: {type: hz.PropTypes.Entity}
  };

  start() {

    // Retrieve the owner of the current entity (the entity this component is attached to).
    let owner = this.entity.owner.get();

    // Get a `TextGizmo` which displays text, associate it with the `ownerNameTextEntity` property.
    let ownerGizmo = this.props.ownerNameTextEntity?.as(hz.TextGizmo);

    // Clear the text in the `TextGizmo`
    ownerGizmo?.text.set("");

    // Check if the current owner is set to a current player or the server.
    if (owner === this.world.getServerPlayer()) {
      // If the owner is the server, clear the text, this occurs if no player owns the object or an owning player drops the object and leaves the session.
      ownerGizmo?.text.set("");
    }
    else {
      // If the owner is not the server, set the text to the owner's name.
      ownerGizmo!.text.set(owner.name.get());
    }

  }
}

// Register the `UpdateOwnerName` component with the Horizon engine.
hz.Component.register(UpdateOwnerName);
```

Example #2: `UI_ShopHud.ts` This script can be attached to a custom UI gizmo, and when pooled will display a HUD element with a clickable button and the owning player’s name. This also sends some logs to Console when ownership is assigned.

![Asset pool gizmo asset assigns the player a custom UI HUD element](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502554127_729175772953710_1326171222938316875_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=FUqLl5CydewQ7kNvwFN70Da&_nc_oc=Adn0P8M7FUcWLdJaT4FxsDwgcUX1v4kaOfzljcsRyyFCVvTvbyEP7q9ktfcw4PDE3uo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=a8uFbqpArlB8mABqQnTwHA&oh=00_AfTSu3HcMAMNbnFf3_JdrA0nYuQj1nOCbRDIGFZZE19nug&oe=689B9E52)

```
// Import necessary components from the Horizon core and UI libraries
import { CodeBlockEvents, Component, Player, World } from 'horizon/core';
import { Binding, Pressable, Text, UIComponent, UINode, View, ViewStyle } from 'horizon/ui';

// Define the class `UI_ShopHud`, which extends `UIComponent` for custom UI in Horizon Worlds
class UI_ShopHud extends UIComponent<typeof UI_ShopHud> {

  // Define props definition
  static propsDefinition = {};

  // Define bindings for UI elements (to make them reactive)
  private titleText!: Binding<string>;  // Title text binding (e.g., shop name)
  private shopText!: Binding<string>;   // Text for the shop label
  private shopTextColor!: Binding<string>; // Binding for the shop text color
  private buttonColor!: Binding<string>; // Binding for the button color

  // Configurations for UI layout and styles
  private readonly featuredTextSize = 36; // Fixed size for featured text
  private debounce: boolean = false; // Flag to prevent multiple button clicks in a short period

  // The `start` method is called when the component is initialized
  start() {
    // Retrieve the server player and local player
    let serverPlayer = World.prototype.getServerPlayer();
    let owner = this.world.getLocalPlayer();

    // Check if the current player is neither the server player nor null
    let currentPlayer = owner === null || owner === serverPlayer ? null : owner;

    // If there is a valid current player, make the shop UI visible
    if (currentPlayer !== null) {
      console.log(`UI_ShopHud CONNECTED to ${currentPlayer.name.get()}`);
      this.entity.visible.set(true);  // Set the UI entity to visible
    }
    else {
      // Otherwise, hide the shop UI
      this.entity.visible.set(false);
    }
  }

  // Method to handle when a slot (button) is clicked
  private onSlotClicked() {
    // Prevent multiple clicks within a short time frame using debounce
    if (!this.debounce) {
      this.debounce = true;  // Set debounce flag to true (no further clicks allowed)

      // Change the button color to grey when pressed
      this.buttonColor.set('grey', [this.world.getLocalPlayer()]);

      console.log("Shop Button Pressed");

      // After a short delay, reset the debounce flag and set the button color back to green
      this.async.setTimeout(() => {
        this.debounce = false;  // Reset debounce flag
        this.buttonColor.set('green', [this.world.getLocalPlayer()]);  // Reset button color
      }, 200); // 200 milliseconds delay
    }
  }

  ////////////////////////////////////////////////////////////////////////
  // UI Formatting Section: This part handles the layout and design of the UI
  ////////////////////////////////////////////////////////////////////////

  // Method to initialize and layout the UI components
  initializeUI() {
    // Skip UI creation if the local player is the server player (since they should not see the UI)
    if (this.world.getLocalPlayer() === this.world.getServerPlayer()) {
      return new UINode();  // Return an empty node if server player
    }

    // Set up bindings for dynamic UI content (e.g., player name, shop name)
    this.titleText = new Binding<string>(this.world.getLocalPlayer().name.get());
    this.shopText = new Binding<string>('Shop');  // Static text for "Shop"
    this.shopTextColor = new Binding<string>('white'); // Default text color for shop text
    this.buttonColor = new Binding<string>('green'); // Default color for the button

    // Define the style for the root panel (container) of the UI
    const rootPanelStyle: ViewStyle = {
      width: "60%",  // Width of the root panel (60% of the screen width)
      height: "80%", // Height of the root panel (80% of the screen height)
      left: "35%",   // Position the panel 35% from the left edge of the screen
      position: "absolute", // Use absolute positioning
      justifyContent: "center", // Vertically center the content inside the panel
      alignContent: "center",
      alignSelf: "center",
      alignItems: "flex-end", // Align content to the bottom (flex-end) horizontally
    };

    // Define the style for the button
    const buttonStyle: ViewStyle = {
      backgroundColor: this.buttonColor,  // Dynamic button color
      borderRadius: 8,  // Rounded corners for the button
      height: 48,       // Button height
      padding: '5%',    // Padding inside the button
      margin: '5%',     // Margin around the button
      width: '80%',     // Button takes up 80% of the panel's width
      justifyContent: 'center',  // Center the button text vertically
      alignContent: "center",
      alignItems: 'center',      // Center the button text horizontally
    };

    // Create a pressable button element with custom styling and text
    const buttonOption = Pressable({
      children: [
        View({
          children: [
            Text({
              text: this.shopText, // Text content for the button (shop name)
              style: {
                fontFamily: "Roboto",   // Font for the button text
                color: this.shopTextColor, // Dynamic text color for the shop name
                fontWeight: "700",      // Bold text
                fontSize: this.featuredTextSize, // Featured text size
                alignItems: "center",   // Center the text vertically
                textAlign: "center",    // Center the text horizontally
              }
            }),
          ],
          style: {
            flexDirection: "row",  // Arrange children in a row
            justifyContent: "center",  // Horizontally center the text
          },
        })
      ],
      style: buttonStyle,  // Apply the defined button style
      onClick: () => this.onSlotClicked(),  // Handle button click event
    });

    // Define and return the root view that contains all UI components
    return View({
      children: [
        // The button container (including title and button)
        View({
          children: [
            Text({
              text: this.titleText, // Display the title text (player's name)
              style: {
                fontFamily: "Roboto", // Font style for the title text
                color: this.shopTextColor, // Dynamic color for the title text
                fontWeight: "700",    // Bold text for the title
                fontSize: this.featuredTextSize, // Set the size of the title text
                alignItems: "center", // Center the title text vertically
                textAlign: "center",  // Center the title text horizontally
              }
            }),
            buttonOption, // Add the button as a child of the root view
          ],
        })
      ],
      style: rootPanelStyle, // Apply the root panel's styles
    });
  }
}

// Register the `UI_ShopHud` component so it can be used in Horizon Worlds
Component.register(UI_ShopHud);
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 