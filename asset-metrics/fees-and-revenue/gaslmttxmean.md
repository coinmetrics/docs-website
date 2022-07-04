# Mean Gas Limit per Tx

## Definition

The mean gas limit per transaction that day.

| Name                  | MetricID     | Category         | Subcategory | Type | Unit | Interval       |
| --------------------- | ------------ | ---------------- | ----------- | ---- | ---- | -------------- |
| Mean Gas Limit per Tx | GasLmtTxMean | Fees and revenue | Fees        | Mean | Gas  | 1 block, 1 day |

## Details

* Computed as GasLmtTx / TxCnt
* Gas is a dimensionless unit measuring the computational cost of operations for ETH-based assets. Each transaction uses gas when being processed. As it’s impossible to know how much gas every transaction will use before executing it, each transaction specifies a gas limit it’s willing to use.

## Asset-Specific Details

* Only relevant for ETH and ETC.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/GasLmtTxMean" %}
