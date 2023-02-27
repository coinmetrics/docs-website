# Base Fee for Block

**Definition**

The base fee of the most recent block processed.

**Dictionary**

| Name               | MetricID         | Category | Sub-category     | Type | Unit | Interval |
| ------------------ | ---------------- | -------- | ---------------- | ---- | ---- | -------- |
| Base Fee for Block | block\_base\_fee | KRI      | Block Attributes | Sum  | ETH  | 1b       |

**Methodology**

The most recent block we processed within a 1-minute window is evaluated and its Base Fee captured. The concept of a Base Fee was introduced as part of EIP-1559 and it represents the portion of the total transaction fees that is destroyed and taken out of circulation (i.e. burnt). Ethereum post-1559 requires users to pay for a Base Fee as a prerequisite to include transactions in a block. The Base Fee can go up or down on the basis of the size (in gas units) of the previous block.

**Available Assets**

Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=eth&frequency=1b&metrics=block_base_fee&pretty=true" %}

\
