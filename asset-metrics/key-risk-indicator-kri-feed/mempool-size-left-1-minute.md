# Mempool Size Left 1 Minute

**Definition**

The total size in bytes of all transactions that have left the mempool over the course of a 1-minute aggregation window. The beginning of this time window is noted in the “time” field of the response.&#x20;

**Dictionary**

| Name                 | MetricID                | Category | Sub-category | Type | Unit  | Interval |
| -------------------- | ----------------------- | -------- | ------------ | ---- | ----- | -------- |
| Mempool Size Left 1m | mempool\_size\_left\_1m | KRI      | Mempool      | Sum  | bytes | 1m       |

**Methodology**

The mempool is evaluated and all transactions within are indexed. The size of all transactions that have left the mempool in the previous 1-minute window is summed.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&metrics=mempool_size_left_1m&pretty=true" %}
