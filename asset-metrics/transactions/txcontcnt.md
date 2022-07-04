# Tx Invoking Contract Cnt

## Definition

The sum count of transactions that invoked a contract in that interval. Failed transactions are counted but internal transactions are not (i.e., only the parent transaction is counted). A contract is a special address that contains and can execute code.

| Name                     | MetricID  | Category     | Subcategory  | Type | Unit         | Interval |
| ------------------------ | --------- | ------------ | ------------ | ---- | ------------ | -------- |
| Tx Invoking Contract Cnt | TxContCnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* Failed transactions are counted.
* Contract creations are counted.
* Internal transactions are not counted (i.e., only the parent transaction is counted).

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxContCnt" %}
