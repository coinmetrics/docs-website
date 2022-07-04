# Tx Gas Limit

## Definition

The sum gas limit of all transactions that day.

| Name         | MetricID | Category         | Subcategory | Type | Unit | Interval       |
| ------------ | -------- | ---------------- | ----------- | ---- | ---- | -------------- |
| Tx Gas Limit | GasLmtTx | Fees and revenue | Fees        | Sum  | Gas  | 1 block, 1 day |

## Details

* Gas is a dimensionless unit measuring the computational cost of operations for ETH-based assets. Each transaction uses gas when being processed. As it’s impossible to know how much gas every transaction will use before executing it, each transaction specifies a gas limit it’s willing to use.

## Asset-Specific Details

* Only relevant for ETH and ETC.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/GasLmtTx" %}
