# ERC-20 Tx Cnt

## Definition

The sum count of transactions that resulted in any ERC-20 activity in that interval. Contracts that contain all of the following are considered to be ERC-20 contracts: the balanceOf function, the transfer function, and the Transfer event hash. Only Transfer or Approval events are counted as activity. If a transaction results in more than 1 transfer or approval, it’s only counted once.

| Name          | MetricID   | Category     | Subcategory  | Type | Unit         | Interval |
| ------------- | ---------- | ------------ | ------------ | ---- | ------------ | -------- |
| ERC-20 Tx Cnt | TxERC20Cnt | Transactions | Transactions | Sum  | Transactions | 1 day    |

## Details

* This metric counts only the ERC-20 specification Transfer and Approval events emitted by contracts detected as ERC-20 following the criteria outlined in Contracts, ERC-20, count.
* Full compliance with the ERC-20 standard is not required as only few ERC-20 tokens attain it. We therefore look for the bare minimum methods and events necessary for wallet integration of the token: balanceOf and transfer functions as well as the Transfer event. If a contract’s code has all of the following markers, it is considered to be ERC-20:
  * Signature of the balanceOf function: 6370a082311461
  * Signature of the transfer function: 63a9059cbb1461
  * Hash of the transfer event ddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxERC20Cnt" %}
