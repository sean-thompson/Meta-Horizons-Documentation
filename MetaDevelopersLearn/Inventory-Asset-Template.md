# Inventory Asset Template

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/inventory-asset-template)

Note

You will need to be a member of MHCP and have accepted the monetization Terms Of Service in the creator portal in order to create in-world items and currency. Find out more about monetization [here](/horizon-worlds/learn/documentation/mhcp-program/monetization/creator-monetization-partner-program) .

The Inventory Asset Template allows creators to easily list the items a player owns or can own within a world. The items displayed and their configuration can be set up using the props element of the included Inventory script. An arbitrary number of items can be listed here, and if the content is larger than the screen there’ll be a scroll bar for the player to navigate through it.

The Inventory Asset Template can be configured to display in-world items created in the **Systems > Commerce** menu. For more information on creating in-world items, visit the [In-World Purchase Guide](/horizon-worlds/learn/documentation/mhcp-program/monetization/meta-horizon-worlds-inworld-purchase-guide#creating-an-item) .

Behind the scenes, the world inventory stores how many of each in-world item is owned by each player. While the Inventory Asset Template interfaces with the world inventory automatically, you can use [World Inventory TypeScript APIs](/horizon-worlds/reference/2.0.0/core_worldinventory) to manually query, grant, and consume in-world items in a player’s world inventory.

## Access the Inventory Asset Template

To access the Inventory Asset Template: In the desktop editor, enter the Build mode and select **Asset Library > Public Assets** from the bottom menu bar. Next, search for “Inventory” in the search field. Finally, select the Inventory Asset Template and drag it into the scene. You can now edit the new asset template properties in the **Properties** panel.

![Finding the Inventory Asset Template](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/495704689_734911825713438_4000559892879335779_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=SdhinziOCjkQ7kNvwG4R2cZ&_nc_oc=AdmhQw0xiA7Gh_3qEpToTysdyiZ37f694q57ulFoOPYgXZ1EZ60G6ZCuAxvN1CkvZWg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DStd0k-n9SFCEwEUspjI3Q&oh=00_AfRLKX7QTgSBQAvMbA2t6BVFMFNEQ8Xnqk4iQ5b6zJtU4w&oe=689BC485)

## Inventory Asset Template properties

The Inventory Asset Template properties can be configured in the **Properties** panel or through scripting.

### Visual and interaction

Here you can change the following:

*   **ID**: ID of the Inventory. Used to differentiate between multiple inventories in the same world.

*   **Displayed Title**: Name of the Inventory, which is displayed in the top-left corner of the Inventory UI.

*   **Displayed Title Icon**: Select an icon to display next to the Inventory title.

*   **Item SKU**: The SKU of an item you want to display in this Inventory.

*   **Item Thumbnail**: The thumbnail of an item you want to display in this Inventory.

### Inventory items

To use the Inventory Asset Template, you will need to create in-world items through the **Systems > Commerce** menu. Once you have done this, you can add these items to the Inventory using the Inventory Asset Template properties.

You can use the Inventory Asset Template properties to configure which in-world items to display.

## Scripting

You can interface with the Inventory Asset Template directly through TypeScript and fully customize the Inventory’s behavior. Please refer to the [World Inventory TypeScript APIs](https://developers.meta.com/horizon-worlds/reference/2.0.0/experimental_worldinventory) documentation for more information on the economy APIs.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 