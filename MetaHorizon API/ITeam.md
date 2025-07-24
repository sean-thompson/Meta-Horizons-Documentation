# ITeam Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_iteam)

Basic functions for teams based gameplay.

## Signature

```
export interface ITeam
```

## Remarks

In horizon, every world comes with a team management logic. Players, at any moment during their session, can join, leave or change teams at will. But a player can only be in one team of a given team group.

  

Team groups are ways to separate teams in different sets. This allows the creation of multiple gameplay bubbles with their own teams in one single world.

## Methods

<table>
  <tbody>
    <tr>
      <td>**addLocalPlayerToTeam(teamName, teamGroupName)**</td>
      <td>Adds the local player to a team. If the player was already in a team, they a removed from it at the same time. Client only, raises an exception on the server.

Signature

```
addLocalPlayerToTeam(teamName: string, teamGroupName?: string): void;
```

Parameters

teamName: string

The name of the team to add to. Non existing teams are ignored.

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Non-existing groups are ignored.

Returns

void</td>
    </tr>
    <tr>
      <td>**addPlayerToTeam(player, teamName, teamGroupName)**</td>
      <td>Adds a player to a team. If the player was already in a team, they a removed from it at the same time. Server only. Raises an exception on clients.

Signature

```
addPlayerToTeam(player: Player, teamName: string, teamGroupName?: string): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player object to add to the team.

teamName: string

The name of the team to add to. Non-existing teams are ignored.

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Nnon-existing groups are ignored.

Returns

void</td>
    </tr>
    <tr>
      <td>**createTeam(teamName, teamGroupName)**</td>
      <td>Creates a new team within a group. Server only, raises an exception on clients.

Signature

```
createTeam(teamName: string, teamGroupName?: string): void;
```

Parameters

teamName: string

The unique name of the team. Empty names are ignored. Duplicates are ignored.

teamGroupName: string *(Optional)* The name of the group in which the team will exist. Undefined redirects to the Default group.

Returns

void</td>
    </tr>
    <tr>
      <td>**createTeamGroup(name)**</td>
      <td>Creates a new group of teams. Server only, raises an exception on clients.

Signature

```
createTeamGroup(name: string): void;
```

Parameters

name: string

The unique name of the group to create. Empty names are ignored. Duplicates are ignored.

Returns

void</td>
    </tr>
    <tr>
      <td>**deleteTeam(teamName, teamGroupName)**</td>
      <td>Delete a team within a group. Server only, raises an exception on clients.

Signature

```
deleteTeam(teamName: string, teamGroupName?: string): void;
```

Parameters

teamName: string

The name of the team to delete. Non-existing teams are ignored.

teamGroupName: string *(Optional)* The name of the group from which the team will be removed. Undefined redirects to the Default group. Non existing groups are ignored.

Returns

void</td>
    </tr>
    <tr>
      <td>**deleteTeamGroup(name)**</td>
      <td>Deletes a group of teams. Server only, raises an exception on clients.

Signature

```
deleteTeamGroup(name: string): void;
```

Parameters

name: string

The name of the group to delete. Default or non existing groups are ignored.

Returns

void</td>
    </tr>
    <tr>
      <td>**getPlayerTeam(player, teamGroupName)**</td>
      <td>Returns the name of the team a given player is in. If it doesn't exist, returns undefined.

Signature

```
getPlayerTeam(player: Player, teamGroupName?: string): string | undefined;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) Player to get the team

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Non-existing groups are ignored.

Returns

string | undefined

The name of the team, or undefined if none.</td>
    </tr>
    <tr>
      <td>**getTeamGroupNames()**</td>
      <td>Gets the list of all groups currently existing in the world.

Signature

```
getTeamGroupNames(): string[];
```

Returns

string\[\]

The list of group names.</td>
    </tr>
    <tr>
      <td>**getTeamNames(teamGroupName)**</td>
      <td>Returns the list of all teams within a group.

Signature

```
getTeamNames(teamGroupName?: string): string[];
```

Parameters

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Non-existing groups are ignored.

Returns

string\[\]

The list of names of the teams.</td>
    </tr>
    <tr>
      <td>**getTeamPlayers(world, teamName, teamGroupName)**</td>
      <td>Returns the list of player IDs in a team. Player objects can be recovered from the [World.getPlayers()](/horizon-worlds/reference/2.0.0/core_world#getplayers) list.

Signature

```
getTeamPlayers(world: World, teamName: string, teamGroupName?: string): Player[];
```

Parameters

world: [World](/horizon-worlds/reference/2.0.0/core_world) The world to extract the player list from.

teamName: string

The name of the team to add to. Non-existing teams are ignored.

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Non-existing groups are ignored.

Returns [Player](/horizon-worlds/reference/2.0.0/core_player) \[\]

The list of player IDs.</td>
    </tr>
    <tr>
      <td>**removeLocalPlayerFromTeam(teamGroupName)**</td>
      <td>Removes the local player from their team. Client only. Raises an exception on the server.

Signature

```
removeLocalPlayerFromTeam(teamGroupName?: string): void;
```

Parameters

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Non-existing groups are ignored.

Returns

void</td>
    </tr>
    <tr>
      <td>**removePlayerFromTeam(player, teamGroupName)**</td>
      <td>Removes a player from their team. Server only. Raises an exception on clients.

Signature

```
removePlayerFromTeam(player: Player, teamGroupName?: string): void;
```

Parameters

player: [Player](/horizon-worlds/reference/2.0.0/core_player) the player object to remove from the team.

teamGroupName: string *(Optional)* The name of the group where the team exists. Undefined redirects to the Default group. Non-existing groups are ignored.

Returns

void</td>
    </tr>
  </tbody>
</table>