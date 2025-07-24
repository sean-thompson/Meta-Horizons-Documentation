# EntityRaycastHit type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_entityraycasthit)

The result of a [raycast](/horizon-worlds/reference/2.0.0/core_raycastgizmo#raycast) collision against an [Entity](/horizon-worlds/reference/2.0.0/core_entity) .

## Signature

```
export declare type EntityRaycastHit = BaseRaycastHit & {
    targetType: RaycastTargetType.Entity;
    target: Entity;
};
```

## References [BaseRaycastHit](/horizon-worlds/reference/2.0.0/core_baseraycasthit) , 

[RaycastTargetType.Entity](/horizon-worlds/reference/2.0.0/core_raycasttargettype)

, 

[Entity](/horizon-worlds/reference/2.0.0/core_entity)