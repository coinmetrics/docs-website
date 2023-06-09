# Consecutive Empty Blocks

**Definition**

The count of consecutive empty blocks captured within the most-recent 1-minute interval.

**Dictionary**

<table data-header-hidden><thead><tr><th width="170"></th><th width="177"></th><th width="107"></th><th width="106"></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Sub-category</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Consecutive Empty Blocks</td><td>block_count_consecutive_empty</td><td>KRI</td><td>Empty Blocks</td><td>Sum</td><td>Count of  Blocks</td><td>1b</td></tr></tbody></table>

**Methodology**

The set of most recently-processed blocks within a 1-minute window are captured and their contents are evaluated. Every consecutive empty block within the window is counted. For Ethereum, the maximum possible value this metric is 5 given that the time between blocks in that network is fixed at 12 seconds.

**Available Assets**

Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=eth&frequency=1b&metrics=block_count_consecutive_empty&pretty=true" %}
