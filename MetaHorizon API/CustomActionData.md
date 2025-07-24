# CustomActionData type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/analytics_customactiondata)

The superset of optional data fields recognized by the Turbo engine.

## Signature

```
export declare type CustomActionData = {
    actionCustom?: string;
    team?: string;
    role?: string;
    gameMode?: string;
    gameRoundName?: string;
    gameRoundId?: string;
    gameRoundActivePlayers?: Array<string>;
    gameState?: GameStateEnum;
} & Optionalize<AbilityEquipPayload> & Optionalize<AbilityDequipPayload> & Optionalize<AbilityUsedPayload> & Optionalize<AFKEnterPayload> & Optionalize<AFKExitPayload> & Optionalize<AreaEnterPayload> & Optionalize<AreaExitPayload> & Optionalize<ArmorEquipPayload> & Optionalize<ArmorDequipPayload> & Optionalize<DamageEnemyPayload> & Optionalize<DamagePlayerPayload> & Optionalize<DeathPayload> & Optionalize<DeathByPlayerPayload> & Optionalize<DeathByEnemyPayload> & Optionalize<DiscoveryMadePayload> & Optionalize<FrictionCausedPayload> & Optionalize<FrictionHitPayload> & Optionalize<KOPlayerPayload> & Optionalize<KOEnemyPayload> & Optionalize<LevelUpPayload> & Optionalize<PlayerReadyEnterPayload> & Optionalize<PlayerReadyExitPayload> & Optionalize<QuestCompletedPayload> & Optionalize<RewardsEarnedPayload> & Optionalize<RoundStartPayload> & Optionalize<RoundEndPayload> & Optionalize<SectionStartPayload> & Optionalize<SectionEndPayload> & Optionalize<StageStartPayload> & Optionalize<StageEndPayload> & Optionalize<TaskStartPayload> & Optionalize<TaskEndPayload> & Optionalize<TaskStepStartPayload> & Optionalize<TaskStepEndPayload> & Optionalize<WeaponGrabPayload> & Optionalize<WeaponEquipPayload> & Optionalize<WeaponReleasePayload> & Optionalize<WearableEquipPayload> & Optionalize<WearableReleasePayload>;
```

## References [GameStateEnum](/horizon-worlds/reference/2.0.0/analytics_gamestateenum) , 

[AbilityEquipPayload](/horizon-worlds/reference/2.0.0/analytics_abilityequippayload)

, [AbilityDequipPayload](/horizon-worlds/reference/2.0.0/analytics_abilitydequippayload) , 

[AbilityUsedPayload](/horizon-worlds/reference/2.0.0/analytics_abilityusedpayload)

, [AreaEnterPayload](/horizon-worlds/reference/2.0.0/analytics_areaenterpayload) , 

[AreaExitPayload](/horizon-worlds/reference/2.0.0/analytics_areaexitpayload)

, [ArmorEquipPayload](/horizon-worlds/reference/2.0.0/analytics_armorequippayload) , 

[ArmorDequipPayload](/horizon-worlds/reference/2.0.0/analytics_armordequippayload)

, [DamageEnemyPayload](/horizon-worlds/reference/2.0.0/analytics_damageenemypayload) , 

[DamagePlayerPayload](/horizon-worlds/reference/2.0.0/analytics_damageplayerpayload)

, [DeathPayload](/horizon-worlds/reference/2.0.0/analytics_deathpayload) , 

[DeathByPlayerPayload](/horizon-worlds/reference/2.0.0/analytics_deathbyplayerpayload)

, [DeathByEnemyPayload](/horizon-worlds/reference/2.0.0/analytics_deathbyenemypayload) , 

[DiscoveryMadePayload](/horizon-worlds/reference/2.0.0/analytics_discoverymadepayload)

, [FrictionCausedPayload](/horizon-worlds/reference/2.0.0/analytics_frictioncausedpayload) , 

[FrictionHitPayload](/horizon-worlds/reference/2.0.0/analytics_frictionhitpayload)

, [KOPlayerPayload](/horizon-worlds/reference/2.0.0/analytics_koplayerpayload) , 

[KOEnemyPayload](/horizon-worlds/reference/2.0.0/analytics_koenemypayload)

, [LevelUpPayload](/horizon-worlds/reference/2.0.0/analytics_leveluppayload) , 

[PlayerReadyEnterPayload](/horizon-worlds/reference/2.0.0/analytics_playerreadyenterpayload)

, [PlayerReadyExitPayload](/horizon-worlds/reference/2.0.0/analytics_playerreadyexitpayload) , 

[QuestCompletedPayload](/horizon-worlds/reference/2.0.0/analytics_questcompletedpayload)

, [RewardsEarnedPayload](/horizon-worlds/reference/2.0.0/analytics_rewardsearnedpayload) , 

[RoundStartPayload](/horizon-worlds/reference/2.0.0/analytics_roundstartpayload)

, [RoundEndPayload](/horizon-worlds/reference/2.0.0/analytics_roundendpayload) , 

[SectionStartPayload](/horizon-worlds/reference/2.0.0/analytics_sectionstartpayload)

, [SectionEndPayload](/horizon-worlds/reference/2.0.0/analytics_sectionendpayload) , 

[StageStartPayload](/horizon-worlds/reference/2.0.0/analytics_stagestartpayload)

, [StageEndPayload](/horizon-worlds/reference/2.0.0/analytics_stageendpayload) , 

[TaskStartPayload](/horizon-worlds/reference/2.0.0/analytics_taskstartpayload)

, [TaskEndPayload](/horizon-worlds/reference/2.0.0/analytics_taskendpayload) , 

[TaskStepStartPayload](/horizon-worlds/reference/2.0.0/analytics_taskstepstartpayload)

, [TaskStepEndPayload](/horizon-worlds/reference/2.0.0/analytics_taskstependpayload) , 

[WeaponGrabPayload](/horizon-worlds/reference/2.0.0/analytics_weapongrabpayload)

, [WeaponEquipPayload](/horizon-worlds/reference/2.0.0/analytics_weaponequippayload) , 

[WeaponReleasePayload](/horizon-worlds/reference/2.0.0/analytics_weaponreleasepayload)

, [WearableEquipPayload](/horizon-worlds/reference/2.0.0/analytics_wearableequippayload) , 

[WearableReleasePayload](/horizon-worlds/reference/2.0.0/analytics_wearablereleasepayload)

## Remarks

This type is exported for easier visibility of the fields recognized by the Turbo engine.