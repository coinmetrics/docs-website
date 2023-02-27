# Mempool Transaction Output Value Entered 1 Minute

**Definition**

The sum of all mempool transaction outputs in native units that have entered the mempool over the course of a 1-minute aggregation window. The beginning of this time window is noted in the “time” field of the response.

**Dictionary**

| Name                                              | MetricID                            | Category | Sub-category | Type | Unit         | Interval |
| ------------------------------------------------- | ----------------------------------- | -------- | ------------ | ---- | ------------ | -------- |
| Mempool Transaction Output value entered 1 minute | mempool\_output\_value\_entered\_1m | KRI      | Mempool      | Sum  | Native Units | 1m       |

**Methodology**

The mempool is evaluated and all transaction outputs (UTXOs) are indexed. The value of all UTXOs of mempool transactions that have entered the mempool in the previous 1-minute window is then summed.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_output_value_entered_1m&pretty=true" %}
