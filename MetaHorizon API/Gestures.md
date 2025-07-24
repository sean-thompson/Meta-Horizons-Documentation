# Gestures Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/mobile_gestures_gestures)

Detects gestures

## Signature

```
export declare class Gestures
```

## Examples

```
import { Gestures } from 'horizon/mobile_gestures';

class MyComponent extends Component {
  gestures = new Gestures(this);

  start() {
    const player = this.entity.owner.get();
    player.enterFocusedInteractionMode();

    this.gestures.onTap.connectLocalEvent(({ touches }) => {
      console.log('tap', touches[0].current.screenPosition);
    });
    this.gestures.onLongTap.connectLocalEvent(({ touches }) => {
      console.log('long tap', touches[0].current.screenPosition);
    });
    this.gestures.onSwipe.connectLocalEvent(({ swipeDirection }) => {
      console.log('swipe', swipeDirection);
    });
    this.gestures.onPinch.connectLocalEvent(({ scale, rotate }) => {
      console.log('pinch', scale, rotate);
    });
  }
}
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(component, options)**</td>
      <td>Creates a Gestures helper

* * *

Signature

```
constructor(component: Component, options?: Partial<GesturesOptions>);
```

Parameters

component: Component

the component to attach to, must be owned by the local player

options: Partial< [GesturesOptions](/horizon-worlds/reference/2.0.0/mobile_gestures_gesturesoptions) > *(Optional)* Remarks

Requires to start processing events.</td>
    </tr>
  </tbody>
</table>

## Properties

| onLongTap | Connect to this event for long tap gestures. See Gestures for example usage.SignatureonLongTap: GestureEvent<LongTapEventData>; |
| onPan | Connect to this event for pan gestures. See Gestures for example usage.SignatureonPan: GestureEvent<PanEventData>; |
| onPinch | Connect to this event for pinch gestures. See Gestures for example usage.SignatureonPinch: GestureEvent<PinchEventData>; |
| onSwipe | Connect to this event for swipe gestures. See Gestures for example usage.SignatureonSwipe: GestureEvent<SwipeEventData>; |
| onTap | Connect to this event for tap gestures. See Gestures for example usage.SignatureonTap: GestureEvent<TapEventData>; |

## Methods

| dispose() | Call this to stop processing events, optional.Signaturedispose(): void;Returnsvoid |