# In-World Purchase (IWP) in Codeblocks

[source](https://developers.meta.com/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/in-world-purchase-iwp-in-codeblocks)

Author: SeeingBlue

## Introduction **Creator Skill Level** Intermediate **Recommended Prerequisite Background Knowledge** An understanding of Intermediate Codeblock Scripting, [Persistent Player Variables](/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/variable-groups/managing-persistent-variables-associated-with-a-variable-group) , and [Basic Asset Spawning](/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/part-one-understanding-asset-spawning-with-seeingblue) is recommended. **Note**: IWP creation is now available in the Desktop Editor. Visit the [documentation](/horizon-worlds/learn/documentation/mhcp-program/monetization/meta-horizon-worlds-inworld-purchase-guide) for more information on this. **Description** In this document, we will go over the different types of In-World Purchases (IWPs), how to create each one, their related codeblocks, and some examples of how to use them. **Learning Objectives** By reading and reviewing this written guide you will be able to:

*   Understand the IWP item types and related codeblock events, actions, operators, and values.

*   Create all IWP item types including durable items with and without assets, auto-use and manual-use consumables, and group consumables together using item packs.

*   Create purchases for members-only areas in your worlds, offer tangible items via the player’s inventory, and sell consumables to enhance gameplay.

## Understanding IWP Item Types and Related Codeblocks

### IWP Types

*   **Durable without Asset**
    
    *   Permanent (unless deleted by the user)
    
    *   Used as a permanent status on a player, like VIP.

*   **Durable with Asset**
    
    *   Permanent (unless deleted by the user)
    
    *   Unlimited uses
    
    *   Retrieved from player’s Horizon inventory
    
    *   Used for items players can spawn/despawn from their inventory.

*   **Consumable with Auto-Use**
    
    *   One-time use (can be repurchased)
    
    *   Consumed immediately after purchase, does not appear in inventory
    
    *   Does not require confirmation
    
    *   Used for temporary statuses, time-based upgrades, and more

*   **Consumable without Auto-use**
    
    *   One-time use per purchase, can stack multiple purchases
    
    *   Consumed from Horizon’s Inventory
    
    *   Requires confirmation (via codeblocks) before consumption
    
    *   Used for temporary statuses, time-based upgrades, and more

*   **Item Packs**
    
    *   Created out of *Consumables without Auto-use* items.
    
    *   Allows you to combine a consumable into a stack of multiples.
    
    *   Used to discount the sale of multiple consumables at once.

### IWP Codeblocks **Broadcast Events**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461828106_558937446644211_4069079405675549335_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=w_sYpyoBshAQ7kNvwFEPZnH&_nc_oc=AdlegObv1DCmVZNEM7UuHTfKSOkl-U-N-J5jPFplxaDOvReFow4meH3cqfiGp7Zz6h4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfQVK9DOObATXDK8Y0J67WZOcGz8qX_qxC7cjOBFDfjuuA&oe=689BA6F4)

*   **“when player starts purchase item (broadcast)”**
    
    *   Broadcast Event - Can be heard from any script in the world
    
    *   Parameters
        
        *   `player`: A reference to the player who started the purchase
        
        *   `itemId`: A string containing the name/id of the item being purchased.
    
    *   This can be used on any script where you need to know when a purchase is started.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461872321_558937569977532_4169706045827159329_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=HdCW8lwjctcQ7kNvwHGK2uY&_nc_oc=AdnCeWuKgHRWaqW3VXWY8JbK_7tdQpiDC6C-NV97lvD3HBWO9YBNEVaxlgbX0vV7D4g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfQnORKxLtxI4Ea--Ji7UdE6weRYBpsq9QwO5Kom3AT05A&oe=689BB666)

*   **“when player completes purchase item (broadcast)”**
    
    *   Broadcast Event - Can be heard from any script in the world
    
    *   Parameters
        
        *   `player`: A reference to the player who completed the purchase
        
        *   `itemId`: A string containing the name/id of the item purchased.
        
        *   `success`: A boolean letting us know if the purchase succeeded or failed.
    
    *   This can be used on any script where you need to know when a purchase is completed successfully or not.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461742436_558937363310886_7632016646801491315_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=7Vq6LEzga-YQ7kNvwGJHSUx&_nc_oc=Adnl3K69wRHn2s2pLFjdiqNnfWI5zZX0Ej4l_cBUQt7jaLeQeESbTWE2tCfAeIw913E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfTQYJk826JRy-NU_9RUpWuZSjSpfRpjFi7NLYfc_a3RgQ&oe=689BAD1C)

*   **“when player starts consume item (broadcast)”**
    
    *   Broadcast Event - Can be heard from any script in the world
    
    *   Parameters
        
        *   `player`: A reference to the player who started the consumption.
        
        *   `itemId`: A string containing the name/id of the item being consumed.
    
    *   This can be used on any script where you need to know when consumption is started.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461947158_558937576644198_8509130094477816769_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=c9kE6UjbVzQQ7kNvwFyiIH6&_nc_oc=AdlHrfciwG6Z2MCyeGox4dTuQ-WgsGeRpL0F0Po613B5QJ3g_j43wBk5_7_7nCfx-6A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRkg1CN4p3auSMTiBJf6DOEFRFyDIkxPpcB0B2vQ0mHQw&oe=689BBE5D)

*   **“when player completes consume item (broadcast)”**
    
    *   Broadcast Event - Can be heard from any script in the world
    
    *   Parameters
        
        *   `player`: A reference to the player who completed the consumption
        
        *   `itemId`: A string containing the name/id of the item consumed.
        
        *   `success`: A boolean letting us know if the consumption succeeded or failed.
    
    *   This can be used on any script where you need to know when consumption is completed successfully or not. **![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462013257_558937543310868_2866554405895002171_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=7LJn7od4BesQ7kNvwH3Lbi0&_nc_oc=AdmACov8_cX9poYBy3VtP09mTRYDkbeFMABlekZNZj0ZO_uozEV6VI7UtSEwcnjfo5c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfTw449eWvqI6m3UFjzacj4pGBCPDL-U3tPoGmupK-0AnA&oe=689B9464)** *   **“when an asset spawns from player inventory”**
    
    *   Broadcast Event - Can be heard from any script in the world
    
    *   Parameters
        
        *   `obj`: A reference to the object that spawned from the player’s inventory.
        
        *   `asset`: A reference to the asset used to spawn the object.
        
        *   `player`: A reference to the player that spawned the item from their inventory.
    
    *   This can be used on any script where you need to know when an item has spawned from a player’s inventory. **Non-broadcast Events** **![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461860683_558937423310880_5802107090403536248_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=T-6P_3rOIJwQ7kNvwEd_jFz&_nc_oc=AdnO4dKVWBvV-wE_DP8JfzAzUnWexrMg9AhD_VdXUvDLibh5ooIBFnj2844ytPiVkNM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSoqx-dkLhTpzqY2aYsdHcPNL7zynF-snqu1cB9GgJFXg&oe=689BC4BA)**

*   **“when player purchase succeeds on item”**
    
    *   Standard Event - Script must be attached to an In-World Item gizmo.
    
    *   Parameters
        
        *   `player`: A reference to the player that purchased the item.
    
    *   This can be used in a script attached to a specific In-World Item gizmo that you need to know when a purchase of that item is successful. **![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461795097_558937546644201_8837716101915000798_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=vpPEMNPZeBoQ7kNvwEUtGJN&_nc_oc=AdksTrq_M86YxuYnSM0xMN4fzOpIgqdFwTiLoGSH8fFdrj9kg4xmjx-byTHDDO99VQo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfS1DSUiLU7-sFg5VyH95c-6c48eVZbfO77RTHdEXXBWgw&oe=689BC4F8)** *   **“when player purchase fails on item”**
    
    *   Standard Event - Script must be attached to an In-World Item gizmo.
    
    *   Parameters
        
        *   `player`: A reference to the player that attempted to purchase the item.
    
    *   This can be used in a script attached to a specific In-World Item gizmo that you need to know when a purchase of that item fails.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462000937_558937573310865_3749702168699519294_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=NN7n4bCq7MkQ7kNvwEq1qgk&_nc_oc=AdkKnnMkH3humMfmWelu2yziXGP8XPY16IO_sONKObX04CrgOvYR3x-Yo1QlPl9n_g8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfQangSyCuBjHJl_beQ1YljYsZwyN6H28bHCmIdsCT6T1A&oe=689B978A)

*   **“when player consume succeeds on item”**
    
    *   Standard Event - Script must be attached to an In-World Item gizmo.
    
    *   Parameters
        
        *   `player`: A reference to the player consumed the item.
    
    *   This can be used in a script attached to a specific In-World Item gizmo that you need to know when the item is consumed successfully.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461730009_558937549977534_9215645537090210231_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=xcVTSKXuSl8Q7kNvwGdFRvA&_nc_oc=AdlXWSKMY8JDnQVUfNxPL61XqdMShDg0EiAl3VIWcD1JvJ8tB-JXyKClvI8YiaPpJBA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSkMAp2YE8-ZSXUvl5Rkq1f396j0WMVBRe0m3_mFbVB7g&oe=689BB058)

*   **“when player consume fails on item”**
    
    *   Standard Event - Script must be attached to an In-World Item gizmo.
    
    *   Parameters
        
        *   `player`: A reference to the player that attempted to consume the item.
    
    *   This can be used in a script attached to a specific In-World Item gizmo that you need to know when the item failed to be consumed.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461742624_558937533310869_3315324053455887134_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Mh31ro5deU8Q7kNvwHY8Jeg&_nc_oc=AdkLJraMnv450NJBWUC7ASvmUqcn2t-asWIf48uVH3iKNhN17v0zAMfxdyzsyo0_ntI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSxeYKtn1Xn77daTXdgvE0ixRWyVH2qnl3gsxA3LTNH4g&oe=689BCB16)

*   **“when player try to consume item”**
    
    *   Standard Event - Script must be attached to an In-World Item gizmo.
    
    *   Parameters
        
        *   `player`: A reference to the player that’s trying to consume the item.
    
    *   This can be used in a script attached to a specific In-World Item gizmo that you need to know when the item is attempted to be consumed. **Actions**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461688556_558937503310872_7649843234651612191_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=KcLe1d2-JGMQ7kNvwH5EyWT&_nc_oc=AdkI1gJjVLLJKFGdwrSCgjfVCDmAdZaNdRnOm8htV5N4EaHD45HPeO-HaluLZDNu6Zs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRUYQv5wTahXzljVIF2uTxBKLthGvV2bPrtRqNCeoN70Q&oe=689BB910)

*   **“consume item for player”**
    
    *   Required Parameters
        
        *   `player`: A reference to the player to consume the item.
        
        *   `itemId`: A reference to the item to be consumed.
            
            *   *Note*: This is an *Input Value* found under the *Values* category of your Script gizmo.
    
    *   This is to be used to confirm the consumption of a *Consumable without Auto-use*. **Operators**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461974836_558937439977545_6340259987809215145_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=xeUDmKu66IwQ7kNvwGkHTXZ&_nc_oc=AdndVhIKcl21iGA0K5iH17faYSHhicp2ZJJLLEcB4zMJ_cc4q_wF2lrPGBXNECg8MHk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSGefH0wWmKu07Trt7Me7pCO2CJCx3mcKIDEXFzmgT1Kg&oe=689BC716)

*   **“player owns item”**
    
    *   Required Parameters
        
        *   `player`: A reference to the player we’re checking.
    
    *   Returns a boolean that tells us whether the player owns the selected In-World item. **![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461742917_558937506644205_5976681854130956775_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=B9UZ1stdil4Q7kNvwHKD6Bt&_nc_oc=Adk4xW6u9vGV220TgsiQULN4HTltBvC_oak6WMLRSSgQ8ZIgQgBklJmEeG_Ns_jDqlM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSQZe48aS6_wDwaZTgawReE3aZJmjsn-qWxjhOdPx9eJQ&oe=689BAE4E)** *   **“player owns item quantity”**
    
    *   Required Parameters
        
        *   `player`: A reference to the player we’re checking.
    
    *   Returns a number that tells us how many of the selected *Consumable without Auto-use* the player owns.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461797566_558937459977543_901849217770869654_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ppd9YQELkbYQ7kNvwEQ_q_R&_nc_oc=AdnSCol0zSh6HppOseZSelB96BXv9lr85Skv0Rq2ZhkDPX64-gjBXLEoeabvyAkGPVg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRwzsgdqdy-5jwGSIoGSsJGkhoKMrACYkglXnXJoERAIA&oe=689BA0CD)

*   **“time since player consumed item”**
    
    *   Required Parameters
        
        *   `player`: A reference to the player we’re checking.
    
    *   Returns a number based on the selected value from a dropdown menu. Options are seconds, minutes, and days. The returned number represents how many seconds, minutes, or days that have passed since the item was consumed.
        
        *   *Note*: Returns a 0 if the item has never been consumed. Recommended that you use this in conjunction with the “ *player has consumed item* ” codeblock.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461825844_558937443310878_2067734326099493470_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=XHIu4wrxECkQ7kNvwESfk4o&_nc_oc=Adkozk-5QOegPJ8EUXjS2LufGkONt-9eHV_aTtsf903DHMN1Bj57HOOCfZKTkdv-JoE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfTSolLrqnFj1YSO5enkQGXEsm9duz_xNbJQXwEK2rJWUQ&oe=689BBEF3)

*   **“player has consumed item”**
    
    *   Required Parameters
        
        *   `player`: A reference to the player we’re checking.
    
    *   Returns a boolean that tells us whether the player has consumed the selected item. **Values**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461976591_558937589977530_5446846885349310805_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=WVP86cP2r2kQ7kNvwGrMv5f&_nc_oc=AdmKoylILuyNu7BaxvGnTvIZA1Npg8wlFrU_a7-wTzgYIy0Ym0mK-BzjhHrJBlFya_w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfTvSgFjIuwz2GDx-iDSP6ONC_o5-KJFYVGa5F7a3r5Sjw&oe=689BA321)

*   **“in-world items”**
    
    *   Contains a dropdown menu that lets you select an In-World Item ID to be used when making conditional checks in your IF statements.

## Creating an IWP

Creating and implementing IWPs involves a series of steps from item creation to placement in your world. This section will walk you through the process of setting up IWPs, including naming, pricing, and configuring item properties. You’ll learn how to create durable and consumable items, add them to your world, and customize their appearance and functionality. **Step 1:** While in build mode, open your build menu, navigate to *Systems,* and click *Commerce* then *Create Item*.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461683576_558937513310871_2554100072706911353_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=fLI6LXiS6HoQ7kNvwFIwNVn&_nc_oc=AdkjtooSLHzVc-0Q8zGIiG-CpiUPV7-asw7Ox1OLL8E0qpkqBiG1zCiZm-qTUaKMmo8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfTglW9x6O9VmnQZML_QjzGBy8bi5ul-0RCQRCzxwXLI3Q&oe=689BA768) **Step 2:** Every IWP you create requires a *Name*, 

*Sell Price*, *Thumbnail*, and selected *Item type*.

| Durable In-World Item | Consumable In-World Item |
| --- | --- |
|  |  |
| Asset reference is optional. Leaving it blank will create a Durable Item without an Asset (permanent player statuses). Adding an Asset will create a Durable Item with Asset, like a permanent weapon, hat, etc… | Decide if your consumable will be automatically consumed upon purchase or allow the user to consume it from their inventory with Auto use. |

**Note:** *Description* is an optional field, but it is recommended that you provide a detailed description to help users understand what they are buying. **Step 3:** Once your In-World Item has been created, you can grab an In-World Item gizmo from your build menu and drag it into your world.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461688156_558937523310870_6289736828187432400_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=C9y18Ej0lAoQ7kNvwGOO7ZC&_nc_oc=Adlxy9xY8QHy4j_NsH7lUwVc4_4_-weZP_x0jr3b37MinjolxlcgTJb_dwUp5BdVNhQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSyef2m6khA5rhR22vE_c22D-SwHwM-dFYQKo9TiqgYWA&oe=689BBBE8) **Step 4:** Open the property panel for your In-World Item gizmo and there are several settings you can change here:

*   Hit *Select* next to *In-World Item* and select the In-World Item associated with this gizmo.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461835191_558937536644202_1528060342302655134_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=UGfBJC2XTbAQ7kNvwH32N0O&_nc_oc=Adn081-fFfM73u3uvcQDANdi2160aCNbTEZU1P81Gb6pHAA71GlUR0zXo4irjjRyFPw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRx-rZbbRHsyDovThqbM5q7wD6Cjn6zXs-Ewa4thiwvPw&oe=689BC092)

*   Click the dropdown next to *UI Property* and change the display style of your gizmo.

| Trigger | Button | Icon |
| --- | --- | --- |
|  |  |  |

*   This is also where you would attach any scripts using the non-broadcast event codeblocks described under the **IWP Codeblocks** section. **Now your IWP is ready for purchase!** ## Creating Item Packs

This section will guide you through the process of creating and selling Item Packs, including how to access the feature, select items, set quantities and prices, and make them available for purchase in your game.

Item Packs consist of *Consumables without Auto-use* offering players the ability to purchase items in bulk. You can create one by opening your build menu, navigating to *Systems* then *Commerce* again, selecting *Item Packs*, and clicking *Create Item Pack*.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461857884_558937456644210_2326314548428903926_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=e_5Q3bsfxqwQ7kNvwGTOyVy&_nc_oc=AdlbJ9b_m8QkQGnm0U1iWzy5x3my0Z_hRLkxAm_-iSIAkViEp54B3mh0ptDrVGCMH2E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRNcyKLqagWZyj1DWaHIEvgmIgXR7RvffR8308YfkkTEg&oe=689BC827)

The next window will ask you which *Consumable without Auto-use* you would like to make an Item Pack out of. Once selected you can choose an *Item quantity* between 2 and 99 then select your *Sell Price*.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461878408_558937519977537_2913137907270513473_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=T7RI3k-iUtAQ7kNvwEZQQ02&_nc_oc=AdmNdi6x12w3YDH3BOChft2uKGRSwO9YyCb9ZBsrTh5Ne9voc443Cs1uOUtlK97tde4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRjQT4vB1U_4ImIbcf_UbiO3iYWeizFm8XpZydNFHVyNA&oe=689BAA0B)

Once created you can follow the same steps 3-4 in the previous section, **Creating an IWP**, to start selling your item pack.

## Examples: Implementing & Selling IWPs

In the following section, we will apply what we learned in the previous sections to build practical applications for our world. Some examples will include developing members-only area, an inventory system for weapons or other items, consumable health potions, and a simple item shop. These examples will demonstrate how to implement common gameplay mechanics, allowing players to access restricted areas, manage their inventory, use items, and make purchases within the game.

### Durable without Asset **VIP Area** **Required:**

 Durable Item without Asset. Follow steps 1-4 under **Creating an IWP** to create the VIP commerce, and setup the related *In-World Item* gizmo. Then pull out a *Trigger Gizmo* to get started

Durable items without assets are straightforward since all you can do is check if the player owns the IWP.

In this example, the script below is attached to a Trigger gizmo that covers our VIP area. When a player enters the trigger, we will check if they own this item and respawn them if they do not.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461957051_558937409977548_2001440408993131692_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=BE932_ER3dQQ7kNvwHbrtNo&_nc_oc=AdmUIgiGtcty_kecna_2qMuquHRRuryTQ3MimLX9_Dg2Qj62s-zCFAdDDQP1dY_q7YA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRD4jIVirjgIiZhD90y4BtdCpyYuSh5ZO8_Bd21xIZ8DQ&oe=689BB235)

This is created by using the *when trigger is entered by player* event codeblock with an *IF* statement inside. We use a *NOT* operator and drag the *player owns item* codeblock inside of it. Using the *player* parameter from the event and an *in-world items* input value, we can complete this *IF* statement and respawn our players.

### Durable with Asset **Spawning from Player Inventory** **Required:**

 Durable Item with Asset. Follow steps 1-4 under **Creating an IWP** to create your durable item with asset commerce by assigning an asset from your asset library, and setup the related *In-World Item* gizmo. Then choose any object to run the following script. You will need to create an asset variable in your script, I called mine *assetToSpawn* and I linked it to the same asset from my asset library that I used when creating the *Durable Item*.

Durable items with assets do not require scripts, but what if we need to communicate with the item our player spawned?

This script can run anywhere in the world since it uses a broadcast event.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461857291_558937556644200_2432027789069136617_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=R6nBML3NiFwQ7kNvwFB-n1Z&_nc_oc=Admzdb025vIdCeJK2eYkuL46yL2nU6eTOFB_mesafGol1DxdjwEJaMc-LeMs0VKZ_1A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfQ0FNC06b0RtZz9SEcgz-WKHQ0yrr2CKHyGo7RLHY6gNQ&oe=689BA3DA)

Using the *when an asset spawns from player inventory* codeblock we get the object that spawned, the asset it was created from, and the player who spawned it. Since this is a broadcast event that will fire on any item spawning from any player, we’re going to check that the asset received by the event is the one we want by using an IF statement to compare the parameter to a specific asset variable in our script. Once we determine this is our asset, we can now send an event to the newly spawned object with our player as a parameter for the object to receive.

### Consumable with Auto-Use **30-VIP Access** **Required:**

 Consumable with Auto-Use. Follow steps 1-4 under **Creating an IWP** to create the VIP consumsable with auto-use, and setup the related *In-World Item* gizmo. Then pull out a *Trigger Gizmo* to get started

In this example, we use a consumable to provide time-based(30 days) access to our users for their purchase. This script runs on a trigger gizmo that covers our VIP area. **Note**: Because the script is too wide, I had to cut and modify the IF statement to show on two lines.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461976494_558937583310864_878520296293413428_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=a369JtqRWv8Q7kNvwE_upPg&_nc_oc=AdlgCXiXpzwCoykDH2HUgd1sBTbeCiDy9R9h4I39E6-ZN7jzoHwM4sDcdwELfo5WFUI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfREFbPBPrIbepQb6ueigOHi6YC5s9iTr-Za8_brp31d6Q&oe=689BA2AC)

This script uses the *IF* statement and the *NOT* operator just like in our previous example. We also incorporate the *AND* operator so we can check two conditions. First, we use the *player has consumed item* codeblock to tell us if they have consumed the item, then we use the *time since player consumed item* codeblock in conjunction with the *LESS THAN* operator and *number* input value to determine if it has been less than 30 days since they consumed. Because of our *AND* operator, if one of these conditions returns false, they will be teleported away from the area. **Restore Health** **Required:**

 Consumable with Auto-Use. Follow steps 1-4 under **Creating an IWP** to create the Health Restore consumable with auto-use, and setup the related *In-World Item* gizmo.

In this example, our users can purchase an instant health restore. This script is attached to the In-World Item gizmo and the events below will fire when the item is purchased. **Note:** This script assumes you have a player manager listening for the restoreHealth event.

We don’t have any need for the *when player purchase succeeds on item* or *when player purchase fails on item* events, but I wanted to show that they still fire.

We wait for the *when player consume succeeds on item* event to fire, although since this is an auto-consumed item, we could have also sent *restoreHealth* under the *when player purchase succeeds on item* event too.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461900167_558937563310866_6112818593593678494_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=udJY4EXOzOYQ7kNvwGgdZO2&_nc_oc=Adkrq7w0AlJD3BgLyJ9SxZzswbMphg8djB-fPMfQirAIExnkTDGMu4fVCSAARjgN2Ck&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfQKLOfL6ak9hNCgdbiqO4--FTHRJji6Ini9DMsVMdb2Sw&oe=689BC9F1)

Below you’ll see an example of my player manager script to give you an idea of what that looks like. This script can be ran on any object in the world and listens for events being sent to players.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461981641_558937419977547_840786302865238297_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=JgfaX_AZ_OUQ7kNvwG55BNQ&_nc_oc=AdnZWOF0oJcAseHbRlNfomWuRLvAe-Tfc90R7Xc6hfqKwdHToOdf1uPpbRvgbaKceKQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfSJGKS8caZkGw8yqBewojJ05oXfTpXJf-b-_dptEPm3_g&oe=689BB17B) **Coin Shop** **Required:**

 Consumable with Auto-Use. Follow steps 1-4 under **Creating an IWP** to create the Coin consumsable with auto-use, and setup the related *In-World Item* gizmo.

This is the same script as the previous **Restore Health** script, but I also wanted to show that you could set a Player-Persistent Variable. This script is attached to the In-World Item gizmo and the events below will fire when the item is purchased.

In this example, the user purchases 100 coins so we need to add the coins to their Coins PPV.

We use the *set player persistent var* to codeblock with a + operator to add their current Coin PPV that we retrieved using the *get user persistent var* codeblock to a number input value of 100.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461688722_558937579977531_291030443651548477_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=zykT1p5RkwQQ7kNvwGfBQML&_nc_oc=Adl-vcWHYqL_TBk1Q4RuwsiCiq6a7IKfH847XGEzzgHiziCwRfFWNuxIftCWoCz14Mo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRDkgSWoBiCFmhLQ5QbhcVI2zV0mUM2tiYUaqFtFPMMCw&oe=689BBDF6)

### Consumable without Auto-use **Example: Manual Health Restore** **Required:**

 Consumable without Auto-Use. Follow steps 1-4 under **Creating an IWP** to create the Health Restore consumsable without auto-use, and setup the related *In-World Item* gizmo.

In this example we show how to handle manual consumption of an In-World Item without auto-use, meaning the item is stored in the player’s inventory and consumed when they are ready. This script is attached to the In-World Item gizmo and the events below will fire when the item is consumed.

The important thing to note when a player tries to consume a *Consumable without Auto-use* is that you must recognize this using the *when player try to consume item* *from inventory*

 codeblock and decide whether to acknowledge this attempt using the *consume item for player* codeblock before the consumption is considered successful, otherwise, the consumption will fail. Refer to the previous example, **Restore Health**, to see what a player manager script would look like.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461732831_558937416644214_556034990091293698_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=nqNtDIRv8MsQ7kNvwE9wCdR&_nc_oc=AdkFk8Lbm4hz9nj0CxqHnQnOGu1cRtJS7Admc8QnK1K9dWVmAmJnRSJc908_Mj8nafU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=HH6wC6okGE8DYnWEVrMaKQ&oh=00_AfRoIDadXZKanLmcwdu2eqeSoIQSynDlYTGZz7hGPAKvRg&oe=689BC22F)

## Extended Learning

To reinforce your understanding of IWP mechanics and put your new skills into practice, try completing the hands-on challenges provided below: **Challenge 1:** Create a basic auto-use and manual-use consumable, then purchase and consume it in build mode. Additionally, go on to create an item pack out of the manual-use consumable. **Challenge 2:** Create a basic durable item with and without an asset, then purchase and use it in build mode.

## Further Assistance

For any questions or further assistance, creators are encouraged to join the discussion on the Discord server or to schedule a mentor session for personalized guidance.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 