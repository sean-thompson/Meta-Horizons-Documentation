# Animation_2 Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/ui_animation_2)

A simple or composite animation that can be passed to the [AnimatedBinding.set()](/horizon-worlds/reference/2.0.0/ui_animatedbinding#set) method.

## Signature

```
export declare abstract class Animation
```

## Examples

```
const anim = new AnimatedBinding(initialValue);
anim.set(Animation.repeat(Animation.timing(endValue, {duration: 300})));
```

## Remarks

Animations start on their own; they can only be used inside an [AnimatedBinding.set()](/horizon-worlds/reference/2.0.0/ui_animatedbinding#set) call.

  

For information about usage, see [Animations for Custom UIs](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/custom-ui/animations-for-custom-ui) .

## Methods

<table>
  <tbody>
    <tr>
      <td>**delay(time, animation)**

 static</td>
      <td>Starts an animation after the specified duration.

Signature

```
static delay(time: number, animation: Animation): Animation;
```

Parameters

time: number

The length of the delay to apply to the animation, in milliseconds.

animation: [Animation](/horizon-worlds/reference/2.0.0/ui_animation_2) The animation to apply the delay to.

Returns

[Animation](/horizon-worlds/reference/2.0.0/ui_animation_2)</td>
    </tr>
    <tr>
      <td>**repeat(animation, iterations)**

 static</td>
      <td>Repeats an animation the given number of times.

Signature

```
static repeat(animation: Animation, iterations?: number): Animation;
```

Parameters

animation: [Animation](/horizon-worlds/reference/2.0.0/ui_animation_2) The animation to repeat.

iterations: number *(Optional)* The number of times to repeat the animation. If not provided, or if a negative value if provided, the animation repeats until it is interrupted or stopped. When repeating the animation by passing an updater function to the [AnimatedBinding](/horizon-worlds/reference/2.0.0/ui_animatedbinding) object, the effect is not accumulative. The same animation with the same start and end values is replayed.

Returns [Animation](/horizon-worlds/reference/2.0.0/ui_animation_2) Remarks

Before each iteration of the animation, the animated binding is reset to the default value when was is created.</td>
    </tr>
    <tr>
      <td>**sequence(animations)**

 static</td>
      <td>Runs a set of animations in sequence.

Signature

```
static sequence(...animations: Array<Animation>): Animation;
```

Parameters

animations: Array< [Animation](/horizon-worlds/reference/2.0.0/ui_animation_2) >

The animations to run in sequence.

Returns [Animation](/horizon-worlds/reference/2.0.0/ui_animation_2) Remarks

When playing multiple animations in a squence for the same [AnimatedBinding](/horizon-worlds/reference/2.0.0/ui_animatedbinding) object, the `sequence` method performs better than the `onEnd` callback that is passed to the `AnimatedBinding`. However, to play animations for different [AnimatedBinding](/horizon-worlds/reference/2.0.0/ui_animatedbinding) objects in sequence, you must use the `onEnd` callback.</td>
    </tr>
    <tr>
      <td>**timing(value, config)**

 static</td>
      <td>Applies a timing animation to the binding based on the given easing curve.

Signature

```
static timing(value: number | ((prev: number) => number), config?: TimingAnimationConfig): Animation;
```

Parameters

value: number | ((prev: number) => number)

The binding value. This can be an explicit value or an updater function that calculates the new value from the previous value.

config: [TimingAnimationConfig](/horizon-worlds/reference/2.0.0/ui_timinganimationconfig) *(Optional)*

 The animation configuration that specifies the easing curve.

Returns

[Animation](/horizon-worlds/reference/2.0.0/ui_animation_2)</td>
    </tr>
  </tbody>
</table>