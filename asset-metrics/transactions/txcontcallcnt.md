# Contracts Executed Cnt

## Definition

The sum count of contract calls executed across all transactions in that interval. A contract call is the invocation of a contract’s code by another contract or non-contract address. Failed invocations are counted. A single transaction can result in multiple contract calls.

| Name                   | MetricID      | Category     | Subcategory | Type | Unit  | Interval |
| ---------------------- | ------------- | ------------ | ----------- | ---- | ----- | -------- |
| Contracts Executed Cnt | TxContCallCnt | Transactions | Internal    | Sum  | Calls | 1 day    |

## Details

* Failed transactions are included.
* Contract creations and destructions are not included.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxContCallCnt" %}
