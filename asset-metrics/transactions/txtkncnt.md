# Token Tx Cnt

## Definition

The sum count of transactions that resulted in any token (ERC-20 or ERC-721) activity in that interval. Only Transfer or Approval events are counted as activity. If a transaction results in more than 1 transfer or approval, it’s only counted once.

| Name         | MetricID | Category     | Subcategory  | Type | Unit         | Interval |
| ------------ | -------- | ------------ | ------------ | ---- | ------------ | -------- |
| Token Tx Cnt | TxTknCnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* This metric counts only the ERC-20 and ERC-721 specification Transfer and Approval events.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTknCnt" %}
