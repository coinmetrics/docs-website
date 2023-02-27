# Average Mining Reward

**Definition**

The mean mining reward (transaction fees + issuance) of the blocks currently being mined across all major mining pools, in native units (e.g. units of BTC).

**Dictionary**

| Name                  | MetricID             | Category | Sub-category | Type | Unit         | Interval |
| --------------------- | -------------------- | -------- | ------------ | ---- | ------------ | -------- |
| Average Mining Reward | mining\_reward\_mean | KRI      | Mining Pools | Sum  | Native units | 1m       |

**Methodology**

Coin Metrics collects data from major mining pools through the Stratum protocol, a popular software used by individual miners to connect to mining pools. That enables Coin Metrics to access all data a mining pool constituent would normally see. In order to compute this metric, the coinbase transactions of all blocks currently being worked on by major mining pools are aggregated and assessed. The statistical mean is then calculated.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mining_reward_mean&pretty=true" %}
