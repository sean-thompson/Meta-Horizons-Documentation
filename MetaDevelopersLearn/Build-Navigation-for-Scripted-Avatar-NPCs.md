# Build Navigation for Scripted Avatar NPCs

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/scripted-avatar-npcs/build-navigation-for-scripted-avatar-npcs)

If your Scripted Avatar NPC is mobile in your world, you should create navigation for it and build TypeScript to use the navigation.

## To Build Navigation or Not

Although recommended, navigation objects are not required for Scripted Avatar NPCs. If you do not build navigation for your NPCs, any NPC attempts to move directly towards its destination. However, this can be complicated by the following:

*   More complex worlds are more difficult to navigate. NPCs may fail to reach destinations that appear navigable.

*   Your NPC may stride across a bubbling pool of lava. With navigation, you can build volumes to include and exclude from navigation. Otherwise, all surfaces are presumed to be navigable.

*   If objects enter in or fall in the world, they may need to be considered with the navigable spaces. Without navigation and rebaking of it, an NPC may fail to safely navigate around these kinds of hazards. **Tip**: Navigation is recommended for enabling Scripted Avatar NPCs to reach their destinations. If you have a simple flat world without complex features, you may be able to avoid deploying navigation.

## Scripted Avatar NPC Positioning

Locate your Scripted Avatar NPC in a position in the world that meets the following requirements:

*   Scripted Avatar NPC must be positioned on the surface of the world.

*   If you are using navigation the Scripted Avatar NPC must be within an included navigation volume assigned to its navigation profile.

## Navigation Entities

Navigation requires building the following entities:

*   Navigation profile(s). A **navigation profile** defines the characteristics of entities that use a set of one or more navigation volumes in the world.

*   Navigation volume(s). A **navigation volume** is a rectangular space in your world that can be included or excluded from a navigation profile. **Navigation profile for NPCs**:

Below are recommended settings with which to begin tuning your NPCs. **Note**: Retain the Name value. This value is passed as a string through a TypeScript API call to locate the profile to your NPC(s). **Note**: These settings are based on a scaling factor of `(1,1,1)` for the size of the avatar in the NPC gizmo. You may need to adjust them if you are using a different scaling.

![Navigation profile settings suitable for Scripted Avatar NPCs](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/469110335_603532525518036_7285455673456390638_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=zmw-qU-XF-4Q7kNvwHevYcr&_nc_oc=AdkWJwtmQKlETKIDgb-gtxl2Divqp7pFo4-VDDD9niqQ88oPXzBA2izGu_upah2hzsE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=hMDdHWk5ZVug8CYhen9Yvg&oh=00_AfQBDP5GeZ8WuxOD1RzhXdW8pqVg1V3q__HxqqVpUkqT_g&oe=689BB479)

For more information on creating navigation profiles and navigation meshes, see [Navigation mesh generation](/horizon-worlds/learn/documentation/desktop-editor/npcs/navigation-mesh-generation) .

## Navigation APIs for Scripted Avatar NPCs

After a navigation profile and its volumes have been defined, you can reference them from TypeScript to enable your NPC to use the navigation.

This section contains some simple examples for how to build the TypeScript to support navigation. **API docs**:

*   [AgentLomotion](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.agentlocomotion.md/?api_version=2.0.0)

*   [AgentLocomotionResult](https://horizon.meta.com/resources/scripting-api/avatar_ai_agent.agentlocomotionresult.md/?api_version=2.0.0)

### Create reference to navigation

After you have created a navigation profile for your Scripted Avatar NPC to use, you must use it to generate a profile for your NPCs to use.

The following example creates reference objects for the navigation associated with the named navigation profile: `NPCs`.

```
private navMesh!: NavMesh;

start() {
    // Get reference to nav profile and assign to constant "navMesh"
   const navMeshManager = NavMeshManager.getInstance(this.world);
    const navMesh = await navMeshManager.getByName("NPCs");
    if (navMesh == null) {
      console.error("Could not find navMesh: NPCs");
      return;
    };
    this.navMesh = navMesh;

    // Get status of navigation mesh baking. Wait until complete.
    const bake = this.navMesh.getStatus().currentBake;
    if (bake != null) {
      await bake;
    };
};
```

When the world is initialized, navigation meshes must be **baked**, which turns the entity information into runtime data that NPC entities can use for navigation. This process is typically quick to complete and can be executed during runtime without interruption. However, at world startup, it may be competing with other processes for resources and may take a bit longer to finish.

After the bake of the `navMesh` object associated with the `NPCs` profile is completed, the `navMesh` is ready for use with the Scripted Avatar NPC APIs.

The next steps involve:

*   Assigning the NPC gizmo entity to be referenced as a type of `AvatarAIAgent`.

*   Applying one or more waypoints to the `moveToPosition()` and `moveToPositions()` methods for the entity to move to those locations.

These methods are covered in the following sections.

### Get path

You can use the following function to get a set of waypoint paths from a `from` location to a `to` location, using the referenced `navMesh` object that you baked:

```
public getPathTo(from : hz.Vec3, to : hz.Vec3) : Array<hz.Vec3> {
    let nextPath: NavMeshPath | null;

    let getPathAttempts: number = 0;
    do {
      nextPath = this.manager.navMesh.getPath(from, to);
      getPathAttempts++;
    } while (nextPath == null && getPathAttempts < 20);
    if (nextPath == null) {
      console.warn("Couldn't find any valid paths from ", from.toString(), " to ", to.toString());
      return new Array<hz.Vec3>();
    } ;
    if(!nextPath.pathReachesDestination) {
      console.warn("Path incomplete");
    };
    console.log("Path size: " +  nextPath.waypoints.length + " from ", from.toString(), " to ", to.toString(), " dest " + nextPath.waypoints[nextPath.waypoints.length - 1].toString());
    return nextPath.waypoints;
  };
```

If it is successful, the `getPathTo()` function returns an array of `hz.Vec3` waypoints between `from` and `to` Vec3 positions, derived from the `nextPath.waypoints` object.

This array can be fed into the `moveToPositions()` function. Alternatively, if you may need to perform other actions during the process or potentially interrupt at a waypoint, you may choose to iterate through the array, feeding individual waypoints to `moveToPosition()` in sequential order.

### Movement Properties

You can query the NPC entity to return current values of its movement status. **Example**:

```
let npcTarget: hz.Vec3 = this.props.npc!
  .as(AvatarAIAgent)
  .locomotion.targetPosition.get();
``` **Properties**:

| Property | Description |
| --- | --- |
| targetPosition.get() | Returns the current target Vec3 position of the agent. Undefined if it is not moving. |
| targetDirection.get() | Returns the current target Vec3 rotation of the agent. Undefined if it is not rotating to a target. |
| isMoving.get() | Returns true if the agent is in motion. |
| isGrounded.get() | Returns true if the agent is on the ground. |
| isJumping.get() | Returns true if the agent is currently jumping. |

### MoveToPosition API

The basic movement API is to `moveToPosition()` method, which returns a Promise that can be evaluated for success or failure. **Example**:

The following basic example executes a `moveToPosition()` call and ignores the result.

```
this.entity.as(AvatarAIAgent).locomotion.moveToPosition((3,2,1))
``` **Example with a Promise**:

The above methods returns a Promise of type `AgentLocomotionResult`, an enum with the following values:

| Value | Description |
| --- | --- |
| 0 | Complete |
| 1 | Canceled |
| 2 | Error |

```
this.entity.as(AvatarAIAgent).locomotion.moveToPosition((3,2,1)).then((locomotionResult) => {
  switch (spawnResult) {
    case AgentLocomotionResult.Complete:
      console.log("Movement complete!");
      break;
    case AgentLocomotionResult.Canceled:
      console.log("Movement was canceled.");
      break;
    case AgentSpawnResult.Error:
      console.error("Uh-oh! An error occurred while moving.");
      break;
  };
});
```

### Waypoint navigation

The `moveToPositions` method accepts an array of Vec3 values. This array is a sequence of waypoints through which the Scripted Avatar NPC moves. **Example 1**:

The following script assigns a set of waypoints to an array, which is passed into the `moveToPositions()` method. The `AgentMovementOptions` object is defined to include a movement speed of `5`.

```
import * as hz from 'horizon/core';
import { AgentLocomotionOptions, AvatarAIAgent } from 'horizon/avatar_ai_agent';


class testScript02 extends hz.Component<typeof testScript02> {


  static propsDefinition = {
    npc: { type: hz.PropTypes.Entity },
    waypoint1: { type: hz.PropTypes.Vec3 },
    waypoint2: { type: hz.PropTypes.Vec3 },
    waypoint3: { type: hz.PropTypes.Vec3 },
  };


  start() {
    console.log("testScript02: Running start().");


    let arrWaypoints: hz.Vec3[] = new Array<hz.Vec3>();


    // sets movement options for movement between waypoints
    let movementOptions: AgentLocomotionOptions = {
      movementSpeed: 5,
    };

    if (this.props.npc) {
      if (this.props.waypoint1) {
        arrWaypoints.push(this.props.waypoint1);
          if (this.props.waypoint2) {
            arrWaypoints.push(this.props.waypoint2);;
            if (this.props.waypoint3) {
              arrWaypoints.push(this.props.waypoint3);
            };
          };
      };


      let npcGizmo = this.props.npc.as(AvatarAIAgent);
      if (arrWaypoints[0]!= null ) {
        npcGizmo.locomotion.moveToPositions(arrWaypoints, movementOptions);
        } else {
        console.error("No waypoints defined!");
      };
    } else {
      console.error("No NPC defined!");
    };
  };
};
hz.Component.register(testScript02);
``` **Example 2**:

This more robust example defines its set of waypoints as a series of Trigger Zones that are chained together through script properties. Trigger0 contains a reference to Trigger1, the position of which is passed to the `moveToPosition()` method when Trigger0 has been entered by the specified Scripted Avatar NPC entity. **Tip**: This approach is helpful for defining the NPC’s path as a set of physical entities in the world. `moveToPositions()` works when the waypoints are a set of known coordinates.

```
import * as hz from "horizon/core";
import { AvatarAIAgent } from "horizon/avatar_ai_agent";


export class TriggerZone extends hz.Component<typeof TriggerZone> {
  static propsDefinition = {
    zoneName: { type: hz.PropTypes.String },
    display: { type: hz.PropTypes.Entity },
    npc: { type: hz.PropTypes.Entity },
  };


  static triggerEnteredEvent = new hz.NetworkEvent<{
    player: hz.Player;
    entered: boolean;
    zoneName: string;
  }>("triggerEnteredEvent");


  start() {
    this.connectCodeBlockEvent(
      this.entity,
      hz.CodeBlockEvents.OnPlayerEnterTrigger,
      (player) => {
        this.sendNetworkBroadcastEvent(TriggerZone.triggerEnteredEvent, {
          player,
          entered: true,
          zoneName: this.props.zoneName,
        });
        this.props.npc
          .as(AvatarAIAgent)
          .locomotion.moveToPosition(hz.Vec3.zero)
          .then((result) => console.log("move to position result: " + result));
      };
    );


    this.connectCodeBlockEvent(
      this.entity,
      hz.CodeBlockEvents.OnPlayerExitTrigger,
      (player) => {
        this.sendNetworkBroadcastEvent(TriggerZone.triggerEnteredEvent, {
          player,
          entered: false,
          zoneName: this.props.zoneName,
        });
      };
    );


    if (this.props.display.exists()) {
      this.props.display.as(hz.TextGizmo).text.set(this.props.zoneName);
    };
  };
};
hz.Component.register(TriggerZone);
```

## Rebake

At runtime, the navigable surfaces available to a navigation profile may change. For example, gameplay may result in a pile of rocks tumbling across a navigable surface. In this case, you must rebake the world’s navigation to include these objects.

For more information, see [Navigation mesh generation](/horizon-worlds/learn/documentation/desktop-editor/npcs/navigation-mesh-generation) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 