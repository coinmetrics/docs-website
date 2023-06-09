# Mean Feerate Mempool

**Definition**

The mean feerate (fee/vsize) of all mempool transactions, in native units per byte. Virtual Size (vsize) is a unit used to measure the size of a bitcoin transaction after the activation of SegWit.

**Dictionary**

<table data-header-hidden><thead><tr><th width="241"></th><th width="221"></th><th width="112"></th><th width="141"></th><th></th><th width="114"></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Mean Feerate Mempool</td><td>mempool_feerate_mean</td><td>KRI</td><td>Mempool</td><td>Mean</td><td>fee/vsize</td><td>1m</td></tr></tbody></table>

**Methodology**

The mempool is evaluated and the feerate (fee/vsize) attached to all transactions is aggregated. The mean feerate of all transactions is then calculated.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_feerate_mean&pretty=true" %}
