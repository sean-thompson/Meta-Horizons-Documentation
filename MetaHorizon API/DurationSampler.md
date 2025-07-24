# DurationSampler Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/performance_durationsampler)

> Warning: This API is now obsolete.
> 
>   
> 
> Use 
> 
> [HorizonDurationSampler](/horizon-worlds/reference/2.0.0/performance_horizondurationsampler)
> 
>  instead!
> 
>   

This class is deprecated.

## Signature

```
export declare class DurationSampler
```

## Remarks

Creates a sampler that can be used to record an event that has a duration.

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(name)**</td>
      <td>Constructs a new instance of the `DurationSampler` class

* * *

Signature

```
constructor(name: string);
```

Parameters

name: string</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**trace(fn)**</td>
      <td>Signature

```
trace(fn: () => void): void;
```

Parameters

fn: () => void

Returns

void</td>
    </tr>
  </tbody>
</table>