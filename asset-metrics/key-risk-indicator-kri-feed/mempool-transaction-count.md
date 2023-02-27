# Mempool Transaction Count

**Definition**

The count of all mempool transactions at a point in time.

**Dictionary**

| Name                      | MetricID       | Category | Sub-category | Type | Unit        | Interval |
| ------------------------- | -------------- | -------- | ------------ | ---- | ----------- | -------- |
| Mempool Transaction Count | mempool\_count | KRI      | Mempool      | Sum  | Transaction | 1m       |

**Methodology**

The mempool is evaluated and all transactions indexed. All unprocessed mempool transactions at a point in time are then counted.

**Available Assets**&#x20;

Bitcoin (BTC)

Sample Query

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_count&pretty=true" %}
