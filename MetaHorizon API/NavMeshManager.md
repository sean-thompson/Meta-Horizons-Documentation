# NavMeshManager Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/navmesh_navmeshmanager)

Stores and retrieves references to [NavMesh](/horizon-worlds/reference/2.0.0/navmesh_navmesh) instances.

## Signature

```
export default class NavMeshManager
```

## Remarks [NavMesh](/horizon-worlds/reference/2.0.0/navmesh_navmesh) instances are cached to ensure that retrieving their profile multiple times with a script only generates one class reference. This is useful for updating navigation mesh profiles at runtime.

## Properties

<table>
  <tbody>
    <tr>
      <td>**getByName**</td>
      <td>Gets a reference to a instance based on a profile name.

Signature

```
getByName: (name: string) => Promise<NavMesh | null>;
```

Remarks

If no matching profile is found, returns `null`.</td>
    </tr>
    <tr>
      <td>**getNavMeshes**</td>
      <td>Gets a set of instances from the cache.

Signature

```
getNavMeshes: () => Promise<NavMesh[]>;
```</td>
    </tr>
    <tr>
      <td>**world**</td>
      <td>Signature

```
world: World;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| getInstance(world) static | Gets a NavMeshManager directory that stores the references to NavMesh instances.Signaturestatic getInstance(world: World): NavMeshManager;Parametersworld: WorldReturnsNavMeshManager |