# World Capacity dialog

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/getting-started/world-capacity)

## Viewing the World capacity guidelines dialog

The World capacity guidelines dialog shows you how close your world is to meeting or exceeding the capacity limits of a World. To access the World Capacity dialog, open the **Main Menu** and select **World Capacity**.

![World Capacity menu item](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/493703357_717633330774621_7408317430748065666_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZGQwCvKiAKsQ7kNvwHMKq3S&_nc_oc=Adnakwk7-5eUD-OnFmyCuSgHrCON4yQC2zazJ44-mKa92QcToC-xB3NsMWU7qPyCYSw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=pXqM9v6ydDEkd_wMdbU9UA&oh=00_AfTixxhEp6ZNMXVpKUC2oZrBkWSJZNicRCczQnSOQBVzkw&oe=689B8EF0)

The World capacity guidelines dialog shows you the used capacity, as a percentage, of four major categories: Objects, Simulation and animation, World vertex count, and Sounds. If you at more than 75% of the capacity limit for any of these categories, you will see a yellow bar for the category. If you are at more than 100% of the capacity limit for any of these categories, you will see a red bar and an error message.

Note

The World vertex count category is incorrectly named in the dialog as world tricount. This will be fixed soon.

![World capacity dialog](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/495375229_717633327441288_7014509691232050718_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=soP_FMeQPzgQ7kNvwGiTYDA&_nc_oc=Adlmm4XyMvptDIFMZBo7u0OPOMOp1TTIzacf2Wqo7IFtHcO0ZOMuYtVrjKKERFO8tt8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=pXqM9v6ydDEkd_wMdbU9UA&oh=00_AfRBUqbg0LN6SUGglQQl2f6Ub8ClfdulyFhjui4eI36tbg&oe=689B8FFF) *World capacity dialog*![World capacity with Sounds at yellow](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/492508614_717633320774622_186645589074315552_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=b9BArx6SVcUQ7kNvwGPA9sh&_nc_oc=Adm7H8LHZ_Tc__bo0aqlsHKDzvvvKhd9IPdVcRKGveY-3HvdtFcthLQa57QvzeszprM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=pXqM9v6ydDEkd_wMdbU9UA&oh=00_AfTchqB_OPrnugH20y5Ac-vb-cJImvRtIJwc6ufZGGaxsg&oe=689BB03B) *World capacity dialog with Sounds at yellow*![World capacity with vertex count at 407% and error message](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/493105892_717633324107955_9093427791641727680_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=MEjP7Rspq8sQ7kNvwGEU0H9&_nc_oc=AdlJ5FbgJcZa3trCLlRQMt9TkZXSWns225hjNckYY4Af0BJWUqLl7AK87oipCDhCol0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=pXqM9v6ydDEkd_wMdbU9UA&oh=00_AfTNPvtwxheZ85jtmsZPx8uK2pBIGu9rjEaouW-xycNW0A&oe=689BB8EF) *World capacity with vertex count at 407% and error message* ## Understanding capacity limits

The capacity limits shown in this dialog are a quick snapshot of the current capacity of your world. There are other factors related to world capacity that are not shown in this dialog. To understand world capacity in more detail, see [Performance limits for a world](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-limits-for-a-world) .

### Objects

The objects category is the number of objects in your world that contain a mesh. The hard limit for these objects is 3000.

### Simulation and animation

The simulation and animation category is a shared bucket of objects related to simulation and animation. These objects are counted based on estimated simulation time, with a total limit of 4.2ms. They include:

*   **Dynamics**
    
     \- Each dynamics (moving) object counts as 0.0121ms.

*   **Triggers**
    
     \- Each trigger object counts as 0.002ms.

*   **VFX**
    
     \- Each VFX object has its own estimated simulation time, from 0.0059ms to 0.1ms.

*   **Physics**
    
     \- Each physics object counts as 0.008ms.

*   **Texts**
    
     \- Each text object counts as 0.0035ms.

*   **Players**
    
     \- The estimated simulation time for the [maximum allowed players](/horizon-worlds/learn/documentation/desktop-editor/settings-modifications/player-settings-modification) in the world, ranging from 0.0ms for 1-4 players up to 2.8ms for 20-32 players.

### World vertex count

The world vertex count is the number of vertices currently rendered in your world. This includes all the vertices in your world, even the ones that may be culled by being out of view. You can have at most 125,000 vertices in a world.

You can reduce vertices by using simpler meshes. See the section for “Highly detailed meshes” in [GPU best practices](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/gpu-best-practices#highly-detailed-meshes) .

### Sounds

The sounds category counts the memory used by sounds in your world. The hard limit for this category is 15,000 kilobytes.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 