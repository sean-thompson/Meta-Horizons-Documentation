# CustomMetricsCoordinator Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/performance_custommetricscoordinator)

Coordinates custom performance metrics behaviors including listening for events from the aggregation pipeline, returning event data, and clearing the event buffer.

## Signature

```
export declare class CustomMetricsCoordinator
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**activateMetric(metricConfig)**

 static</td>
      <td>Adds a metric to the active metrics list if there isn't already a metric with the provided name. Also, adds any samplers that contribute to the metric so they can be accessed at runtime.

Signature

```
static activateMetric(metricConfig: HorizonPerformanceMetricConfig): void;
```

Parameters

metricConfig: [HorizonPerformanceMetricConfig](/horizon-worlds/reference/2.0.0/performance_horizonperformancemetricconfig) The configuration for new metric to activate.

Returns

void</td>
    </tr>
    <tr>
      <td>**getActiveMetrics()**

 static</td>
      <td>Gets the metrics that are currently being aggregated.

Signature

```
static getActiveMetrics(): Array<HorizonPerformanceMetricConfig>;
```

Returns

Array< [HorizonPerformanceMetricConfig](/horizon-worlds/reference/2.0.0/performance_horizonperformancemetricconfig) >

An array that contains configurations of the active metrics.</td>
    </tr>
    <tr>
      <td>**getActiveSamplers()**

 static</td>
      <td>Gets the trace samplers that are running.

Signature

```
static getActiveSamplers(): Array<string>;
```

Returns

Array<string>

An array that contains the active trace samplers.</td>
    </tr>
    <tr>
      <td>**isTracingActive()**

 static</td>
      <td>Indicates whether the trace is running.

Signature

```
static isTracingActive(): boolean;
```

Returns

boolean `true` if tracing is in progress; false otherwise.</td>
    </tr>
  </tbody>
</table>