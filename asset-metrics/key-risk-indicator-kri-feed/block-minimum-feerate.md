# Block Minimum Feerate

**Definition**

A block's minimum transaction feerate. For Bitcoin this is measured in sats/vbyte. For Ethereum this measures the gas price in Gwei

**Dictionary**

<table data-header-hidden><thead><tr><th width="180"></th><th width="210"></th><th width="116"></th><th width="141"></th><th></th><th width="107"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Block Minimum Feerate</td><td>block_feerate_min</td><td>KRI</td><td>Block Attributes</td><td>Min</td><td>Native feerate</td><td>1 block</td></tr></tbody></table>

**Methodology**

The most recent block is evaluated and the minimum feerate in that block is computed.

**Available Assets**&#x20;

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc,eth&frequency=1b&metrics=block_feerate_min&pretty=true" %}
