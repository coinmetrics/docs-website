# ERC-721 Tx Cnt

## Definition

The sum count of transactions that resulted in any ERC-721 activity in that interval. Only transfers between two distinct addresses are counted. ERC-165 is used to determine a contract’s compliance with ERC-721. Only Transfer or Approval events are counted as activity. If a transaction results in more than 1 transfer or approval, it’s only counted once.

| Name           | MetricID    | Category     | Subcategory  | Type | Unit         | Interval |
| -------------- | ----------- | ------------ | ------------ | ---- | ------------ | -------- |
| ERC-721 Tx Cnt | TxERC721Cnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* This metric counts only the ERC-721 specification Transfer and Approval events emitted by ERC-721 compliant contracts.
* ERC-721 contracts are detected if they implement the ERC-165-compatible interface defined in the ERC-721 specification using the procedure specified in the ERC-165 specification.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxERC721Cnt" %}
