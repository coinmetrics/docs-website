# Mempool Fees Mean

**Definition**

The sum value of all mempool transaction fees at a point in time in native units.

**Dictionary**

| Name              | MetricID           | Category | Sub-category | Type | Unit         | Interval |
| ----------------- | ------------------ | -------- | ------------ | ---- | ------------ | -------- |
| Mempool Fees Mean | mempool\_fee\_mean | KRI      | Mempool      | Mean | Native units | 1m       |

**Methodology**

The mempool is evaluated and all transactions indexed. The mean value of all transaction fees within these unprocessed transactions is then calculated.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_fee_mean&pretty=true" %}
