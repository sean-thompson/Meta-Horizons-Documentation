# Introduction to Asset Spawning

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/asset-spawning/introduction-to-asset-spawning)

Asset spawning and despawning allows creators to instantiate and destroy objects at runtime. It does this through scripts powered by CodeBlocks and TypeScript. When objects are tied to Assets pulled from the creator’s Asset Library, it enables objects to be spawned so users can interact with them to perform in-world actions.

## Considerations

Before deciding to add object spawning to a world, there are a few questions you’ll want to answer to determine if object spawning and despawning benefits or detracts from your world’s experience. Spawning and despawning has a performance cost at runtime, especially when objects are spawned in quick succession. Consider the following:

*   How often will objects need to be created or removed for the experience?

*   How many object variations does the world require?

*   Do certain objects need to persist for the entire world experience? **Note:** See the Optimization Tips near the end of this document for information on improving performance.

## Implementing SpawnController

The SpawnController object is a container for managing the spawning and despawning of assets. You create a SpawnController object to contain a specified asset, including position, rotation, and scale:

```
// Controls the asset spawn
spawnController!: SpawnController;

this.spawnController = new SpawnController(
  myAsset,
  myPosition,
  myRotation,
  Vec3.one
  );
```

The SpawnController contains:

*   The asset you’d like to spawn (myAsset)

*   The position for the spawned object as a Vec3 (myPosition)

*   The rotation for the spawned object as a Quaternion (myRotation)

*   The scale of the spawned object as a Vec3 (Vec3.one)

A full example is listed below.

After the SpawnController has been defined for the asset, the following methods can be applied on the object:

| Method | Description |
| --- | --- |
| load() | Loads the asset specified in the SpawnController object into runtime memory. |
| spawn() | Spawns the asset from runtime memory into the location specified when you created the SpawnController object. If the load() method has not been called yet, it is automatically called before spawn(). The combined call to load() and spawn() is much longer than just calling spawn() by itself. |
| unload() | Unloads the SpawnController entity from the world. A reference to the spawn entity remains. The spawn entity can be reused by calling again the load() method. |
| dispose() | Destroys the SpawnController object. |

### Performance notes

The load() method performs 0.5 ms/frame of spawning work, while spawn() performs 5 ms/frame of spawning work.

If load() finished before calling spawn(), then the spawn() call has almost nothing left to do. To finish the spawning, the spawn() method enables and makes visible the entity at the specified location in a single frame and waits for lighting of the entity to begin.

## Asset Spawning and Despawning Example

The following TypeScript example demonstrates how to spawn and despawn a wall when the player steps on a trigger. The code:

*   Creates the asset variable `wallAsset` in the script.

*   Declares two CodeBlockEvents: one to trigger spawning, and the other to trigger despawning.

*   Creates a `SpawnController` to control the spawning of the asset.

*   Uses the `SpawnController.spawn` function to spawn the asset once the trigger is activated.

*   Uses the `SpawnController.unload` function to delete the asset when the despawn trigger is received.

```
// Official documentation on TypeScript can be found here:
// https://www.typescriptlang.org/docs/handbook/typescript-from-scratch.html

import { Component, PropTypes, CodeBlockEvent, SpawnController, Vec3 } from 'horizon/core';

const spawnTriggerEvent = new CodeBlockEvent<[]>('spawnEvent', []); // Will spawn asset.
const despawnTriggerEvent = new CodeBlockEvent<[]>('despawnEvent', []); // Will despawn asset.

class SimpleSpawn extends Component<typeof SimpleSpawn> {
 // Define the inputs available in the property panel
 // in the UI as well as default values.

  static propsDefinition = {
    wallAsset: { type: PropTypes.Asset },
  };

  // Controls the asset spawn
  spawnController!: SpawnController;

  // Called on world start.
  start() {
    this.spawnController = new SpawnController(this.props.wallAsset!, this.entity.position.get(), this.entity.rotation.get(), Vec3.one);

    // Handle when the user steps on trigger.
    this.connectCodeBlockEvent(this.entity, spawnTriggerEvent, () => {
      this.spawnController.spawn();
    });

    // Handle when the user steps off  trigger.
    this.connectCodeBlockEvent(this.entity, despawnTriggerEvent, () => {
      this.spawnController.unload();
    });
  }
}

// Tells the UI that your component can be attached to an entity.
Component.register(SimpleSpawn);
```

## Asset Spawning in VR

You can also use CodeBlocks with a Trigger gizmo to trigger the asset spawning script:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452578226_512510381286918_2130091807967526852_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=e060ZQAiVtkQ7kNvwEnUmf0&_nc_oc=AdmtHSC5B1AKefaelCQM00CMuGEgjfpR1bjYH1i9HvWE_IxR49-gjtZV1YCBWz8nt8I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=0TpiJ-HH3uJeYGPHc8ouCA&oh=00_AfS_2nRTDedajuU9s5RAXRYj_6JpZ2-M39Td3QQoFqAe_g&oe=689BA07C)

*   Create a trigger CodeBlock script to send the spawn and despawn events to an object. These scripts can be different for the spawn and despawn, but in this case we keep them together since they will be tied to the same trigger. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452514526_512510377953585_8446492638471105033_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=IFgr9FhXtd8Q7kNvwEw4MzB&_nc_oc=Adnzw_LA7XgfY3QWs4HK5eIDPNr3DAv-3TTrAmKYo-LIk5UpFEr1iXBerqDzPc2eq3c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=0TpiJ-HH3uJeYGPHc8ouCA&oh=00_AfTGPSSN9TRBvCZp7I1EyRFWiCAz0CgG4jpa2hqQjBHtqQ&oe=689B9B73) 

*   Create a Trigger gizmo and attach the CodeBlock script to the trigger. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452702326_512510374620252_2897307560533346680_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=tkWHRpb70HQQ7kNvwFsSA-s&_nc_oc=AdmR-PAImZ_F8D-6SOAUt8ggTBuXb9fwMavzoF8tO13ORuLr37NEwv9zvePVphKD28M&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=0TpiJ-HH3uJeYGPHc8ouCA&oh=00_AfROEOVpj9-lAK_dA1sfv8JKgmAwim9RMm8S2FQG_Ar0YA&oe=689B9196) 

*   Create an object and attach the TypeScript script to it. Depending on the application, it might be a good idea to make this object invisible.
    

*   Attach the asset you would like to spawn in the asset field that appears when you attach the script. This is done with the following steps:
    
    *   Navigate to your asset library from the build menu, then to the asset you want to spawn.
    
    *   Select the view info (“i”) icon on that asset.
    
    *   On the property panel, scroll down to see the asset reference pill (a blue oval containing the asset name).
    
    *   Select and drag this reference pill to the Asset Variable field “empty” on the object’s property panel. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/453003138_512510371286919_5172008865838978843_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=jU2hrbKyNVUQ7kNvwHPLW0v&_nc_oc=AdmIbo-uFVcdS1XWkTQ-qP6UnY3DGRhOO3bs_PNZWQfOlbm5G46vylCuVTMCD2iTZHA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=0TpiJ-HH3uJeYGPHc8ouCA&oh=00_AfRBf3QbQCgue9UOXY8APLlV4WJOeq1Zbr08oIVJsKs0UQ&oe=689BC048) 

*   Finally, attach this script object to the Trigger gizmo.

Once you are done, you should have a CodeBlock script attached to a Trigger gizmo which in turn is attached to an object. The object should have the TypeScript script attached to it as well as the asset to be spawned and despawned.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452746658_512510367953586_6703341356671159163_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=3zHMNjJ15z0Q7kNvwETRwQH&_nc_oc=AdmuQrVCR7uhfSvs4PwLZT2ZcRfMvhKZf38r0GD3DvjcZSdFA67Jj7f7MklRfrZdGig&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=0TpiJ-HH3uJeYGPHc8ouCA&oh=00_AfQvDu-lWOCtM7rCsCxTfg4WaCNG8dqgL9_PDxkX4ESQHg&oe=689B951B)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 