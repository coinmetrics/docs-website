# Total Fees (USD)

## Definition

The sum USD value of all fees paid to miners, transaction validators, stakers and/or block producers that interval. In certain cryptonetworks, fees might be burned (destroyed), but they are still accounted for in this metric.

| Name             | MetricID  | Category         | Subcategory | Type | Unit | Interval      |
| ---------------- | --------- | ---------------- | ----------- | ---- | ---- | ------------- |
| Total Fees (USD) | FeeTotUSD | Fees and revenue | Fees        | Sum  | USD  | 1 day, 1 hour |

## Details

* Computed as FeeTotNtv \* PriceUSD
* Price used is daily close price.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeTotUSD" %}
