# Transaction Count Entered Mempool 1 Minute

**Definition**

The count of all transactions that have entered the mempool over the course of a 1-minute aggregation window. The beginning of this time window is noted in the “time” field of the response.

**Dictionary**

| Name                                       | MetricID                    | Category | Sub-category | Type | Unit        | Interval |
| ------------------------------------------ | --------------------------- | -------- | ------------ | ---- | ----------- | -------- |
| Transaction Count entered mempool 1 minute | mempool\_count\_entered\_1m | KRI      | Mempool      | Sum  | Transaction | 1m       |

**Methodology**

The mempool is evaluated and all transactions that have been entered (new transactions broadcasted by users) since a point in time are counted.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_count_entered_1m&pretty=true" %}
