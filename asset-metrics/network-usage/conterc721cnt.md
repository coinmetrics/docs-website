# ERC-721 Contracts Cnt

## Definition

The sum count of unique contracts implementing the ERC-721 standard that exist in the ledger at the end of the interval. A contract is a special address that contains and can execute code. ERC-165 is used to determine a contract’s compliance with ERC-721.

| Name                  | MetricID      | Category      | Subcategory | Type | Unit      | Interval |
| --------------------- | ------------- | ------------- | ----------- | ---- | --------- | -------- |
| ERC-721 Contracts Cnt | ContERC721Cnt | Network Usage | Contracts   | Sum  | Contracts | 1 day    |

## Details

* Contracts with no balance in native units are counted.
* ERC-721 contracts are detected if they implement the ERC-165-compatible interface defined in the ERC-721 specification using the procedure specified in the[ ERC-165 specification.](https://eips.ethereum.org/EIPS/eip-165)

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ContERC721Cnt" %}
