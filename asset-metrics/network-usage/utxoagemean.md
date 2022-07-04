# UTXO Mean Age (Days)

## Definition

The simple average age in full days of all unspent transaction outputs. \


| Name                 | MetricID    | Category      | Subcategory | Type | Unit | Interval |
| -------------------- | ----------- | ------------- | ----------- | ---- | ---- | -------- |
| UTXO Mean Age (Days) | UTXOAgeMean | Network Usage | UTXOs       | Mean | Days | 1 day    |

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Interpretation

This metric calculates the average number of days an asset (e.g, BTC) is held between transactions. Note that it may be less robust to outliers than median and could be skewed by older addresses.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/UTXOAgeMean" %}
