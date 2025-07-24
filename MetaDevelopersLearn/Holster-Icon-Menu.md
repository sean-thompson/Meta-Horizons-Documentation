# Holster Icon Menu

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/holster-icon-menu)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452415087_512510754620214_5211438736433049027_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=NEIe3EWdExgQ7kNvwEP7aLF&_nc_oc=AdkW4b7I2r09vnHXqq9_8-nYIGlXkAGemeaVCvbhAdsmCyQXeF4N6UZHBSdp3b1_c4Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=QnIstGYkGhm4amhcHAc4Iw&oh=00_AfTPF91xeLviByeZOSWQPqoagtAZA147-FjQ3V_kxQBpgQ&oe=689BB3FC)

The holster icon menu is a menu of UI icons representing items attached to a player’s avatar. Players can use these icons to switch between and equip items. These icons show items that are grabbable entities attached to the player. **Note**: The holster button to open the holster icon menu will appear if a player has more than one grabbable entity attached.

## Attaching a grabbable entity to a player

For an item to appear in the holster icon menu when it is not equipped you must attach that grabbable entity to the player:

```
this.entity
  .as(hz.AttachableEntity)
  .attachToPlayer(player, AttachablePlayerAnchor.Torso);
```

You can combine attaching the entity with a primary input action API so the player can control the attachment process:

```
this.connectCodeBlockEvent(
  this.entity,
  CodeBlockEvents.OnIndexTriggerUp,
  (player: Player) => {
    this.entity
      .as(hz.AttachableEntity)
      .attachToPlayer(player, AttachablePlayerAnchor.Torso);
  },
);
```

## Configure how an entity appears in the holster icon menu

You can configure how a grabbable entity will show up in the holster icon menu by setting the **Holster Icon** property in the entity properties panel:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452586781_512510717953551_1463442642763553743_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=fp6RIA_a4wEQ7kNvwHaE0jH&_nc_oc=Adkanz-YUggtHKBdkpj-MfhVaHlxxz4fm6LxkN39p4uXqfTitexPZlPnHAYTVzdrsLM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=QnIstGYkGhm4amhcHAc4Iw&oh=00_AfS-bN2TvWkHXteeZFDXoSw3KGOXnn4zYil1GRi8l6JIbQ&oe=689B9452)

*   **Default value:**
    
     If you don’t specify a value, the holster icon will show the default slot number. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452718392_512510654620224_8780972206080984700_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=mZcBl4QbYwQQ7kNvwGLL1gZ&_nc_oc=Adk2WVDOneHaV1xY2K1CJuimkbabbqFm-bSt4rJjPUYVai9F_KzdGg262XK8aOufgho&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=QnIstGYkGhm4amhcHAc4Iw&oh=00_AfTwPZnwrm5dtAG63gUVobi2ZrUPHPvtGzXlu1_mNY8ReA&oe=689B965D) 

*   [Action icon value:](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/action-buttons/)
    
     The holster icon will show the selected action icon.

*   **None:**
    
     The entity will not be included in the holster icon menu.

To ensure an entity won’t appear in the holster icon menu, you can either:

*   Select **None** in the **Holster Icon** property on the grabbable entity.

*   Set the **Who Can Grab?** property of the grabbable entity to an empty array of Script assignees to make it impossible to grab.

#### Available Action Icons

The pool of available icons grows continually. The following table lists examples of the icons that you can select for controls on web and mobile.

| Shoot | Reload | Jump | Unholster | Drop | Special | Grab |
| --- | --- | --- | --- | --- | --- | --- |
| Interact | Throw | Ability | Rocket | Airstrike | Swing | Swap |
| Inspect | Open Door | Shield | Aim | Dual Wield | Sprint | Crouch |
| Eat | Drink | Speak | Purchase | Place | Heal |  |

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 