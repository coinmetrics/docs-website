---
description: /timeseries/asset-metrics
---

# Asset Metrics Overview

Our Asset metrics include our Network Data time series metrics and certain Market Data metrics that are aggregated at the asset-level \(e.g., Reference Rates/Prices and Trusted Volume\). 

### Network Data

Our Network Data asset-metrics are typically daily metrics, but some metrics for some assets available in one block frequencies.  

* Daily network data metrics are computed at 00:00 UTC time for the previous 24 hour interval.   
* Block-by-block metrics are calculated each block. The data returned by the response will vary based on the `min_confirmations` parameter, which specifies the desired number of blocks behind the chain tip for the response

### Market Data

We have several Market Data metrics aggregated at the asset level, most notably our Reference Rates \(asset prices\).  These asset metrics are typically available in daily \(UTC and NY close\), hourly, minute-by-minute and one second frequencies.  

### Asset Coverage

Asset Metrics availability by asset can be found by selecting an asset in our [Assets Knowledge Base](https://docs.coinmetrics.io/info/assets).  

### Endpoint Response

The **Asset Metrics** endpoint returns time series data for each asset and metric requested.  The response is formatted as follows:

| Field | Description |
| :--- | :--- |
| asset | Asset |
| time | [Timestamp](../api.md#timestamps) |
| {MetricID} | Metric ID data \(as identified in the hundreds of asset-metrics that follow\) for the specific asset and timestamp  |
| {MetricID}-status | Status for metrics that require human review \(e.g., on-chain exchange supply and flows\); responses include "flash" for when a metric is just computed and not reviewed, "reviewed" for when a metric has been manually reviewed, and "revised" if a metric has been revised since its first publication  |
| {MetricID}-status-time | Date of last human review for metrics that require periodic review \(e.g., on-chain exchange supply and flows\) |



