# HorizonDurationSampler Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/performance_horizondurationsampler)

A trace sampler that tracks the duration of function calls.

## Signature

```
export declare class HorizonDurationSampler
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(samplerName)**</td>
      <td>Constructs a new instance of the `HorizonDurationSampler` class.

* * *

Signature

```
constructor(samplerName: string);
```

Parameters

samplerName: string

The name of the `HorizonDurationSampler` instance.</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**trace(fn)**</td>
      <td>Tracks the duration of the given function call.

Signature

```
trace(fn: () => void): void;
```

Parameters

fn: () => void

The function call to track.

Returns

void</td>
    </tr>
  </tbody>
</table>

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)