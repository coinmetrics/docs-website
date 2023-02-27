# Mempool Size

**Definition**

The total size of all transactions in the mempool, in bytes.&#x20;

**Dictionary**

| Name         | MetricID      | Category | Sub-category | Type | Unit  | Interval |
| ------------ | ------------- | -------- | ------------ | ---- | ----- | -------- |
| Mempool Size | mempool\_size | KRI      | Mempool      | Sum  | bytes | 1m       |

**Methodology**

The mempool is evaluated and all transactions within are indexed. The size of all transactions is summed.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&metrics=mempool_size&pretty=true" %}
