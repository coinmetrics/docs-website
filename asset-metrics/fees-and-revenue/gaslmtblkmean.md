# Mean Block Gas Limit

## Definition

The mean gas limit per block that day.

| Name                 | MetricID      | Category         | Subcategory | Type | Unit | Interval |
| -------------------- | ------------- | ---------------- | ----------- | ---- | ---- | -------- |
| Mean Block Gas Limit | GasLmtBlkMean | Fees and revenue | Fees        | Mean | Gas  | 1 day    |

## Details

* Computed as GasLmtBlk / BlkCnt
* Gas is a dimensionless unit measuring the computational cost of operations for ETH-based assets. Each transaction spends gas when being processed.

## Asset-Specific details

* Only relevant for ETH and ETC.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/GasLmtBlkMean" %}
