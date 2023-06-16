# Block Mean Feerate

**Definition**

A block's mean transaction feerate. For Bitcoin this is measured in sats/vbyte. For Ethereum this measures the gas price in Gwei

**Dictionary**

<table data-header-hidden><thead><tr><th width="180"></th><th width="210"></th><th width="116"></th><th width="141"></th><th></th><th width="107"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Block Mean Feerate</td><td>block_feerate_mean</td><td>KRI</td><td>Block Attributes</td><td>Mean</td><td>Native feerate</td><td>1 block</td></tr></tbody></table>

**Methodology**

The most recent block is evaluated and the mean feerate in that block is computed.

**Available Assets**&#x20;

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc,eth&frequency=1b&metrics=block_feerate_mean&pretty=true" %}
