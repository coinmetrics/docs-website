# Priority Fee for Block

**Definition**

The priority fee, or tip, of the most recent block processed.

**Dictionary**

| Name                   | MetricID             | Category | Sub-category     | Type | Unit | Interval |
| ---------------------- | -------------------- | -------- | ---------------- | ---- | ---- | -------- |
| Priority Fee for Block | block\_priority\_fee | KRI      | Block Attributes | Sum  | ETH  | 1b       |

**Methodology**

The most recent block we processed within a 1-minute window is evaluated and its Priority Fee, or tip, is captured. The concept of a Miner Tip was introduced as part of EIP-1559 and it represents the portion of the total transaction fees that rewards miners. This serves as an added incentive so that miners prioritize transactions that have opted-in and paid a tip. The other portion is called the Base Fee, and it is burnt (destroyed) after the transaction is included in a block.

**Available Assets**

Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=eth&frequency=1b&metrics=block_priority_fee&pretty=true" %}
