# Consecutive Empty Blocks

**Definition**

The count of consecutive empty blocks captured within the most-recent 1-minute interval.

**Dictionary**

| Name                     | MetricID                         | Category | Sub-category | Type | Unit             | Interval |
| ------------------------ | -------------------------------- | -------- | ------------ | ---- | ---------------- | -------- |
| Consecutive Empty Blocks | block\_count\_consecutive\_empty | KRI      | Empty Blocks | Sum  | Count of  Blocks | 1b       |

**Methodology**

The set of most recently-processed blocks within a 1-minute window are captured and their contents are evaluated. Every consecutive empty block within the window is counted. For Ethereum, the maximum possible value this metric is 5 given that the time between blocks in that network is fixed at 12 seconds.

**Available Assets**

Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=eth&frequency=1b&metrics=block_count_consecutive_empty&pretty=true" %}
