# Mempool Fees Median

**Definition**

The sum value of all mempool transaction fees at a point in time in native units.

**Dictionary**

| Name                | MetricID             | Category | Sub-category | Type   | Unit         | Interval |
| ------------------- | -------------------- | -------- | ------------ | ------ | ------------ | -------- |
| Mempool Fees Median | mempool\_fee\_median | KRI      | Mempool      | Median | Native units | 1m       |

**Methodology**

The mempool is evaluated and all transactions indexed. The median value of all transaction fees within these unprocessed transactions is then calculated.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_fee_median&pretty=true" %}
