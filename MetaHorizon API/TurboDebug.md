# TurboDebug Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/analytics_turbodebug)

A set of tools for debugging and testing Turbo implementations.

## Signature

```
export declare class TurboDebug
```

## Remarks

To use Turbo debugging, you must enable it by setting the [ITurboSettings.debug](/horizon-worlds/reference/2.0.0/analytics_iturbosettings#debug) property to `true`.

## Properties

<table>
  <tbody>
    <tr>
      <td>**events**

static

  </td>
      <td>An event subscription that delivers enriched analytics payloads to event listeners.

Signature

```
static events: {
        onDebugTurboPlayerEvent: hz.LocalEvent<{
            player: hz.Player;
            eventData: EventData;
            action: Action;
        }>;
    };
```</td>
    </tr>
  </tbody>
</table>