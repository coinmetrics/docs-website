# Next Block Minimum Recommended Fee

**Definition**

The recommended minimum feerate required for a transaction to be included in the upcoming blockchain block. This metric differs from mempool\_next\_block\_approx\_feerate\_min in that it accounts for situations where there are many transactions paying the minimum feerate. By adding an additional cushion to the minimum estimate, this metric provides better settlement guarantees.

**Dictionary**

| Name                               | MetricID                                              | Category | Sub-category | Type | Unit       | Interval |
| ---------------------------------- | ----------------------------------------------------- | -------- | ------------ | ---- | ---------- | -------- |
| Next Block minimum recommended fee | mempool\_next\_block\_inclusion\_approx\_feerate\_min | KRI      | Mempool      | Sum  | sats/vbyte | 1m       |

**Methodology**

The calculation begins by ranking mempool transactions based on how much fees they are paying. A block template is then applied to these transactions with the goal of identifying which transactions rational miners would pick if they were to build a block at that minute The feerate of the lowest transaction that would still be included in that block template is then showcased. Depending on the aggregate size of transactions paying the minimum feerate, additional satoshi units are added in order to increase the likelihood that a transaction paying this feerate will be included in the next block.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_next_block_approx_feerate_min&pretty=true" %}
