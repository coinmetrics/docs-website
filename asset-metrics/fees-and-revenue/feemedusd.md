# Median Tx Fee (USD)

## Definition

The USD value of the median fee per transaction that day.

| Name                | MetricID  | Category         | Subcategory | Type   | Unit | Interval |
| ------------------- | --------- | ---------------- | ----------- | ------ | ---- | -------- |
| Median Tx Fee (USD) | FeeMedUSD | Fees and revenue | Fees        | Median | USD  | 1 day    |

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

