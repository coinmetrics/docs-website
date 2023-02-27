# Next Block Average Feerate

**Definition**

The approximate value of the mean feerate for the upcoming blockchain block.

**Dictionary**

| Name                        | MetricID                                    | Category | Sub-category | Type | Unit       | Interval |
| --------------------------- | ------------------------------------------- | -------- | ------------ | ---- | ---------- | -------- |
| Next Block Average feerate  | mempool\_next\_block\_approx\_feerate\_mean | KRI      | Mempool      | Sum  | sats/vbyte | 1m       |

**Methodology**

The calculation begins by ranking mempool transactions based on how much fees they are paying. A block template is then applied to these transactions with the goal of identifying which transactions rational miners would pick if they were to build a block at that minute The average (mean) feerate of the transactions in that block template is then showcased.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Assets**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_next_block_approx_feerate_men&pretty=true" %}
