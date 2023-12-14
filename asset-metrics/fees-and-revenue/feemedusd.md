# Median Tx Fee (USD)

## Definition

The USD value of the median fee per transaction that day.

<table><thead><tr><th>Name</th><th width="203">MetricID</th><th width="150">Category</th><th width="210">Subcategory</th><th>Type</th><th>Unit</th><th>Interval</th></tr></thead><tbody><tr><td>Median Tx Fee (USD)</td><td>FeeMedUSD</td><td>Fees and revenue</td><td>Fees </td><td>Median</td><td>USD</td><td>1 day, 1 hour</td></tr></tbody></table>

## Details

* Computed as FeeMedNtv \* PriceUSD
* Price used is the daily close price
* 0-fee transactions are included
* If there were no transactions that day, this metric isn’t computed
* If there’s an even number of fees, the median is computed by averaging the middle values of the sorted fees.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeMedUSD" %}

