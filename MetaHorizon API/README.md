# Meta Horizon Worlds TypeScript API Reference

This folder contains comprehensive API documentation for the Meta Horizon Worlds TypeScript API version 2.0.0. Each file documents a specific class, interface, method, or component of the API.

## API Information
- **Version**: 2.0.0 ([ApiVersion.md](ApiVersion.md))
- **API Name**: "avatar_ai_agent" ([ApiName.md](ApiName.md))
- **Official Documentation**: [Meta Horizon Worlds Developer Docs](https://developers.meta.com/horizon-worlds/)

## Quick Start
If you're new to the API, start with these foundational files:
- [Entity.md](Entity.md) - Core class representing objects in Meta Horizon Worlds
- [Component.md](Component.md) - Base class for all components
- [Class.md](Class.md) - Interface representing a class

## Core System Components

### Entities and Components
- [Entity.md](Entity.md) - Core entity class
- [Component.md](Component.md) - Base component class
- [ComponentWithConstructor.md](ComponentWithConstructor.md)
- [AttachableEntity.md](AttachableEntity.md)
- [GrabbableEntity.md](GrabbableEntity.md)
- [MeshEntity.md](MeshEntity.md)
- [AnimatedEntity.md](AnimatedEntity.md)

### Properties and Data Binding
- [HorizonProperty.md](HorizonProperty.md) - Core property system
- [HorizonReferenceProperty.md](HorizonReferenceProperty.md)
- [Bindable.md](Bindable.md)
- [Binding.md](Binding.md)
- [BindingSet.md](BindingSet.md)
- [AnimatedBinding.md](AnimatedBinding.md)

### Events and Callbacks
- [CodeBlockEvent.md](CodeBlockEvent.md)
- [CodeBlockEvents.md](CodeBlockEvents.md)
- [LocalEvent.md](LocalEvent.md)
- [EventData.md](EventData.md)
- [EventSubscription.md](EventSubscription.md)
- [Callback.md](Callback.md)
- [CallbackMap.md](CallbackMap.md)
- [CallbackWithPayload.md](CallbackWithPayload.md)

## Gizmos (Interactive Components)

### Audio and Media
- [AudioGizmo.md](AudioGizmo.md)
- [AudioOptions.md](AudioOptions.md)
- [AudibilityMode.md](AudibilityMode.md)

### Visual and UI
- [DynamicLightGizmo.md](DynamicLightGizmo.md)
- [AvatarPoseGizmo.md](AvatarPoseGizmo.md)
- [AssetPoolGizmo.md](AssetPoolGizmo.md)
- [AssetBundleGizmo.md](AssetBundleGizmo.md)
- [IWPSellerGizmo.md](IWPSellerGizmo.md)

### AI and NPCs
- [AIAgentGizmo.md](AIAgentGizmo.md)
- [AvatarAIAgent.md](AvatarAIAgent.md)
- [AchievementsGizmo.md](AchievementsGizmo.md)

## User Interface System

### Core UI
- [IUI.md](IUI.md) - Main UI interface
- [CustomUI-gizmo.md](Custom-UI-gizmo.md)
- [DynamicList.md](DynamicList.md)
- [DynamicListProps.md](DynamicListProps.md)

### UI Styling and Layout
- [EntityStyle.md](EntityStyle.md)
- [IEntityStyle.md](IEntityStyle.md)
- [LayoutStyle.md](LayoutStyle.md)
- [BorderStyle.md](BorderStyle.md)
- [FontFamily.md](FontFamily.md)
- [Color.md](Color.md)
- [ColorValue.md](ColorValue.md)

### UI Components
- [Image_2.md](Image_2.md)
- [ImageProps.md](ImageProps.md)
- [ImageSource.md](ImageSource.md)
- [ImageStyle.md](ImageStyle.md)
- [InfoSlide.md](InfoSlide.md)
- [InfoSlideStyle.md](InfoSlideStyle.md)

### UI Interactions
- [ButtonIcon.md](ButtonIcon.md)
- [ButtonPlacement.md](ButtonPlacement.md)
- [FocusedInteraction.md](FocusedInteraction.md)
- [FocusedInteractionOptions.md](FocusedInteractionOptions.md)
- [FocusUIOptions.md](FocusUIOptions.md)

## Animation System

### Core Animation
- [Animation_2.md](Animation_2.md)
- [AnimationCallback.md](AnimationCallback.md)
- [AnimationCallbackReason.md](AnimationCallbackReason.md)
- [AnimationCallbackReasons.md](AnimationCallbackReasons.md)
- [AnimatedInterpolation.md](AnimatedInterpolation.md)

### Avatar Animation
- [AvatarAnimationMask.md](AvatarAnimationMask.md)
- [AvatarGripPose.md](AvatarGripPose.md)
- [AvatarGripPoseAnimationCallback.md](AvatarGripPoseAnimationCallback.md)
- [AvatarGripPoseAnimationNames.md](AvatarGripPoseAnimationNames.md)
- [AvatarImageExpressions.md](AvatarImageExpressions.md)
- [AvatarPoseUseMode.md](AvatarPoseUseMode.md)

### Easing and Transitions
- [Easing.md](Easing.md)
- [Easing (1).md](Easing%20(1).md)

## Camera System
- [Camera.md](Camera.md)
- [LocalCamera.md](LocalCamera.md)
- [LocalCamera (2).md](LocalCamera%20(2).md)
- [CameraApiName.md](CameraApiName.md)
- [CameraMode.md](CameraMode.md)
- [CameraTarget.md](CameraTarget.md)
- [ICameraMode.md](ICameraMode.md)

### Camera Modes
- [FirstPersonCameraMode.md](FirstPersonCameraMode.md)
- [FixedCameraMode.md](FixedCameraMode.md)
- [FollowCameraMode.md](FollowCameraMode.md)
- [AttachCameraMode.md](AttachCameraMode.md)

### Camera Options
- [FixedCameraOptions.md](FixedCameraOptions.md)
- [FollowCameraOptions.md](FollowCameraOptions.md)
- [AttachCameraOptions.md](AttachCameraOptions.md)
- [CameraTransitionOptions.md](CameraTransitionOptions.md)
- [CameraTransitionEndReason.md](CameraTransitionEndReason.md)

## Navigation and Physics

### Navigation Mesh
- [NavMesh.md](NavMesh.md)
- [INavMesh.md](INavMesh.md)
- [NavMeshAgent.md](NavMeshAgent.md)
- [INavMeshAgent.md](INavMeshAgent.md)
- [NavMeshApiName.md](NavMeshApiName.md)
- [NavMeshAgentAlignment.md](NavMeshAgentAlignment.md)
- [NavMeshBakeInfo.md](NavMeshBakeInfo.md)
- [NavMeshDetailedPath.md](NavMeshDetailedPath.md)
- [NavMeshHit.md](NavMeshHit.md)

### Physics and Collision
- [BaseRaycastHit.md](BaseRaycastHit.md)
- [EntityRaycastHit.md](EntityRaycastHit.md)
- [Bounds.md](Bounds.md)

### Agent Behavior
- [AgentGrabActionResult.md](AgentGrabActionResult.md)
- [AgentGrabbableInteraction.md](AgentGrabbableInteraction.md)
- [AgentLocomotion.md](AgentLocomotion.md)
- [AgentLocomotionOptions.md](AgentLocomotionOptions.md)
- [AgentLocomotionResult.md](AgentLocomotionResult.md)
- [AgentRotationOptions.md](AgentRotationOptions.md)
- [AgentSpawnResult.md](AgentSpawnResult.md)

## Input and Interaction

### Player Input
- [Gestures.md](Gestures.md)
- [GesturesOptions.md](GesturesOptions.md)
- [GestureEvent.md](GestureEvent.md)
- [LongTapEventData.md](LongTapEventData.md)
- [MobileGestureApiName.md](MobileGestureApiName.md)

### Interaction Modes
- [EntityInteractionMode.md](EntityInteractionMode.md)
- [InteractionInfo.md](InteractionInfo.md)
- [FocusedInteractionTapOptions.md](FocusedInteractionTapOptions.md)
- [FocusedInteractionTrailOptions.md](FocusedInteractionTrailOptions.md)

### Haptic Feedback
- [HapticSharpness.md](HapticSharpness.md)
- [HapticStrength.md](HapticStrength.md)
- [Handedness.md](Handedness.md)

## Assets and Resources

### Asset Management
- [Asset.md](Asset.md)
- [AssetContentData.md](AssetContentData.md)
- [AssetBundleInstanceReference.md](AssetBundleInstanceReference.md)
- [MaterialAsset.md](MaterialAsset.md)

### Player Attachments
- [AttachablePlayerAnchor.md](AttachablePlayerAnchor.md)

## Analytics and Metrics

### Core Analytics
- [analytics.md](analytics.md)
- [analytics (1).md](analytics%20(1).md)
- [AnalyticsSectionGameMode.md](AnalyticsSectionGameMode.md)

### Custom Metrics
- [CustomMetricsBuffer.md](CustomMetricsBuffer.md)
- [CustomMetricsCoordinator.md](CustomMetricsCoordinator.md)

### Performance Metrics
- [HorizonCountSampler.md](HorizonCountSampler.md)
- [HorizonDurationSampler.md](HorizonDurationSampler.md)
- [HorizonMarkerSampler.md](HorizonMarkerSampler.md)
- [HorizonMetricSuffixes.md](HorizonMetricSuffixes.md)
- [HorizonPerformanceMetricConfig.md](HorizonPerformanceMetricConfig.md)
- [CountSampler.md](CountSampler.md)
- [DurationSampler.md](DurationSampler.md)
- [MarkerSampler.md](MarkerSampler.md)

### Trace Events
- [HorizonTraceEvent.md](HorizonTraceEvent.md)
- [HorizonTraceEventType.md](HorizonTraceEventType.md)

## Game Systems

### Teams and Leaderboards
- [ITeam.md](ITeam.md)
- [ILeaderboards.md](ILeaderboards.md)
- [LEADEBOARD_SCORE_MAX_VALUE.md](LEADEBOARD_SCORE_MAX_VALUE.md)

### Game State
- [GameStateEnum.md](GameStateEnum.md)
- [GameRoundEndForPlayersPayload.md](GameRoundEndForPlayersPayload.md)
- [GameRoundStartForPlayersPayload.md](GameRoundStartForPlayersPayload.md)

### Monetization
- [InWorldPurchasable.md](InWorldPurchasable.md)
- [InWorldPurchasablePrice.md](InWorldPurchasablePrice.md)
- [InWorldPurchase.md](InWorldPurchase.md)
- [InWorldShopHelpers.md](InWorldShopHelpers.md)
- [MonetizationTimeOption.md](MonetizationTimeOption.md)

## Event Payloads

### Player Events
- [DeathPayload.md](DeathPayload.md)
- [DeathByEnemyPayload.md](DeathByEnemyPayload.md)
- [DeathByPlayerPayload.md](DeathByPlayerPayload.md)
- [DamageEnemyPayload.md](DamageEnemyPayload.md)
- [DamagePlayerPayload.md](DamagePlayerPayload.md)
- [KOEnemyPayload.md](KOEnemyPayload.md)
- [KOPlayerPayload.md](KOPlayerPayload.md)
- [LevelUpPayload.md](LevelUpPayload.md)

### Equipment Events
- [AbilityDequipPayload.md](AbilityDequipPayload.md)
- [AbilityEquipPayload.md](AbilityEquipPayload.md)
- [AbilityUsedPayload.md](AbilityUsedPayload.md)
- [ArmorDequipPayload.md](ArmorDequipPayload.md)
- [ArmorEquipPayload.md](ArmorEquipPayload.md)

### World Events
- [AreaEnterPayload.md](AreaEnterPayload.md)
- [AreaExitPayload.md](AreaExitPayload.md)
- [DiscoveryMadePayload.md](DiscoveryMadePayload.md)
- [CustomEventPayload.md](CustomEventPayload.md)

### Physics Events
- [FrictionCausedPayload.md](FrictionCausedPayload.md)
- [FrictionHitPayload.md](FrictionHitPayload.md)

## Storage and Persistence
- [IPersistentStorage.md](IPersistentStorage.md)
- [IPersistentStorageWorld.md](IPersistentStorageWorld.md)

## Utility Functions and Helpers

### Math Utilities
- [clamp.md](clamp.md)
- [degreesToRadians.md](degreesToRadians.md)
- [EulerOrder.md](EulerOrder.md)

### Testing and Debugging
- [BaseTestComponent.md](BaseTestComponent.md)
- [assert.md](assert.md)

### Data Types and Interfaces
- [Comparable.md](Comparable.md)
- [Copyable.md](Copyable.md)
- [DisposableObject.md](DisposableObject.md)
- [DisposeOperation.md](DisposeOperation.md)
- [DisposeOperationRegistration.md](DisposeOperationRegistration.md)

## Configuration and Options

### Default Options
- [DefaultFetchAsDataOptions.md](DefaultFetchAsDataOptions.md)
- [DefaultFocusedInteractionEnableOptions.md](DefaultFocusedInteractionEnableOptions.md)
- [DefaultFocusedInteractionTapOptions.md](DefaultFocusedInteractionTapOptions.md)
- [DefaultFocusedInteractionTrailOptions.md](DefaultFocusedInteractionTrailOptions.md)
- [DefaultPopupOptions.md](DefaultPopupOptions.md)
- [DefaultSpringOptions.md](DefaultSpringOptions.md)
- [DefaultThrowOptions.md](DefaultThrowOptions.md)
- [DefaultTooltipOptions.md](DefaultTooltipOptions.md)

### Fetch and Data Options
- [FetchAsDataOptions.md](FetchAsDataOptions.md)

### Aim and Targeting
- [AimAssistOptions.md](AimAssistOptions.md)
- [ForceLookAtOptions.md](ForceLookAtOptions.md)
- [LaunchProjectileOptions.md](LaunchProjectileOptions.md)

## Enums and Constants

### Built-in Types
- [BuiltInVariableType.md](BuiltInVariableType.md)
- [LayerType.md](LayerType.md)
- [DimensionValue.md](DimensionValue.md)

### Event Types
- [EventTargetType.md](EventTargetType.md)
- [EventValueType.md](EventValueType.md)

### Entity Operations
- [EntityTagMatchOperation.md](EntityTagMatchOperation.md)

### UI Properties
- [ConditionalProps.md](ConditionalProps.md)

### Settings
- [ITurboSettings.md](ITurboSettings.md)

## Advanced Features

### Custom Actions
- [Action.md](Action.md)
- [CustomActionData.md](CustomActionData.md)

### Entity Visibility
- [EntityVisibility.md](EntityVisibility.md) (if exists)

---

## Navigation Tips

1. **Start with Core Concepts**: Begin with Entity.md and Component.md to understand the fundamental building blocks
2. **Browse by Category**: Use the categories above to find related functionality
3. **Search by Name**: Use Ctrl+F to search for specific class or method names
4. **Follow References**: Each file includes links to the official Meta documentation for more context
5. **Check Examples**: Many files include code examples showing practical usage

## Additional Resources

- [Meta Horizon Worlds Developer Portal](https://developers.meta.com/horizon-worlds/)
- [TypeScript API Documentation](https://developers.meta.com/horizon-worlds/reference/2.0.0/)
- [Getting Started Guide](https://developers.meta.com/horizon-worlds/learn/getting-started/)

---

*This documentation is for Meta Horizon Worlds TypeScript API version 2.0.0. For the latest updates and complete documentation, visit the official Meta Horizon Worlds developer portal.*
