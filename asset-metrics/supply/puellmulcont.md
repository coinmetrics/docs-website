# Puell Multiple, Coinbase Issuance

## Definition

The ratio of the USD value of new issuance during the period to the 365-day moving average of the USD value of new issuance. Only those native units that are issued by a protocol-mandated continuous emission schedule are included (i.e., units manually released from escrow or otherwise disbursed are not included).

| Name                              | MetricID     | Category | Subcategory | Type  | Unit          | Interval |
| --------------------------------- | ------------ | -------- | ----------- | ----- | ------------- | -------- |
| Puell Multiple, Coinbase Issuance | PuellMulCont | Supply   | Issuance    | Ratio | Dimensionless | 365 days |

## Details

* Computed as IssContUSD/ma365(IssContUSD)

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

The Puell Multiple provides insight into market cycles from a mining revenue perspective. Because miners are sometimes considered compulsory sellers given their fixed costs (e.g., equipment, electricity), metric provides insight into the supply side of a cryptoasset's economy.   The idea being, that periods where the Puell Multiple is extremely low could be buying opportunities for investors, and periods where it is extremely high could indicate a profit-taking/selling opportunities.&#x20;

## See Also

* [Puell Multiple, Revenue](puellmulrev.md)
* [Puell Multiple, Total Issuance](puellmultot.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/PuellMulCont" %}
