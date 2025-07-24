# PlayerRaycastHit type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playerraycasthit)

The result of a [raycast](/horizon-worlds/reference/2.0.0/core_raycastgizmo#raycast) collision against a [Player](/horizon-worlds/reference/2.0.0/core_player) .

## Signature

```
export declare type PlayerRaycastHit = BaseRaycastHit & {
    targetType: RaycastTargetType.Player;
    target: Player;
};
```

## References [BaseRaycastHit](/horizon-worlds/reference/2.0.0/core_baseraycasthit) , 

[RaycastTargetType.Player](/horizon-worlds/reference/2.0.0/core_raycasttargettype)

, 

[Player](/horizon-worlds/reference/2.0.0/core_player)