# Mean Feerate Mempool

**Definition**

The mean feerate (fee/vsize) of all mempool transactions, in native units per byte. Virtual Size (vsize) is a unit used to measure the size of a bitcoin transaction after the activation of SegWit.

**Dictionary**

| Name                 | MetricID               | Category | Sub-category | Type | Unit      | Interval |
| -------------------- | ---------------------- | -------- | ------------ | ---- | --------- | -------- |
| Mean Feerate Mempool | mempool\_feerate\_mean | KRI      | Mempool      | Mean | fee/vsize | 1m       |

**Methodology**

The mempool is evaluated and the feerate (fee/vsize) attached to all transactions is aggregated. The mean feerate of all transactions is then calculated.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_feerate_mean&pretty=true" %}
