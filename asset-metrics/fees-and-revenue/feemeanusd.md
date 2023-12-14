# Mean Tx Fee (USD)

## Definition

The USD value of the mean fee per transaction that interval.

| Name              | MetricID   | Category         | Subcategory | Type | Unit | Interval      |
| ----------------- | ---------- | ---------------- | ----------- | ---- | ---- | ------------- |
| Mean Tx Fee (USD) | FeeMeanUSD | Fees and revenue | Fees        | Mean | USD  | 1 day, 1 hour |

## Details

* 0-fee transactions are included
* Computed as FeeMeanNtv \* PriceUSD
* The price used is the daily close price
* If there were no transactions that interval, this metric isn’t computed

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeMeanUSD" %}
