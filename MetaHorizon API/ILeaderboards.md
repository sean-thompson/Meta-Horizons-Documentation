# ILeaderboards Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_ileaderboards)

The leaderboards for the players in the world.

## Signature

```
export interface ILeaderboards
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**setScoreForPlayer(leaderboardName, player, score, override)**</td>
      <td>Sets the leaderboard score for a player.

Signature

```
setScoreForPlayer(leaderboardName: string, player: Player, score: number, override: boolean): void;
```

Parameters

leaderboardName: string

The name of the leader board.

player: [Player](/horizon-worlds/reference/2.0.0/core_player) The player for whom the score is updated.

score: number

The new score.

override: boolean

If `true`, overrides the previous score; otherwise the previous score is retained.

Returns

void</td>
    </tr>
  </tbody>
</table>