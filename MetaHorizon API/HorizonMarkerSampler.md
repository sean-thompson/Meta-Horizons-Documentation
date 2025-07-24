# HorizonMarkerSampler Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/performance_horizonmarkersampler)

A trace sampler that flags events.

## Signature

```
export declare class HorizonMarkerSampler
```

## Remarks

Events flagged by this sampler aggregate to 1 if invoked and 0 if not.

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(samplerName)**</td>
      <td>Constructs a new instance of the `HorizonMarkerSampler` class.

* * *

Signature

```
constructor(samplerName: string);
```

Parameters

samplerName: string

The name of the `HorizonMarkerSampler` instance.</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**mark()**</td>
      <td>Flags an event, which aggregates to 1 if the event is called and 0 if it's not called.

Signature

```
mark(): void;
```

Returns

void</td>
    </tr>
  </tbody>
</table>