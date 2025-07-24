# Object hierarchy and groups

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/objects/object-grouping)

The Meta Horizon Worlds desktop editor provides you with the ability to combine objects so you can select, move, rotate, or scale objects as a single unit. This is achieved through defining object relationships that allow you to set behaviors, such as [collidable](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/physics-best-practices#collidable-objects) , for all the child objects of the same parent. Additionally, creating nested [parent-child relationships](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview#features) between objects improves world organization, and object manipulation and management. **Note**: While creating parent-child relationships between objects, pay attention to the location of the [pivot point](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview#pivot-around-parent-objects) that defines your rotations and scale transformations.

## Create a parent-child hierarchy between objects

While it’s not necessary to designate an existing object in the scene as the parent of a group, any [object in the hierarchy view](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview#parent-anything-to-anything) can be dragged and dropped onto any other object to create a parent-child relationship. Alternatively, you can create an intangible [empty object](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview#empty-objects) as the parent for one or more children. The following steps demonstrates how an empty object is created to be the parent of selected objects.

*   Press Ctrl + Click or Shift + Click to select multiple objects.
    
    ![Create a hierarchy](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/486620414_681803087690979_4488656560382183237_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=phCAmtVN8bYQ7kNvwGrRkfA&_nc_oc=AdnXGn4JZYsMiJBXymfCYtFBjbFx2ZrRmukV0i1hxBqbF0U_LHvHIuJmpPrqCvsw2Mc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=AnqWoAu0TktRP-aVcAIJvg&oh=00_AfThIMOTS9ppH8hw3Qsuattvxu2clBxneZvV2UNlVSPzZw&oe=689BBD02)
    

*   Create an empty object to be the parent of the selected objects:
    
    Press Ctrl + G on your keyboard, or right click to select **Create parent object** from the context menu.
    

## Add an object to an existing hierarchy

*   Select the object you want to add to an existing hierarchy.
    

*   Click and drag the object to the hierarchy.
    
    In the following image, the **Sound Recorder** is dragged to the **Empty Object** hierarchy.
    
    ![The object is added to the chosen hierarchy](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/486610726_681803084357646_8044919782849029886_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZGrtM2RNhI4Q7kNvwHjIuLP&_nc_oc=AdnzZS7fxlAhBacQpaE8TMzRXYz9_R5UsYU4ilq596yEXakS1goO3U628enCOC0mwc0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=AnqWoAu0TktRP-aVcAIJvg&oh=00_AfRahDksuSRGObY6II_vMVXXpZzAU0TMaQPGgU2yk3FrrA&oe=689B943A)
    

## Remove objects from a hierarchy

*   Objects can be removed from hierarchies using the same drag-and-drop method as described above.
    
    You can also right-click the object you’d like to remove from the hierarchy and select **Unparent selection**.
    

## Unparent all objects in a hierarchy

*   Select the parent object of the hierarchy.
    

*   Right-click the parent object to click **Unparent child objects**.
    

*   All child objects are removed from the hierarchy, and the parent object remains.
    

## Additional object organizations

The four procedures explained above can be combined to create additional object organizations such as the following:

*   Add multiple objects to an existing group.

*   Remove multiple objects from an existing group.

*   Move objects from one group to another group.

*   Nest groups.

*   Add or remove objects from nested groups.

*   Move objects from a nested group to a higher level group.

*   Undo or Redo your last operation.

## What’s next?

Learn more about the concepts of object hierarchy and pivot around parent objects in [Hierarchy panel overview](/horizon-worlds/learn/documentation/desktop-editor/hierarchy-window/hierarchy-window-overview) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 