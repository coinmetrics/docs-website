# Miner Fees per Block

**Definition**

The sum of fees paid to miners for the transactions included in each mined block.

**Dictionary**

| Name                 | MetricID    | Category | Sub-category     | Type  | Unit       | Interval |
| -------------------- | ----------- | -------- | ---------------- | ----- | ---------- | -------- |
| Miner Fees per block | block\_fees | KRI      | Block Attributes | Delta | Difficulty | 1 block  |

**Methodology**

The most recently-mined block is evaluated and the sum of fees in that block is computed.

**Available Assets**

Bitcoin (BTC), _Ethereum (ETH)\*_

_\* Historical data covering the pre-merge timeframe only (up to 9/15/2022). With the merge ETH switched from Proof of Work and miners to Proof of Stake and validators meaning the miner fees per block are non-existent post the merge date for Ethereum._

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_fees&pretty=true" %}
