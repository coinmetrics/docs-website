# Empty Blocks

**Definition**

The number of empty blocks in the past 6 blocks. Empty blocks are blocks that do not contain any transactions other than the coinbase. They may be a result of no underlying economic activity leading to no user transactions to mine, or they can be a result of deliberate action by miners. As explored [here](http://dspace.unive.it/handle/10579/15163), there are incentives for miners to work on empty blocks. Since empty blocks consume less space, they can be propagated faster. Additionally, empty blocks can increase fees in times of vibrant network activity, as unprocessed transactions accumulate. If persistent, empty blocks can be very disruptive to a network.

**Dictionary**

<table data-header-hidden><thead><tr><th width="173"></th><th width="213"></th><th width="110"></th><th width="143"></th><th></th><th width="174"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Empty Blocks</td><td>block_count_empty_6b</td><td>KRI</td><td>Empty Blocks</td><td>Sum</td><td>Number of blocks</td><td>1 block</td></tr></tbody></table>

**Methodology**

The 6 blocks from the tip of the blockchain (including the most recent block) are assessed, and the number of empty blocks is counted.

**Available Assets**

Bitcoin (BTC), _Ethereum (ETH)\*_

_\*Ethereum data is available up to the merge on 9/15/2022. After that date Ethereum data for this metric is not available_

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_count_empty_6b&pretty=true" %}
