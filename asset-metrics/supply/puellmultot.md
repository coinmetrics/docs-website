# Puell Multiple, Total Issuance

## Definition

The ratio of the USD value of all new issuance during the period to the 365-day moving average of the USD value of all new issuance.

| Name                           | MetricID    | Category | Subcategory | Type  | Unit          | Interval |
| ------------------------------ | ----------- | -------- | ----------- | ----- | ------------- | -------- |
| Puell Multiple, Total Issuance | PuellMulTot | Supply   | Issuance    | Ratio | Dimensionless | 365 days |

## Details

* Computed as IssTotUSD/ma365(IssTotUSD)
* Created by David Puell

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

The Puell Multiple provides insight into market cycles from a mining revenue perspective. Because miners are sometimes considered compulsory sellers given their fixed costs (e.g., equipment, electricity), this metric provides insight into the supply side of a cryptoasset's economy.   The idea being, that periods where the Puell Multiple is extremely low could be buying opportunities for investors, and periods where it is extremely high could indicate a profit-taking/selling opportunities.&#x20;

## See Also

* [Puell Multiple, Revenue](puellmulrev.md)
* [Puell Multiple, Coinbase Issuance](puellmulcont.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/PuellMulTot" %}
