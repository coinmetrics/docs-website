# Miner Revenue from Fees (%)

## Definition

The percentage of miner revenue derived from fees that interval. This is equal to the fees divided by the miner revenue.

| Name                        | MetricID  | Category         | Subcategory | Type       | Unit          | Interval |
| --------------------------- | --------- | ---------------- | ----------- | ---------- | ------------- | -------- |
| Miner Revenue from Fees (%) | FeeRevPct | Fees and revenue | Fees        | Percentage | Dimensionless | 1 day    |

## Details

* Computed as 100 \* FeeTotNtv / RevNtv

## Release History

* Released in the 1.0 release of NDP

## Interpretation

For blockchains aiming to retain a limited supply by weaning themselves off an issuance-based validator subsidy, fees are expected to be a critical part of the long-term security model. This metric gives you an indication of how prepared a blockchain is to transition from an issuance-based compensation model for validators to a fee-based model.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeRevPct" %}
