# Mempool Fee Sum

**Definition**

The sum value of all mempool transaction fees at a point in time in native units.

**Dictionary**

| Name            | MetricID     | Category | Sub-category | Type | Unit         | Interval |
| --------------- | ------------ | -------- | ------------ | ---- | ------------ | -------- |
| Mempool Fee Sum | mempool\_fee | KRI      | Mempool      | Sum  | Native units | 1m       |

**Methodology**

The mempool is evaluated and all transactions indexed. The value of all transaction fees within these unprocessed transactions is then summed.

**Available Assets**&#x20;

Bitcoin (BTC)

Sample Query

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_fee&pretty=true" %}
