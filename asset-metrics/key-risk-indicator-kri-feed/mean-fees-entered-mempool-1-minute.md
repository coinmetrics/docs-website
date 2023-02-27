# Mean Fees Entered Mempool 1 minute

**Definition**

The mean value of the fees paid for all transactions entering the mempool over the course of a 1-minute aggregation window. The beginning of this time window is noted in the “time” field of the response.

**Dictionary**

| Name                               | MetricID                        | Category | Sub-category | Type | Unit         | Interval |
| ---------------------------------- | ------------------------------- | -------- | ------------ | ---- | ------------ | -------- |
| Mean Fees entered mempool 1 minute | mempool\_fee\_mean\_entered\_1m | KRI      | Mempool      | Mean | Native units | 1m       |

**Methodology**

The mempool is evaluated and the fees attached to all transactions that have been entered (new transactions broadcasted by users) in the previous 1-minute interval are aggregated. The statistical mean of these fees is then calculated.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_fee_mean_entered_1m&pretty=true" %}
