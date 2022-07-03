# Mean Gas Used per Tx

## Definition

The mean gas used (i.e., paid) per transaction that day.

| Name                 | MetricID      | Category         | Subcategory | Type | Unit | Interval       |
| -------------------- | ------------- | ---------------- | ----------- | ---- | ---- | -------------- |
| Mean Gas Used per Tx | GasUsedTxMean | Fees and revenue | Fees        | Mean | Gas  | 1 block, 1 day |

## Details

* Computed as GasUsedTx / TxCnt
* Gas is a dimensionless unit measuring the computational cost of operations for ETH-based assets. Each transaction uses gas when being processed.

## Asset-Specific Details

* Only relevant for ETH and ETC.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/GasUsedTxMean" %}
