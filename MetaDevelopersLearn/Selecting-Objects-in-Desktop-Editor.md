# Selecting Objects in Desktop Editor

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/selecting-objects-in-desktop-editor)

When working in the Desktop Editor, you can select an object and edit its properties or attached script by:

*   Clicking on an object directly in the scene.

*   Clicking on an object in the Hierarchy panel window.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452908562_512532827951340_3391031282719828034_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=tZidnTPgUGwQ7kNvwEnDb4M&_nc_oc=AdlhNovX6i5mlLaR6Y6dlN0L7r7ppx4On9OQPWdVGPKaYXxF2b0sHeleGBXIVxT7So8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfQFGO0CAHT3rmUDjPpUwdmRBEb8jk4N8NQrsP2_Eq6zow&oe=689B8D62)

![](https://scontent.oculuscdn.com/v/t64.5771-25/75416836_1103563701114794_7392234213205777378_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=tSv_mgw9q9MQ7kNvwHE9xCn&_nc_oc=AdlsiyW-d413oa6uFo5l1KC6yyiBl3hFDr0SSiTaA7RRdwst-NGTIVSEUpUrfEqxvaw&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfTdXlp9YH3V5A6byUxWHQeNVLspLH1wiKImFiPyd3EsGA&oe=689BA4DE) **Note:** To redirect the view towards a specific object, select an object and press the “F” key.

## Selecting multiple objects

You can select multiple objects in the Hierarchy panel in the following ways:

*   Select an object, then hold the Ctrl key and click another object to add it to the selection. You may repeat this until all the desired objects are selected. You can also use this method to deselect individual objects.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915738_512532831284673_8889899307286045688_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=xywEgkCK-J4Q7kNvwEf3e_C&_nc_oc=Adkoxsrbwpz1QtvDqc2oIRthItMy7Gb6wryAFhPBiVBqqj804zrdyzO5Gnhf0AOoDSo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfR8IVBZ9I6O1nLYH00DApWyGhl-Dk_uSKtvMScjHmESzA&oe=689B8FD5)

*   Select an object, then hold the Shift key and click another object to select those objects and all objects in between them.

![](https://scontent.oculuscdn.com/v/t64.5771-25/38982529_1576236403284573_8965784620002181160_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=MYv26HQLCToQ7kNvwGPS89c&_nc_oc=AdkD_9jcSB9pRaQze5bkxfXetJOFLP2p4Fi21qudzraM8Z19vn_CgbNlP7ft7-qT8yM&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfRiYaN6ZZPYQ9EyW270uPgwehkKtdRySIhsSjef5o-G6g&oe=689B8F89) **NOTE:** You can also click individual objects in the scene while holding Shift or Ctrl to add or remove them from the current selection.

## Duplicate selected objects

After selecting an object, or multiple objects, in the hierarchy view you can duplicate it to create multiple instances of the same object. Duplicating your existing objects can help reduce the time needed to create things like multiple instances of an item or texture that needs to be repeated or reused.

To do so use the following process:

*   Select an object or objects in the hierarchy view.

*   Right click and select **Duplicate selection** from the pop-up menu. You can also use the keyboard shortcut **Ctrl + D**. 
    
    ![Duplicate object option in the hierarchy window view](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475996211_643175471553741_3194313167617336242_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=BpljZXmBwvcQ7kNvwGvsBoE&_nc_oc=AdliZ68bnB9lOIFVyJfXtWGIeBu_GEuiXuJ4L-cSOOISYaF6i1f1aPM3ajil8mwklK8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfREp7ZEXLd4iPDTEF4FsoUC6xRQwWvBhDdE281oIPG6Ag&oe=689BB763) 

*   Your selected objects, including any child objects, will appear in the hierarchy view.

## Sub-Object Selection

In the Desktop Editor, you can’t select a single sub-object of a group simply by clicking on it in the scene.

Sub-object selection is a feature for the Desktop Editor that lets you select sub-objects in the scene using a second click.

*   The first click selects the group.

*   The second click selects the sub-object that you clicked on. **NOTE**: Sub-object selection applies only to groups. For sub-objects in regular hierarchies, the first click still selects the sub-object. To select the parent object, you can simply select it directly.

### User flow

Use this procedure to try out sub-object selection.

*   In the Desktop Editor, travel to any world in Edit mode.

*   In the world, either create a new group of entities, or find an existing group.

*   Click on one of the objects in the group. The entire group is selected.

*   Click on the same object again. The sub-object is selected.

*   You can repeat this procedure again with nested groups.

## Selecting simulated objects and ghost visuals

While running a simulation, animated or physics objects (the objects that move) leave behind a ghost visual at their origin point.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453001795_512532771284679_6244440347639127473_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=-6vmC55UtrgQ7kNvwETHyTT&_nc_oc=AdnStLYOn4jHz6_FJ8d0xDi7KqXz8heQVmp-N7oCC98F0t6r6Ixgki0di3pJkohWl5I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfRtsslOQ7VUcpB-x_ueBz0LRIki06n8JQL_P4oSgnGWAw&oe=689B8E3A)

While the simulation is running, you can select the moving object either by clicking on the simulated object itself, or its ghost visual.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653115_512532804618009_5932082721550188701_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=EP3YBp3kn0MQ7kNvwFqXfFk&_nc_oc=AdmIAN-24kFsrSnFK7Fp2aYxhjpibdaooYZERvWP0khQZh_7j0RUfJTNqiWX1vq24X4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfSAl4lMnrlg01nANwIFpZMbIm2G8UqZqzui-fDZeHTmlg&oe=689B9630)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452635555_512532817951341_6397424954436022188_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=FfwVtrJh52cQ7kNvwGM0ghX&_nc_oc=Adkh90kidrBsBr1AWUZGLDwslIdZaHDNvSxzwu-4RNgIMkliUp8o7yoxjjUb-xKUZTw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfQH0NOLbwJLWSbGnY2WGstTo0imNpT-LIDFFhqHBO4ZKQ&oe=689BB2C0)

This works for both regular selection and marquee selection.

## Outline colors

*   **Selected**
    
     objects and gizmos are outlined in blue.

*   **Locked**
    
     objects and gizmos are outlined in red, both on mouse over and when selected.

![56b7a774-5178-4932-9458-82bb7b33895c.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453000787_512532807951342_3805190600803216520_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=5g1-RGFZAhYQ7kNvwHN8xHK&_nc_oc=AdmzFKBirESXt_HcDCrkHOXR4i0q4tywQPb59dZR-F9QxPTx2nlynG-SCI9nltndCjM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfQzR9LJaa0I002gfOez9BX8SFWVXAZPTh0yrrOiVxA_OA&oe=689B8E53)

## Focusing the camera on a selected entity

To focus the camera on a specific object or gizmo, select the object and press the “F” key. 

![](https://scontent.oculuscdn.com/v/t64.5771-25/39001711_555881607346476_6364462366655503089_n.gif?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=jZWH6Bis6EkQ7kNvwEG6gAq&_nc_oc=AdlyTLIWtNHaHtTqplki7a5RbzEPZXo3lQzpEyWE56uQIrD2_Za1PGswatVcmDTHXjA&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfRPvPjhTux9SFeTcIeuCJwwUfAN-5rDhuvROrZiPMMQhA&oe=689B8AF2)

## Grouped object behaviors

In grouped objects, when selecting a child object it selects the whole group.

![SelectionGif.gif](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452863001_512532794618010_116291496740666727_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=eaFXLF9XOq0Q7kNvwGf_Ls-&_nc_oc=Adm27H9xihmWCbUaTcSIb6pHr9l22H2_juXojAoduWQ7aD-XEa8O6ztuarxKV90kxq0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfT2mSkeD1G71zNr6XoJU1vlj-tb7Qe_7F_BpWvmH7Urxg&oe=689BADAC)

Locked entities can be selected in the viewport, but manipulators are disabled on locked entities.

![LockSelectionGif.gif](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452753851_512532824618007_1878177382760896463_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=o2jLom9FhS4Q7kNvwFMbQRg&_nc_oc=AdlPGS-NMhXDgmxIMR-ZR_plqm70VkxZb2tNA1M9DEEUpQtLBOaeHE9539NqiKcICZs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfR_j1EzyTveXPHOvLqjCcUyq31miKzpz5RMJ6Swx5UK-g&oe=689BBCB9)

Ghost visuals of a single mesh entity use the object’s mesh, but the ghost of a grouped object uses the group’s bounding box instead.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452635059_512532797951343_6323948175748851752_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=rXj0mfTbEaAQ7kNvwHuhc5t&_nc_oc=AdlFYUT89WqGvOISXG5bOvOPy5x-83TX59LafYrLwd5uMzSEWGiED3FQUIHYW8ZtHCM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfRJi3jDtn1isxdCvTZ5H1HiarEHDi4Tym5NRZV5tBe38Q&oe=689B92FA)

## Marquee selection

Marquee selection makes it easier to select multiple objects. It simplifies the selection process by allowing you to select more than one object by creating a box around the objects you want selected and highlighting them in blue.

#### How to use marquee selection

*   In the Desktop Editor, click and drag a selection box over the objects that you want to select.
    
    *   All non-locked and visible objects within the box become outlined in blue.
    
    *   Child objects not within the selection box but with parents that are within the selection box are outlined in white.
    
    *   Any object within the selection box and belonging to either a group or asset template instance will result in the entire group/asset template instance being outlined in blue. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452886151_512532757951347_636423381972171589_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=imtyShckfjAQ7kNvwEQElmU&_nc_oc=Adlxv4nmCQR-035Jxt3GF-FNyWUlHnle3MJOXL957NiVNVpK9Qd0AUXeDx7k3NZesEE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=lBP371NH4fN_aIFNvfBd0g&oh=00_AfSo02479cDq12h9GvYPNnMgcORt-8ZJ-1VTyfXCza7ptQ&oe=689B8625) 

*   When you unclick, the blue outlined objects within the box are selected.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)