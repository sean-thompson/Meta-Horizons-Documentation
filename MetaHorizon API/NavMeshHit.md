# NavMeshHit type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/navmesh_navmeshhit)

The collision data returned when a raycast is performed on a [NavMesh](/horizon-worlds/reference/2.0.0/navmesh_navmesh) object by the method.

## Signature

```
export declare type NavMeshHit = {
    position: Vec3;
    normal: Vec3;
    distance: number;
    hit: boolean;
    navMesh: INavMesh;
};
```

## References [INavMesh](/horizon-worlds/reference/2.0.0/navmesh_inavmesh) ## Remarks

Variables:

  

position: The ending location where the raycast collided with the NavMesh.

  

normal: The normal vector at the point of impact for the raycast.

  

distance: The distance traveled when the raycast was performed.

  

hit: true if the raycast hit any obstructions or edges during the calculation; otherwise, false.

  

navMesh: The NavMesh the raycast was performed on.

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)