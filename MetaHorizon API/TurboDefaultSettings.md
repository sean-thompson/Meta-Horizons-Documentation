# TurboDefaultSettings Variable

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/analytics_turbodefaultsettings)

The default [settings](/horizon-worlds/reference/2.0.0/analytics_iturbosettings) for a [Turbo](/horizon-worlds/reference/2.0.0/analytics_turbo) instance, including the initial Turbo events and data to collect.

## Signature

```
TurboDefaultSettings: ITurboSettings
```

## Remarks

To use these settings, pass this value to `Turbo.register(component, configs)` method. For more information, see the [Turbo](/horizon-worlds/reference/2.0.0/analytics_turbo) variable.

  

Default settings: [debug](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#debug) `false` [experiments](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#experiments) `new Set<string>()` [frictionNoKOsTimerSeconds](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#frictionnokostimerseconds) `120.0` [gameMode](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#gamemode) \- game mode is empty [heartbeatFrequencySeconds](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#heartbeatfrequencyseconds) `120` [maxAFKSecondsBeforeRemove](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#maxafksecondsbeforeremove) `180` [maxFrictionNoKOEvents](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#maxfrictionnokoevents) `30` [playerInitialArea](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#playerinitialarea) `lobby_world_enter` [playerInitialState](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#playerinitialstate) `ParticipationEnum.IN_LOBBY` [turboUpdateSeconds](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#turboupdateseconds) `1.0`

  

These settings are set to true by default, which enables the associated Turbo actions: [useAFK](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useafk) [useDiscovery](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usediscovery) [useFriction](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usefriction) [useGameMode](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usegamemode) [useHeartbeats](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useheartbeats) [useLevelUp](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#uselevelup) [useQuests](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usequests) [useRewards](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#userewards)

  

These settings are set to false by default, which disables the associated Turbo actions: [eventsForWearableEquipAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#eventsforwearableequipandrelease) [useAbilities](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useabilities) [useArmor](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usearmor) [useDamage](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usedamage) [useForward](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useforward) [useFrictionNoKOs](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usefrictionnokos) [useRotation](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#userotation) [useRounds](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#userounds) [useSections](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usesections) [useStages](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usestages) [useTasks](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usetasks) [useTeamAndRole](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useteamandrole) [useTransforms](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usetransforms) [useWeaponEquip](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweaponequip) [useWeaponGrabAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweapongrabandrelease) [useWeapons](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#useweapons) [useWearableEquipAndRelease](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usewearableequipandrelease) [useWearables](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#usewearables)

## Examples

This example sets the Turbo settings to the default settings.

```
Turbo.register(this, TurboDefaultSettings);
```