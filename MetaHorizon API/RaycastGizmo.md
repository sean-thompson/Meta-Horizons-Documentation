# RaycastGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_raycastgizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a Raycast gizmo in the world.

## Signature

```
export declare class RaycastGizmo extends Entity
```

## Remarks

A Raycast gizmo projects an invisible beam into a world to return information about any objects it collides with.

## Methods

<table>
  <tbody>
    <tr>
      <td>**raycast(origin, direction, options)**</td>
      <td>Casts a ray from the Raycast gizmo using the given origin and direction and then retrieves collision information.

Signature

```
raycast(origin: Vec3, direction: Vec3, options?: RaycastOptions): RaycastHit | null;
```

Parameters

origin: [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) The starting point of the ray.

direction: [Vec3](/horizon-worlds/reference/2.0.0/core_vec3) The direction for the ray to travel.

options: [RaycastOptions](/horizon-worlds/reference/2.0.0/core_raycastoptions) *(Optional)*

 The options for configuring the raycast operation.

Returns [RaycastHit](/horizon-worlds/reference/2.0.0/core_raycasthit) | null

The collision information.</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the RaycastGizmo.

Signature

```
toString(): string;
```

Returns

string

A string representation of the RaycastGizmo.</td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)