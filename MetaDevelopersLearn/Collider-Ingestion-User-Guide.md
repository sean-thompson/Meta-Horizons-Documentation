# Collider Ingestion User Guide

[source](https://developers.meta.com/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/collider-ingestion-user-guide)

Collider ingestion allows asset creators to define custom collision shapes in the FBX file for a mesh asset. When these colliders are ingested into Horizon they become collider entities, these are a new type of entity in Horizon that is only used for collision.

Collider entities have collision, physics, and grabbable components but no renderable mesh component. Collider entities can be ingested with mesh assets or spawned directly from the Creator User Interface (CUI). By grouping collider entities with mesh entities, creators are able to create visually complex objects with performant collision. These collider entities are viewable with the collision debug view but otherwise be invisible.

## Types of collider entities

Collider entities can either be primitives (box, sphere, capsule) or meshes. Primitives have significant performance advantages, but mesh colliders allow for more precise collision.

| Type | Source | Description |
| --- | --- | --- |
| Box | CUI or Ingested | Primitive box collider. Uses Unity’s BoxCollider component. |
| Sphere | CUI or Ingested | Primitive sphere collider. Uses Unity’s SphereCollider component. |
| Capsule | CUI or Ingested | Primitive capsule collider. Uses Unity’s CapsuleCollider component. |
| Mesh | Ingested Only | A mesh ingested from an asset. Uses Unity’s MeshCollider component. Can represent a convex hull or a concave mesh. |

## Ingesting collider entities

When importing 3D models made in a DCC tool (Digital Content Creation) into horizon we provide a way for creators to designate a custom collider setup. Mesh names saved out from the DCC tool define which meshes represent colliders and what type of colliders they are.

The colliders should be attached to the visible geometry in the DCC tool, so they’re grouped together when spawned in Horizon.

This same mesh name-based custom collider approach is used by Unreal, Houdini, and Unity (via plugin).

| Type | Mesh Prefix Naming | Requirements |
| --- | --- | --- |
| Box | UBX_[VisibleMesh]_## | A Box must be created using a regular rectangular 3D object. You cannot move the vertices around or deform it in any way to make it something other than a rectangular prism, or else it will not work. |
| Sphere | USP_[VisibleMesh]_## | A Sphere does not need to have many segments (8 is a good number) at all because it is converted into a true sphere for collision. Like boxes, you should not move the individual vertices around. |
| Capsule | UCP_[VisibleMesh]_## | A Capsule must be a cylindrical object capped with hemispheres. The capsule is expected to be vertical in local space. It does not need to have many segments (8 is a good number) at all because it is converted into a true capsule for collision. Like boxes, you should not move the individual vertices around. |
| Convex Hull | UCX_[VisibleMesh]_## | A Convex object can be any completely closed convex 3D shape. |
| Concave Mesh | UCC_[VisibleMesh]_## | Any concave mesh. This is the most flexible type of collider but is also the least performant. Unity will generate a convex hull if it is marked as dynamic. |

The geometry for primitive colliders (box, sphere, capsule) is expected to have its pivot at the center. This restriction does not apply to convex or concave mesh colliders.

This screenshot from Blender shows a visible mesh (RingTarget) with a number of primitive colliders defined for it.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652340_512500407954582_5623056193016771241_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=1336Pr0QtPQQ7kNvwFKU7ep&_nc_oc=Adk64mRbDhDYNiZiTaQd61dnuaSSV2cclwpVOh5mXKRPabYytpXfP_ois4BrMiv5v2s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=rYg8bylXgz2czAylLlrySw&oh=00_AfQg-ZMp7vqWg_VCbsyEqZX_tBnJtwEi68ipJgIbWkHjCQ&oe=689BBAEB)

## Spawning collider entities in the desktop editor

Collider entities are also available for World Creators in the desktop editor. Spawning them is similar to spawning a primitive shape, but there will be no visible geometry. Only primitive colliders (box, sphere, capsule) are available from the desktop editor. Collider entities can be grouped with visible meshes to define custom collision for those meshes, or used on their own to add collision volumes to the world.

To add a primitive collider to the world, select **Colliders** from the **Build** menu. This will open the **Colliders** panel. Select the type of collider you want to add to the world, then right-click and select **Place**.

|  |  |
| Collider option in the Build menu | Colliders panel |

We automatically enter Colliders view mode when you place a collider entity into the world. To enter collider view manually, select **Collisions** from the **View Mode** menu at the top right of the **Preview** window.

![Collider view option](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/514025692_754517587086195_4881851379016605796_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=saG2Gz6Z1l8Q7kNvwFiet5F&_nc_oc=AdnlCZXqd19Nqj-uu8pZ9yoBpgoHqZBLC77RTloYB8KaCkISyhn588syboltu4EA9QA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=rYg8bylXgz2czAylLlrySw&oh=00_AfRTDx1VPtCzLJBCFvyIXDsGkq6pQkRdWMwvj_HsRu8GNQ&oe=689BB05F)

*Collider view option*

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 