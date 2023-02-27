# Block Difficulty Change

**Definition**

The latest change in network difficulty. Difficulty represents how hard it is to find a hash that meets the protocol-designated requirement (i.e., the difficulty of finding a new block). The requirement is unique to each applicable cryptocurrency protocol. Difficulty is adjusted periodically by the protocol as a function of how much hashing power is being deployed by miners.

**Dictionary**

| Name                    | MetricID                  | Category | Sub-category     | Type  | Unit       | Interval |
| ----------------------- | ------------------------- | -------- | ---------------- | ----- | ---------- | -------- |
| Block Difficulty Change | block\_difficulty\_change | KRI      | Block Attributes | Delta | Difficulty | 1 block  |

**Methodology**

Difficulty is a protocol-defined metric that can be obtained natively. As such, the methodology is handled by the protocol. Difficulty change is calculated by subtracting the current block difficulty by the difficulty of the previous block.

**Available Assets**&#x20;

Bitcoin (BTC), _Ethereum (ETH)\*_

_\* since the move to Proof of Stake on 9/15/2022, Ethereum no longer has a block difficulty. Historical data for this metric is available for ETH_

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_difficulty&pretty=true" %}
