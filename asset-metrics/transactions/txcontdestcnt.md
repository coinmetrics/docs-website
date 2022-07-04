# Destroyed Contracts Cnt

## Defintion

The sum count of contracts successfully destroyed across all transactions in that interval. A contract is a special address that contains and can execute code.

| Name                    | MetricID      | Category     | Subcategory | Type | Unit      | Interval |
| ----------------------- | ------------- | ------------ | ----------- | ---- | --------- | -------- |
| Destroyed Contracts Cnt | TxContDestCnt | Transactions | Internal    | Sum  | Contracts | 1 day    |

## Details

* If a transaction destroys several contracts, each destruction is counted once.
* Not all contract protocols allow contract destruction.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxContDestCnt" %}
