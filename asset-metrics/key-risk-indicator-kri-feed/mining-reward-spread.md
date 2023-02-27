# Mining Reward Spread

**Definition**

The difference between the highest and lowest miner reward of the blocks being mined by the major mining pools.

**Dictionary**

| Name                 | MetricID               | Category | Sub-category | Type  | Unit         | Interval |
| -------------------- | ---------------------- | -------- | ------------ | ----- | ------------ | -------- |
| Mining Reward Spread | mining\_reward\_spread | KRI      | Mining Pools | Delta | Native units | 1m       |

**Methodology**

Coin Metrics collects data from major mining pools through the Stratum protocol, a popular software used by individual miners to connect to pools. That enables Coin Metrics to access all data an individual constituent of a mining pool would normally receive. In order to compute this metric, the coinbase transactions of all blocks currently being worked on by major mining pools are aggregated and assessed. The difference between the highest and lowest coinbase transaction is then calculated.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mining_reward_spread&pretty=true" %}
