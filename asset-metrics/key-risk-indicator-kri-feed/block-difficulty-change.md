# Block Difficulty Change

**Definition**

The latest change in network difficulty. Difficulty represents how hard it is to find a hash that meets the protocol-designated requirement (i.e., the difficulty of finding a new block). The requirement is unique to each applicable cryptocurrency protocol. Difficulty is adjusted periodically by the protocol as a function of how much hashing power is being deployed by miners.

**Dictionary**

<table data-header-hidden><thead><tr><th width="165"></th><th width="210"></th><th width="116"></th><th width="141"></th><th></th><th width="107"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Block Difficulty Change</td><td>block_difficulty_change</td><td>KRI</td><td>Block Attributes</td><td>Delta</td><td>Difficulty</td><td>1 block</td></tr></tbody></table>

**Methodology**

Difficulty is a protocol-defined metric that can be obtained natively. As such, the methodology is handled by the protocol. Difficulty change is calculated by subtracting the current block difficulty by the difficulty of the previous block.

**Available Assets**&#x20;

Bitcoin (BTC), _Ethereum (ETH)\*_

_\* since the move to Proof of Stake on 9/15/2022, Ethereum no longer has a block difficulty. Historical data for this metric is available for ETH_

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_difficulty&pretty=true" %}
