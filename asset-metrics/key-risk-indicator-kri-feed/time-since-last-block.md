# Time Since Last Block

**Definition**

The time elapsed between the current time and the last block at the tip of the chain (the most recent block).

**Dictionary**

| Name                  | MetricID                 | Category | Sub-category     | Type  | Unit    | Interval |
| --------------------- | ------------------------ | -------- | ---------------- | ----- | ------- | -------- |
| Time since last block | time\_since\_last\_block | KRI      | Block Attributes | Delta | seconds | 1 minute |

**Methodology**

The metric is computed as the time difference between the arrival of the block at the chain tip as seen by our nodes, and the current time. As a timestamp for the block at the chain tip this metric uses the concept of miner\_time (for more on the differences between miner\_time and consensus\_time refer to our [wiki article](../../on-chain-data/methodologies/on-chain-basics.md) on normalizing timestamps). For Bitcoin, miner\_time can be set arbitrarily by miners which can impact the value of this metric.

**Available Assets**&#x20;

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc,eth&frequency=1m&limit_per_asset=1&metrics=time_since_last_block&pretty=true" %}
