# HorizonTraceEvent Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/performance_horizontraceevent)

A trace event in Horizon Worlds.

## Signature

```
export declare class HorizonTraceEvent
```

## Constructors

<table>
  <tbody>
    <tr>
      <td>**(constructor)(samplerName, type, value)**</td>
      <td>Constructs a `HorizonTraceEvent` object.

* * *

Signature

```
constructor(samplerName: string, type: HorizonTraceEventType, value: number);
```

Parameters

samplerName: string

The name of the `HorizonTraceEvent` object.

type: [HorizonTraceEventType](/horizon-worlds/reference/2.0.0/performance_horizontraceeventtype) The type of the sampler.

value: number

The value of the trace.</td>
    </tr>
  </tbody>
</table>

## Properties

<table>
  <tbody>
    <tr>
      <td>**samplerName**

\[readonly\]</td>
      <td>The name of the trace sampler for the event.

Signature

```
readonly samplerName: string;
```</td>
    </tr>
    <tr>
      <td>**timeStamp**

\[readonly\]</td>
      <td>The timestamp of event.

Signature

```
readonly timeStamp: number;
```</td>
    </tr>
    <tr>
      <td>**type**

\[readonly\]</td>
      <td>The trace event type.

Signature

```
readonly type: HorizonTraceEventType;
```</td>
    </tr>
    <tr>
      <td>**value**

\[readonly\]</td>
      <td>The value of the metric.

Signature

```
readonly value: number;
```</td>
    </tr>
  </tbody>
</table>