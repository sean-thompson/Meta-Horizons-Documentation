# SetTextureOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_settextureoptions)

Options for the [MeshEntity.setTexture()](/horizon-worlds/reference/2.0.0/core_meshentity#settexture) method.

## Signature

```
export declare type SetTextureOptions = {
    players?: Array<Player>;
};
```

## References [Player](/horizon-worlds/reference/2.0.0/core_player) ## Remarks

players - The players to apply the texture for. If null or empty, applies the texture for all players.