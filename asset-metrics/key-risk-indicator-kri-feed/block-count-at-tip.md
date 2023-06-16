# Block Count at Tip

**Definition**

The number of blocks identified at the chain tip.

**Dictionary**

| Name               | MetricID              | Category | Sub-category     | Type | Unit          | Interval |
| ------------------ | --------------------- | -------- | ---------------- | ---- | ------------- | -------- |
| Block Count at Tip | block\_count\_at\_tip | KRI      | Block Attributes | Sum  | Count of tips | 1b       |

**Methodology**

Counts the number of unique block hashes at the tip of the chain and returns that number. More than one block count at the tip of the chain indiciates a fork in the chain.

**Available Assets**

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc,eth&frequency=1b&metrics=block_count_at_tip&pretty=true" %}
