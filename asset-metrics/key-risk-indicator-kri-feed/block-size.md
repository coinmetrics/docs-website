# Block Size

**Definition**

A block's size in bytes

**Dictionary**

| Name       | MetricID    | Category | Sub-category     | Type | Unit  | Interval |
| ---------- | ----------- | -------- | ---------------- | ---- | ----- | -------- |
| Block Size | block\_size | KRI      | Block Attributes | Sum  | bytes | 1b       |

**Methodology**

The most recent block is evaluated and the total size of that block is computed in bytes.

**Available Assets**

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc,eth&frequency=1b&metrics=block_size&pretty=true" %}
