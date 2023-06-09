# Mempool Size Left 1 Minute

**Definition**

The total size in bytes of all transactions that have left the mempool over the course of a 1-minute aggregation window. The beginning of this time window is noted in the “time” field of the response.&#x20;

**Dictionary**

<table data-header-hidden><thead><tr><th width="162"></th><th width="240"></th><th width="107"></th><th width="144"></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Mempool Size Left 1m</td><td>mempool_size_left_1m</td><td>KRI</td><td>Mempool</td><td>Sum</td><td>bytes</td><td>1m</td></tr></tbody></table>

**Methodology**

The mempool is evaluated and all transactions within are indexed. The size of all transactions that have left the mempool in the previous 1-minute window is summed.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&metrics=mempool_size_left_1m&pretty=true" %}
