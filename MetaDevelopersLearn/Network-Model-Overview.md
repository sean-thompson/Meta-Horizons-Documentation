# Network Model Overview

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/network-model)

In Meta Horizon Worlds, each virtual world uses a distributed client-server architecture where a server and multiple clients synchronize state changes across the network using an entity-component system (ECS). In this approach, each entity (object) in the world is owned by a client giving it authority to modify the entity and broadcast the updates to other clients on the network.

Entity ownership determines where code runs and what tasks are performed on a local client before state changes are synchronized with remote clients. Ownership is transferred between clients to lower latency, reduce consumption of computing resources, and reduce the amount of physics data synchronized over the network. When using scripts to update entities in real-time, you can set the execution mode to improve the latency of specific entities while they are owned by the local client.

## Server

The server for a world instance runs game logic and scripts by default, but doesn’t render the world or receive local input from a human player. The server also facilitates synchronization of state changes between clients.

## Clients

Clients are instances of Meta Horizon Worlds that run on the devices of human players. The devices include smartphones, tablets, PCs, and VR headsets. Clients render the world, receive user input, run local scripts, and synchronize data with other clients across the network.

All clients have a full scene graph, which is a collection of all entities, their attributes, and their relationships.

### Players

Meta Horizon Worlds is designed for multiplayer experiences where human players interact with each other, AI players, and numerous entities in the world. All human players are associated with a client and have an avatar that provides them with a physical presence in the world. Clients prioritize processing state changes that impact the local player while receiving the remaining data from remote clients. For example, a client doesn’t process [physics](#physics) for every entity in a scene; some of that data is processed on remote clients and then synchronized over the network.

## Synchronization

Network synchronization is performed on each client near the end of each frame. During synchronization, each client processes received network data and broadcasts updates from [network events](/horizon-worlds/reference/2.0.0/core_networkevent) to other clients.

Once network synchronization completes on a client, it renders the game world for the local player.

### Physics

The physics engine on each client focuses on simulating local entities and treats non-local entities as kinematic, so clients can synchronize the position and velocity of entities over the network without including detailed physics data. The server resynchronizes physics data periodically to prevent the movement of non-local entities from diverging from local physics simulations.

For more information, see the [Physics overview](physics) .

### Entity ownership

Entity ownership identifies the client that is the current authority for an entity’s state, as well as the potential to update the entity locally before broadcasting the change to other clients.

Only one client can own an entity at a time. When a new world instance starts ( [world.onUpdate](/horizon-worlds/learn/documentation/typescript/events/world-update-events) ), the server owns all entities; however, ownership of most entities is eventually transferred to clients. Ownership typically transfers to another client when a player grabs an entity, an entity collides with an entity owned by another client, or a script initiates the [transfer](/horizon-worlds/learn/documentation/typescript/local-scripting/ownership-in-horizon-worlds#ownership-transfer) . **Note**: For information about the lifecycle of scripts and components, see [TypeScript Script Lifecycle](/horizon-worlds/learn/documentation/typescript/typescript-script-lifecycle) .

By default, all scripts run on the server. If local execution mode is enabled on a script, the script can run on the client that owns the entity the script is attached to. This can improve latency for the local player making some actions in a world feel immediate because it can bypass two or more client-server interactions. However, running scripts locally limits their interaction with events and assets. For details, see [Getting Started with Local Scripting](/horizon-worlds/learn/documentation/typescript/local-scripting/getting-started-with-local-scripting) .

Here’s a comparison of the client server interactions needed for a client to update the state of an entity based on ownership:

*   A client modifies an entity owned by the server:
    
    *   The update is sent to the server
    
    *   The server applies the update
    
    *   The update is sent to all clients
    
    *   The clients apply the update

*   A client modifies an entity it owns:
    
    *   The owner applies the update at the end of the current frame
    
    *   The update is sent to the server
    
    *   The update is sent to the other clients
    
    *   The clients apply the update

*   A client modifies an entity owned by another device:
    
    *   The update is sent to the server
    
    *   The update is sent to the owner
    
    *   The owner applies the update
    
    *   The update is sent to the server
    
    *   The update is sent to other clients
    
    *   The other clients apply the update

For details about entity ownership, see [Ownership in Meta Horizon Worlds](/horizon-worlds/learn/documentation/typescript/local-scripting/ownership-in-horizon-worlds) .

## Performance considerations

The following recommendation can improve the network performance of your world.

*   Ownership optimization:
    
    *   You should run most scripts in default execution mode. However, for scripts that require lower latency, you should enable local execution mode. For details, see [Getting Started with Local Scripting](/horizon-worlds/learn/documentation/typescript/local-scripting/getting-started-with-local-scripting) .
        
    
    *   Use [local events](/horizon-worlds/learn/documentation/typescript/events/local-events) instead of [network events](/horizon-worlds/reference/2.0.0/core_networkevent) for updates that are only relevant and visible to the local player.
        
    
    *   Use [local execution mode for custom UI scripts](/horizon-worlds/learn/documentation/desktop-editor/custom-ui/local-mode-custom-ui-scripts) to avoid unecessary network calls in custom UIs.
        

*   Reducing the number of animations and entities in the world also reduces the amount of data synchronized between clients, which improves network performance.
    

*   Use [file backed scripts](/horizon-worlds/learn/documentation/typescript/filebacked-scripts) instead of [legacy script storage](/horizon-worlds/learn/documentation/typescript/legacy-script-storage) to reduce the delivery time of scripts across the network.
    

*   Measure performance:
    
    *   When capturing performance data, enable [server tracing options](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/tracing#tracing-options) so you can analyze world performance, network calls, and script updates.
        
    
    *   [Profile your UI](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/custom-ui-optimization)
        
         to analyze network RPC events associated with UI binding in custom UIs.
        

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 