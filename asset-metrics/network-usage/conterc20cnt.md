# ERC-20 Contracts Cnt

## Definition

The sum count of unique ERC-20 contracts that exist on the ledger at the end of the interval. A contract is a special address that contains and can execute code. Contracts that contain all of the following are considered to be ERC-20 contracts: the balanceOf function, the transfer function, and the Transfer event hash.

| Name                 | MetricID     | Category      | Subcategory | Type | Unit      | Interval |
| -------------------- | ------------ | ------------- | ----------- | ---- | --------- | -------- |
| ERC-20 Contracts Cnt | ContERC20Cnt | Network Usage | Contracts   | Sum  | Contracts | 1 day    |

## Details

* Contracts with no balance in native units are counted.
* Full compliance with the ERC-20 standard is not required as only few ERC-20 tokens attain it. We therefore look for the bare minimum methods and events necessary for wallet integration of the token: balanceOf and transfer functions as well as the Transfer event. If a contract’s code has all of the following markers, it is considered to be ERC-20:
*
  * Signature of the balanceOf function: 6370a082311461
  * Signature of the transfer function: 63a9059cbb1461
  * Hash of the transfer event ddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ContERC20Cnt" %}
