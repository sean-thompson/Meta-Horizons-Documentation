# CustomMetricsBuffer Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/performance_custommetricsbuffer)

A list that contains a buffer of HorizonTraceEvents to send to the event aggregation pipeline for processing.

## Signature

```
export declare class CustomMetricsBuffer
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**getBufferContents()**

 static</td>
      <td>Gets the trace events that are in the trace event buffer.

Signature

```
static getBufferContents(): Array<HzTraceEventsBySampler>;
```

Returns

Array<HzTraceEventsBySampler>

An array that contains the elements in the trace event buffer.</td>
    </tr>
  </tbody>
</table>