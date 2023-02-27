# Empty Blocks

**Definition**

The number of empty blocks in the past 6 blocks. Empty blocks are blocks that do not contain any transactions other than the coinbase. They may be a result of no underlying economic activity leading to no user transactions to mine, or they can be a result of deliberate action by miners. As explored [here](http://dspace.unive.it/handle/10579/15163), there are incentives for miners to work on empty blocks. Since empty blocks consume less space, they can be propagated faster. Additionally, empty blocks can increase fees in times of vibrant network activity, as unprocessed transactions accumulate. If persistent, empty blocks can be very disruptive to a network.

**Dictionary**

| Name         | MetricID                | Category | Sub-category | Type | Unit             | Interval |
| ------------ | ----------------------- | -------- | ------------ | ---- | ---------------- | -------- |
| Empty Blocks | block\_count\_empty\_6b | KRI      | Empty Blocks | Sum  | Number of blocks | 1 block  |

**Methodology**

The 6 blocks from the tip of the blockchain (including the most recent block) are assessed, and the number of empty blocks is counted.

**Available Assets**

Bitcoin (BTC), _Ethereum (ETH)\*_

_\*Ethereum data is available up to the merge on 9/15/2022. After that date Ethereum data for this metric is not available_

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_count_empty_6b&pretty=true" %}
