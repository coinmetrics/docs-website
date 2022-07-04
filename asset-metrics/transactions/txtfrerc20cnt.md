# ERC-20 Xfer Cnt

## Definition

The sum count of ERC-20 transfers in that interval. Only non-zero transfers between two distinct addresses are counted. Contracts that contain all of the following are considered to be ERC-20 contracts: the balanceOf function, the transfer function, and the Transfer event hash.

| Name            | MetricID      | Category     | Subcategory | Type | Unit      | Interval |
| --------------- | ------------- | ------------ | ----------- | ---- | --------- | -------- |
| ERC-20 Xfer Cnt | TxTfrERC20Cnt | Transactions | Transfers   | Sum  | Transfers | 1 day    |

## Details

* This metric uses the ERC-20 specification Transfer event as the definition for ERC-20 transfer and only looks for transfers emitted by contracts detected as ERC-20 following the criteria outlined in Contracts, ERC-20, count.
* Full compliance with the ERC-20 standard is not required as only few ERC-20 tokens attain it. We therefore look for the bare minimum methods and events necessary for wallet integration of the token: balanceOf and transfer functions as well as the Transfer event. If a contract’s code has all of the following markers, it is considered to be ERC-20:
  * Signature of the balanceOf function: 6370a082311461
  * Signature of the transfer function: 63a9059cbb1461
  * Hash of the transfer event ddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrERC20Cnt" %}
