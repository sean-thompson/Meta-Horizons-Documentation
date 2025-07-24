# World Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_world)

Represents a virtual world in Meta Horizon Worlds, which provides access to properties, events, and operations related to the world state; including events scripts can use to time operations based on state changes to the world.

## Signature

```
export declare class World
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**id**</td>
      <td>Returns the current world ID.

Signature

```
id: ReadableHorizonProperty<bigint>;
```</td>
    </tr>
    <tr>
      <td>**leaderboards**</td>
      <td>The leaderboards for the players in the world.

Signature

```
leaderboards: ILeaderboards;
```</td>
    </tr>
    <tr>
      <td>**matchmaking**</td>
      <td>The matchmaking system for queueing players into the world.

Signature

```
matchmaking: {
        allowPlayerJoin(allow: boolean): Promise<void>;
    };
```

Remarks `allowPlayerJoin` \- Indicates whether players can join the world.</td>
    </tr>
    <tr>
      <td>**name**</td>
      <td>The human-readable name of the world.

Signature

```
name: ReadableHorizonProperty<string>;
```</td>
    </tr>
    <tr>
      <td>**onPrePhysicsUpdate**

static

  

\[readonly\]</td>
      <td>An event that broadcasts on every rendered frame before the physics engine updates the world state. This event is especially useful for timing animations and entity locations before physics calculations are performed.

Signature

```
static readonly onPrePhysicsUpdate: LocalEvent<{
        deltaTime: number;
    }>;
```

Remarks

The [World.onPrePhysicsUpdate](/horizon-worlds/reference/2.0.0/core_world#onprephysicsupdate) event provides similar functionality, but after the physics engine performs calculations.

  

For more information about subscribing to world update events, see the [World Update Events](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/events/world-update-events) guide.</td>
    </tr>
    <tr>
      <td>**onUpdate**

static

  

\[readonly\]</td>
      <td>An event that broadcasts on every rendered frame in the world, allowing synchronization between the state of the world and the rendering pipeline. You can use this event to time animations, physics, and entity transforms for optimal performance.

Signature

```
static readonly onUpdate: LocalEvent<{
        deltaTime: number;
    }>;
```

Remarks

By subscribing to this event, a script can perform operations during the world update loop, such as [spawning an asset](/horizon-worlds/reference/2.0.0/core_world#spawnasset) .

  

The [World.onPrePhysicsUpdate](/horizon-worlds/reference/2.0.0/core_world#onprephysicsupdate) event provides similar functionality, but before the physics engine performs calculations.

  

For more information about subscribing to world update events, see the [World Update Events](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/events/world-update-events) guide.</td>
    </tr>
    <tr>
      <td>**persistentStorage**</td>
      <td>A persistent storage object, which contains a set of functions that interact with player variables.

  

For information about using player variables, see the [Persistent Variables](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/object-type-persistent-variables) guide.

Signature

```
persistentStorage: IPersistentStorage;
```</td>
    </tr>
    <tr>
      <td>**persistentStorageWorld**</td>
      <td>A persistent storage object, which contains a set of functions that interact with player variables.

Signature

```
persistentStorageWorld: IPersistentStorageWorld;
```</td>
    </tr>
    <tr>
      <td>**team**</td>
      <td>Basic functions for teams based gameplay.

Signature

```
team: ITeam;
```

Remarks

In horizon, every world comes with a team management logic. Players, at any moment during their session, can join, leave or change teams at will. But a player can only be in one team of a given team group.

  

Team groups are ways to separate teams in different sets. This allows the creation of multiple gameplay bubbles with their own teams in one single world.</td>
    </tr>
    <tr>
      <td>**ui**</td>
      <td>Basic UI functions for displaying popups and tooltips.

Signature

```
ui: IUI;
```

Remarks

For an example, see the [Lobby tutorial](https://developers.meta.com/horizon-worlds/learn/documentation/tutorials/multiplayer-lobby-tutorial/module-4-starting-the-game#display-a-countdown-timer) .</td>
    </tr>
  </tbody>
</table>

## Methods

| deleteAsset(entity, fullDelete) | Removes a previously spawned asset from the world.SignaturedeleteAsset(entity: Entity, fullDelete?: boolean): Promise<undefined>;Parametersentity: EntityThe previously spawned entity.fullDelete: boolean(Optional) if true, the entity must be the root object, thus deleting all sub-objects.ReturnsPromise<undefined>A promise that resolves when the entity has been deleted. |
| getEntitiesWithTags(tags, matchOperation) | Gets all world entities containing the provided tags using the provided match operation.SignaturegetEntitiesWithTags(tags: string[], matchOperation?: EntityTagMatchOperation): Entity[];Parameterstags: string[]An array of tag names to match against. The comparison is case sensitive.matchOperation: EntityTagMatchOperation(Optional) The match operation to run when searching for entities with given tags. Defaults to EntityTagMatchOperation.HasAnyExact.ReturnsEntity[]An array of all of the entities matching the tags and operation.ExamplesentityA.tags.set(['tag1', 'tag2', 'tag3']); entityB.tags.set(['tag2', 'tag3', 'tag4']); entitiesWithAnytags = this.world.getEntitiesWithTags(['tag1', 'tag2'], EntityTagMatchOperation.MatchAny); // returns entityA & entityB entitiesWithAlltags = this.world.getEntitiesWithTags(['tag3', 'tag4'], EntityTagMatchOperation.MatchAll); // returns entityBRemarksThis is an expensive operation and should be used carefully. |
| getLocalPlayer() | Gets the player corresponding to the local Meta Horizon Worlds client running on the player's machine where this script is currently executing.SignaturegetLocalPlayer(): Player;ReturnsPlayerThe local player.RemarksThis is particularly useful for Local Scripting to figure out which player's machine a local script is executing on. Note that if the local script is executing on the server, this will return the server player. |
| getPlayerFromIndex(playerIndex) | Gets the Player object for the given player index.SignaturegetPlayerFromIndex(playerIndex: number): Player \| null;ParametersplayerIndex: numberThe index of the player. Retrievable with the Player.index property.ReturnsPlayer \| nullThe player corresponding to that index, or null if no player exists at the index. |
| getPlayers() | Gets all players currently in the world, not including the server player.SignaturegetPlayers(): Player[];ReturnsPlayer[]An array of Player objects in the world. |
| getServerPlayer() | Gets the player corresponding to the server's Meta Horizon Worlds client.SignaturegetServerPlayer(): Player;ReturnsPlayerThe server player.RemarksThis is particularly useful for Local Scripting to figure out if a script is executing on some client other than the server. Note that a server player is not physically present in the world and does not support a number of standard features (such as name.get() or being moved) that normal players do. |
| reset() | Resets the world's state. This sets all entities back to their initial position, cancels all event and event listeners, and restarts scripts in the world.Signaturereset(): void;Returnsvoid |
| spawnAsset(asset, position, rotation, scale) | Asynchronously spawns an asset.SignaturespawnAsset(asset: Asset, position: Vec3, rotation?: Quaternion, scale?: Vec3): Promise<Entity[]>;Parametersasset: AssetThe asset to spawn.position: Vec3The position where the asset is spawned.rotation: Quaternion(Optional) The rotation of the spawned asset. If invalid, is replace with Quaternion.one (no rotation).scale: Vec3(Optional) The scale of the spawned asset.ReturnsPromise<Entity[]>A promise resolving to all of the root entities within the asset. |
| toString() | Creates a string representation of the World object.SignaturetoString(): string;ReturnsstringA string representation of the World object. |
| update(updateType, deltaTime) | Called on every frame.Signatureupdate(updateType: WorldUpdateType, deltaTime: number): undefined;ParametersupdateType: WorldUpdateTypeThe type of update.deltaTime: numberThe duration, in seconds, since the last frame.Returnsundefined |