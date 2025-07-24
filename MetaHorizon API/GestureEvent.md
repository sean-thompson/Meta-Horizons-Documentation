# GestureEvent Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/mobile_gestures_gestureevent)

Extends *LocalEvent<T>* Generic gesture event

## Signature

```
export declare class GestureEvent<T extends TouchEventData> extends LocalEvent<T>
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**connectLocalEvent(callback)**</td>
      <td>Signature

```
connectLocalEvent(callback: (payload: T) => void): EventSubscription;
```

Parameters

callback: (payload: T) => void

Returns

EventSubscription</td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)