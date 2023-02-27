# Mempool visze Left 1 Minute

**Definition**

The total virtual size (vsize), in bytes, of all transactions that have left the mempool over the course of a 1- minute aggregation window. The beginning of this time window is noted in the “time” field of the response. [Virtual Size (vsize)](https://en.bitcoin.it/wiki/Weight\_units) is a unit used to measure the size of a bitcoin transaction after the activation of SegWit.

**Dictionary**

| Name                        | MetricID                 | Category | Sub-category | Type | Unit          | Interval |
| --------------------------- | ------------------------ | -------- | ------------ | ---- | ------------- | -------- |
| Mempool vsize left 1 minute | mempool\_vsize\_left\_1m | KRI      | Mempool      | Sum  | Virtual bytes | 1m       |

**Methodology**

The mempool is evaluated and all transactions within are indexed. The virtual size of all transactions that have left the mempool in the previous 1-minute window is summed.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_vsize_left_1m&pretty=true" %}
