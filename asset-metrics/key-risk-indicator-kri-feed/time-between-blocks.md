# Time between blocks

**Definition**

The time elapsed between the block at the tip of the chain (the most recent block) and its predecessor.

**Dictionary**

| Name                | MetricID           | Category | Sub-category     | Type | Unit    | Interval |
| ------------------- | ------------------ | -------- | ---------------- | ---- | ------- | -------- |
| Time between blocks | time\_inter\_block | KRI      | Block Attributes | Sum  | seconds | 1 minute |

**Methodology**

The metric is computed as the time difference between the arrival of the block at the chain tip as seen by our nodes, and the arrival of the previous block.

**Available Assets**&#x20;

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=time_inter_block&pretty=true" %}
