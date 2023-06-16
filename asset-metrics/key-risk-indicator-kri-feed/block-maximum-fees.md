# Block Maximum Fees

**Definition**

Mined block's max transaction fee in native units.

**Dictionary**

<table data-header-hidden><thead><tr><th width="165"></th><th width="210"></th><th width="116"></th><th width="141"></th><th></th><th width="107"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Block Maximum Fees</td><td>block_fee_max</td><td>KRI</td><td>Block Attributes</td><td>Max</td><td>Native Currency</td><td>1 block</td></tr></tbody></table>

**Methodology**

The most recently-mined block is evaluated and the maximum of fees in that block is computed.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&metrics=block_fee_max&pretty=true" %}
