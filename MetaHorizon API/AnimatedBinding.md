# AnimatedBinding Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_animatedbinding)

Extends 

*[ValueBindingBase](/horizon-worlds/reference/2.0.0/ui_valuebindingbase)

<number>*

A [Binding](/horizon-worlds/reference/2.0.0/ui_binding) that supports animations when setting values. Only numbers are supported. When the value of the `AnimatedBinding` is updated at runtime, the UI panels that use it are automatically re-rendered to reflect the change.

## Signature

```
export declare class AnimatedBinding extends ValueBindingBase<number>
```

## Examples

```
const anim = new AnimatedBinding(initialValue);
anim.set(Animation.timing(newValue));
```

## Remarks

The `AnimatedBinding` class differs from the [Binding](/horizon-worlds/reference/2.0.0/ui_binding) class in the following ways:

  

1\. It only takes number value, while the `Binding` class takes any type.

  

2\. It has no method, but has a more restrictive [AnimatedBinding.interpolate()](/horizon-worlds/reference/2.0.0/ui_animatedbinding#interpolate) method.

  

3\. In addition to plain numbers and update functions, the [AnimatedBinding.set()](/horizon-worlds/reference/2.0.0/ui_animatedbinding#set) method can also take an Animation object to define an animated transition to the new value.

  

For information about usage, see [Animations For Custom UIs](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/animations-for-custom-ui) .

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(value)**</td>
      <td>Constructs a new instance of the `AnimatedBinding` class.

* * *

Signature

```
constructor(value: number);
```

Parameters

value: number

The value of the binding.</td>
    </tr>
  </tbody>
</table>

## Methods

| interpolate(inputRange, outputRange) | Returns and interpolated version of the animated binding.Signatureinterpolate<T extends number \| string \| Color>(inputRange: Array<number>, outputRange: Array<T>): AnimatedInterpolation<T>;ParametersinputRange: Array<number>The range of number inputs to map to the output range of the interpolation. The array must have at least 2 elements. Each value in the range must be must be greater than or equal to the previous value (monotonically non-decreasing). The range must not contain positive or negative infinity.outputRange: Array<T>The range of number, string, or color outputs to map to the input range of the interpolation. The array must be of the same length as the inputRange array. The range must not contain positive or negative infinity. When the array elements are strings or Color objects, all elements must be of the same category. If the elements are suffixed numbers (a number with a unit, like 5.5%, 90deg), there must be no space between number and suffix, and all elements must have the same suffix. If the elements are colors, different color formats can be used in the same array.ReturnsAnimatedInterpolation<T>RemarksThis method maps the value of the animated binding to a new range using linear interpolation (LERP).When the length of the inputRange and outputRange is greater than 2, the animated binding is interpolated with multiple range segments. Within each segment, the value is interpolated linearly.When an input number is outside of the inputRange, it will linearly extrapolate beyond the ranges given. To achieve a clamped extrapolation, you can add a small flat segment outside of the range. |
| reset(players) | Resets the player-specific value of the binding, if any, back to the global value. Like the Binding.set() method, this method also queues a re-render operation for all UI panels that use this Binding.Signaturereset(players?: Array<Player>): void;Parametersplayers: Array<Player>(Optional) The players to reset the value for. If not provided, all player-specific values are cleared. If provided, only value for players in the list are reset and receive the global value.Returnsvoid |
| set(value, onEnd, players) | Updates the value of the binding and queues a re-render operation for all UI panels that use the binding. The UI does not update if the new and old values are the same.Signatureset(value: number \| ((prev: number) => number) \| Animation, onEnd?: AnimationOnEndCallback, players?: Array<Player>): void;Parametersvalue: number \| ((prev: number) => number) \| AnimationThe new value of the binding. This parameter can either be an explicit value, an updater function, or an Animation_2 object.onEnd: AnimationOnEndCallback(Optional) If an animation is passed to the value parameter, this callback triggers when animation ends, whether the animation completes or stops prematurely. This parameter is ignored if an Animation_2 object is not passed to the value parameter.players: Array<Player>(Optional) The players to apply the updated value to. This is used to determine whether the global value or the player-specific value should be updated. When not provided, all players receive the updated value; the global value is updated, and any player-specific values are cleared. When provided, only those players will get the new value as a new player-specific value, but the global value is unchanged.ReturnsvoidRemarksTo play multiple animations for the same AnimatedBinding object in a sequence, the Animation_2.sequence() method performs better than starting the next animation in the onEnd callback.When the value parameter is a an explicit value or an updater function, the value of the AnimatedBinding object is updated immediately without any animated transition. The updater function recieves the current value and mutates both the global value and each associated player value. If an Animation_2 object is passed to the value parameter, the AnimatedBinding object will smoothly transition to the final value using the specified animation. |
| stopAnimation(players) | Stops the binding animation for the given players.SignaturestopAnimation(players?: Array<Player>): void;Parametersplayers: Array<Player>(Optional) The players to stop the animation for.Returnsvoid |