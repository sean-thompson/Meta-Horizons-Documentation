# Daily Rewards Asset Template

[source](https://developers.meta.com/horizon-worlds/learn/documentation/code-blocks-and-gizmos/daily-rewards-asset-template)

![Daily Rewards Asset Template](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/497935804_734911832380104_6962771998323814286_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=1aMVHjHJfN8Q7kNvwGKViaJ&_nc_oc=Admn2dNynhgXxr7aBfPtLCgO8JOIagekotzq8wsCCNbygcizyNDjhbPhEw4GEPBjfps&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=trUGgS9KtnOUXKd8AxGPAA&oh=00_AfR-esOIQ4i13VhoNFnElOxtQvU6_-ARqw6T0eJ5NbVsaQ&oe=689BA5F8)

Note

You will need to be a member of MHCP and have accepted the monetization Terms Of Service in the creator portal in order to create in-world items and currency. Find out more about monetization [here](/horizon-worlds/learn/documentation/mhcp-program/monetization/creator-monetization-partner-program) .

The Daily Rewards Asset Template allows users to be granted rewards for each day they log in to your world helping improve retention and engagement.

The Daily Rewards Asset Template can be configured to grant in-world items created in the **Systems > Commerce** menu. For more information on creating in-world items, visit the [In-World Purchase Guide](/horizon-worlds/learn/documentation/mhcp-program/monetization/meta-horizon-worlds-inworld-purchase-guide#creating-an-item) .

Behind the scenes, the world inventory stores how many of each in-world item is owned by each player. While the Daily Rewards Asset Template interfaces with the world inventory automatically, you can use [World Inventory TypeScript APIs](/horizon-worlds/reference/2.0.0/core_worldinventory) to manually query, grant, and consume in-world items in a player’s world inventory.

## Access the Daily Rewards Asset Template

To access the Daily Rewards Asset Template: In the desktop editor, enter the Build mode and select **Asset Library > Public Assets** from the bottom menu bar. Next, search for “Daily Rewards” in the search field. Finally, select the Daily Rewards Asset Template and drag it into the scene. You can now edit the new asset template properties in the **Properties** panel.

![Finding the Daily Rewards Asset Template](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/503910304_734911829046771_4309394035385604873_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=pCkgED_6LQ0Q7kNvwFUOZ5G&_nc_oc=AdlWMwCQViJKvGH7u257cZSFH0ZD9AIrsjQA-WxHWeXL84Hq5NC5tJBtEu4usg8PM9k&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=trUGgS9KtnOUXKd8AxGPAA&oh=00_AfRjZRTLwnKsPsQ3EsvrlEZGNMCotzn1TLjyTpVTSBHfXQ&oe=689BBB16)

## Daily Rewards Asset Template properties

The Daily Rewards Asset Template properties can be configured in the **Properties** panel or through scripting.

Note

In order to save the state of the daily rewards for each player, you will need to create a new Persistent Variable of type *Object* and assign it’s key under the Daily Rewards Asset Template properties. Find out how to create and use Persistent Variables [here](/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/variable-groups/managing-persistent-variables-associated-with-a-variable-group) .

### Visual and interaction

Here you can change the following:

*   **Id**: ID of the daily rewards. Used to differentiate between multiple daily rewards in the same world.

*   **Displayed Title**: Tile displayed in the top-left corner of the daily rewards UI.

*   **Displayed Title Icon**: Select an icon to display next to the daily rewards title.

*   **Persistent Object Variable**: Id of the Persistent Variable of type *Object* used to store the event state. See the note above for details on how to create it.

*   **Daily Rewards Activation**: Whether the daily rewards system is active (default *true* ). Set this to *false* when you prefer to enable it via the TypeScript API.

*   **Auto Repeat**: Indicates if the daily rewards automatically restarts after the player has collected all rewards available (default *true* ).

*   **Show Timer**: Whether the timer with the remaining time for the next reward to be available should be shown (default *true* ).

*   **Reset Streak If Day Is Missed**: Whether missing a day resets the player’s streak (default *false* ).

*   **Day X Reward SKU**: The SKU of an item you want to award the player for logging in on day X.

*   **Day X Reward Quantity**: The quantity of the chosen award item to be granted.

*   **Day X Reward Thumbnail**: The thumbnail of the chosen award item to be granted.

### Daily Rewards items

To use the Daily Rewards Asset Template, you will need to create in-world items through the **Systems > Commerce** menu. Once you have done this, you can add these items to the awards list using the Daily Rewards Asset Template properties.

You can use the Daily Rewards Asset Template properties to configure which in-world items to grant on each day and their respective quantities.

## Scripting

You can interface with the Daily Rewards Asset Template directly through TypeScript and fully customize the feature’s behavior. Please refer to the [World Inventory TypeScript APIs](https://developers.meta.com/horizon-worlds/reference/2.0.0/experimental_worldinventory) documentation for more information on the economy APIs.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 