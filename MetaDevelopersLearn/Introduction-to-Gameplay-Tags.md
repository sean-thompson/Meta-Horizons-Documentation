# Introduction to Gameplay Tags

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/gameplay-tags-api/introduction-to-gameplay-tags)

Gameplay Tags are user-defined labels given to gameplay objects. These labels allow you to define sets of objects e.g., player, respawn, and enemy to identify and manipulate using scripts. This new tag type expands on the current functionality of tags - removing existing pain points - and aligns more closely with industry standards. To learn more about possible use-cases for tags and understand how tags are used in game development, visit the [Unity](https://docs.unity3d.com/Manual/Tags.html) and [Unreal](https://docs.unrealengine.com/4.26/en-US/ProgrammingAndScripting/Tags/) documentation on tags. With this update, your entities will automatically migrate to the new field type: “gameplayTags” and be ready for use in scripts.

Gameplay Tags allow you to:

*   Assign multiple tags to a single entity (up to 5 tags with a max of 20 characters per tag)

*   Manipulate tags using TypeScript e.g. add, remove, set, and compare

*   Search with Typescript using AND|OR to find entities with specific tags or sets of tags on a “World” level

*   Assign tags to triggers and raycasts

*   Filter entities by tags in Desktop Editor

For more information on the Gameplay Tags API and to see example code, see the [API reference doc](/horizon-worlds/learn/documentation/typescript/gameplay-tags-api/modify-gameplay-tags-on-entity-and-get-entities-with-tags/) .

## Using Gameplay Tags in Desktop Editor and VR

Since this feature involves multiple moving parts, below are a few different scenarios for modifying and manipulating gameplay tags in Desktop Editor and Build Mode in Meta Horizon Worlds.

To quickly navigate to a specific editing workflow, use the following links:

*   [Tag Editing in Desktop](/horizon-worlds/learn/documentation/typescript/gameplay-tags-api/introduction-to-gameplay-tags#tag-editing-in-desktop-editor)

*   [Tag Editing in VR](/horizon-worlds/learn/documentation/typescript/gameplay-tags-api/introduction-to-gameplay-tags#tag-editing-in-vr)

*   [Tag Filtering](/horizon-worlds/learn/documentation/typescript/gameplay-tags-api/introduction-to-gameplay-tags)
    
     (Desktop#tag-filtering-in-desktop-editor)

## Tag Editing in Desktop Editor

Using Desktop Editor, you can search for, add, remove, and modify gameplay tags. **Search for a tag** *   Navigate to the right-most menu and find the “Gameplay Tags” section 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452819243_512510297953593_3713360108182145117_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=0W6KirnQJisQ7kNvwH4UnbD&_nc_oc=Adms7yhctpVpXvKE5563he-_Pg7KdheGJh9K5GHsl2KnhHP1mHu636czLTVLudDax-s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfSqUHknv01lXhKjYHOWqDkHohv_hwRhgW63dW-jxoWzRw&oe=689BB570) 

*   Enter the keyword in the search bar and press enter 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452531950_512510307953592_5435334402365433075_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=yOLSJo3CZ5AQ7kNvwFf_NqR&_nc_oc=AdmaoMWWAg95rPcWY4BcxHxhbyf2QQfsrscfM88V3SvA0J8O9L9co4lDmEk3zOoxdEk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfT6ngd5c9olMjXeIr3DxlwDKPh4EEXTaEwfUyoqEcLAoQ&oe=689BAF81) 

*   Any entities with this tag should appear **Add a tag** *   Select the object 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452932800_512510317953591_7736172710593851318_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=Inpr076evScQ7kNvwGf-Pft&_nc_oc=AdlRfNiNcmAMOI053ALwHXvJScZZOc6EkfDhXNzx2KTNMxdmp5oI9mNulIEn2jDE-34&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfSUhuD4gC--GtlV07yETrS0UCFHW4BO5tBqt9mfrKaZwQ&oe=689B8FD4) 

*   Navigate to the right-most menu and find the “Gameplay Tags” section 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652805_512510324620257_7535330597218424662_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=CPg8GSA-n9MQ7kNvwFn70ti&_nc_oc=AdkzS_7HWec1mgoTgZiwqYXld2NDLsFn0_djd6Pf5zs32ec9kGEeb3BT5ZvUsoFQSrA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfQ6admBO6fGsOj89kW3K-fredWzXYQTe6tOyytYu8uqvg&oe=689BAC8C) 

*   Select the “+” symbol next to the search bar 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452533361_512510337953589_5428023551380485005_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=LJsDl75K4j8Q7kNvwHiJPgr&_nc_oc=AdnEZcdvRcrKyFwethnEGziDywo_686W2KwTdyd0QLY28407GmX9Uzev-jFKK0O2nYA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfSOEVsW3NjsTkKwaTKkCFrS9rEOOL7eyVU0WA6x3v0G_Q&oe=689B91A8) 

*   Enter tag name into field and press enter 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452698786_512510327953590_7203122234308935135_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ne-DfdXQuWsQ7kNvwEjamWp&_nc_oc=AdlwguLJWkUWpm9p2M3o5DEAvwa3fiIF1uoNC1FID_tda2M9QiQaHarGlCqkFt_Fac0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfRZ76NOdq96Iau1Fa7pCMOsS1l0zHTA2E7RfLM-mikRCg&oe=689BB42C) 

*   The tag will now appear under the object’s tags 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915412_512510331286923_4938518147116670862_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=-j92VEIONC4Q7kNvwG8td5u&_nc_oc=Adlsir3_qr9GPc4Kgj3TugUrkhsq-f4zsFLLK_CxffiigCelPzsCjUwlFD88LbDoX_I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfS9Z-LtppazX7z4Z8tG1-1-NxQorI_F_3eUix8nuuE1Ew&oe=689B8F72) **Remove a tag** Repeat steps 1 and 2 from “Add a tag”

*   Navigate to the desired tag to remove and click on the “-” icon 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452533360_512510341286922_8800632251859838755_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=X6C7Xy6RDC0Q7kNvwGOQsio&_nc_oc=AdkfIgRK3HbYciaAy7vwnGc02LM1N9dksiCrCqE7P3lUgqv1RxVagsKL4XfG5pcYmu4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfRuHcpbG1viOjX_ptlIlHER1E7VZ1uUbnYjQZZ4MSeDBA&oe=689BB4A2) 

*   The tag will be removed from the object’s tags **Modify a tag** Repeat steps 1 and 2 from “Add a tag”

*   Navigate to the desired tag to modify and click on the pencil icon 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452704028_512510334620256_4085579888356380485_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=MfckkIHQWM0Q7kNvwHs2HhP&_nc_oc=Adl4fIuWIw7KJ8RX_Yx1rInu4juYNnL6TUWMxXW0cwxQRGRa1K33cX7KI25kQ_MR-eE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfTShZRtmPPlnfh4qriDEn6DHC4PwYxT39Poil4tigcs4A&oe=689B967E) 

*   Enter the new tag name or modifications 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453001282_512510314620258_5253799186195480687_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=ybxjgi6XYZsQ7kNvwHzUVWX&_nc_oc=Adkl8GLFzrQdsa3Z3fK26oTDJZ7JMbtDdEsUw825QB0Xh3usXhExmsb-MzaFdtsvgsI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfRf5uCQOOogau_JC6UakFG9bxayC3K9RR-_u46Ix0R7TQ&oe=689B940B) 

*   Click enter and the tag will update
    

## Tag Editing in VR

Adding, removing, and modifying tags in VR is a similar process to that of Desktop Editor. The following video shows where to find tags (under Attributes in a game object’s menu) and how to remove, add, and modify them.

## Tag Filtering in Desktop Editor

In the “Hierarchy” menu of Desktop Editor, you’re able to filter entities by their associated tags. To do so, click on the filter icon and select the appropriate tag and watch the list re-populate with only the entities using that tag.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652242_512510271286929_4441725871151863114_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=FXvnSWBZkOYQ7kNvwHTA_4b&_nc_oc=Adlu9VBoUoi0OYPG6Z4UlVcR_pyTuFnLgDiv5k-2TMzhdNLx2BwGUzKR57N5FKB8BGo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ah1NGEJSto4Bmq28g9LPbA&oh=00_AfTeZIRYwMDPhyqr09A3kNg4D64qbPv5Of0YCYZ6yDNZ7g&oe=689BB73B)

## Known Issues

*   Due to limitations on world builder that do not allow for collection types on Entity fields, tags are stored as a JSON serialized string. To counteract the performance implications of serialization, we’ve introduced a service that caches tags in a readily available set to perform any matching operation on an Entity’s tags.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 