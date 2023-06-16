# Block Count by Same Miner

**Definition**

The number of blocks mined by the same miner in the past 6 blocks.

**Dictionary**

<table data-header-hidden><thead><tr><th width="179"></th><th width="282"></th><th width="112"></th><th width="142"></th><th></th><th width="155"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Block Count by Same Miner</td><td>block_count_by_same_miner_6b</td><td>KRI</td><td>Block Attributes</td><td>Sum</td><td>Coun of Blocks</td><td>1b</td></tr></tbody></table>

**Methodology**

The 6 blocks from the tip of the blockchain (including the most recent block) are assessed. Coin Metric employs a proprietary entity clustering methodology in order to identify major mining pools & miners. The coinbase output field used by miners to self-identify is also used to help assess miner identities.

**Available Assets**

Bitcoin (BTC), _Ethereum (ETH)\*._

_\* Historical data covering the pre-merge timeframe only (up to 9/15/2022). With the merge ETH switched from Proof of Work and miners to Proof of Stake and validators meaning the network no longer has any miners as of the merge date._

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&metrics=block_count_by_same_miner_6b&pretty=true" %}
