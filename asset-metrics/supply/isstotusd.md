# Total Issuance (USD)

## Definition

The sum USD value of all new native units issued that day.

| Name                 | MetricID  | Category | Subcategory | Type | Unit | Interval |
| -------------------- | --------- | -------- | ----------- | ---- | ---- | -------- |
| Total Issuance (USD) | IssTotUSD | Supply   | Issuance    | Sum  | USD  | 1 day    |

## Details

* In this metric, compared to the continuous one, all sources of issuance are taken into account.
* Computed as IssTotNtv \* PriceUSD

## Release History

* Released in the 1.0 release of NDP

## Interpretation

This metric can be understood as miner (or validator) revenue in fiat terms, excluding fees.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/IssTotUSD" %}
