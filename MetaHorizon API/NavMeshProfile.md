# NavMeshProfile type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/navmesh_navmeshprofile)

The configuration for a navigation [NavMesh.profile](/horizon-worlds/reference/2.0.0/navmesh_navmesh#profile) .

## Signature

```
export declare type NavMeshProfile = {
    typeId: number;
    name: string;
    color: string;
    agentRadius: number;
    agentMaxSlope: number;
    navMesh: INavMesh;
};
```

## References [INavMesh](/horizon-worlds/reference/2.0.0/navmesh_inavmesh) ## Remarks

Variables:

  

typeId: The Unique ID for this profile type (provided by the backend server).

  

name: The name of the profile entity in World Builder.

  

color: The color of the given profile as defined in World Builder.

  

agentRadius: The radius for the agent's navmesh calculations.

  

agentMaxSlope: The maximum angle on a slope the agent can traverse.

  

navMesh: The NavMesh the agent is running a calculation against.