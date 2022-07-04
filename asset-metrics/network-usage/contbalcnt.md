# Contracts Cnt with Bal > 0

## Definition

The sum count of unique contracts that exist in the ledger and that hold a balance (i.e., own a non-zero amount) of native units at the end of the interval. A contract is a special address that contains and can execute code.

| Name                      | MetricID   | Category            | Subcategory | Type | Unit      | Interval |
| ------------------------- | ---------- | ------------------- | ----------- | ---- | --------- | -------- |
| Contracts Cnt with Bal >0 | ContBalCnt | Blockchain / Ledger | Contracts   | Sum  | Contracts | 1 day    |

## Details

* Contracts with no balance in native units are not counted.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ContBalCnt" %}
