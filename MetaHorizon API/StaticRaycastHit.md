# StaticRaycastHit type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_staticraycasthit)

The result of a [raycast](/horizon-worlds/reference/2.0.0/core_raycastgizmo#raycast) collision against a static [Entity](/horizon-worlds/reference/2.0.0/core_entity) .

## Signature

```
export declare type StaticRaycastHit = BaseRaycastHit & {
    targetType: RaycastTargetType.Static;
};
```

## References [BaseRaycastHit](/horizon-worlds/reference/2.0.0/core_baseraycasthit) , 

[RaycastTargetType.Static](/horizon-worlds/reference/2.0.0/core_raycasttargettype)