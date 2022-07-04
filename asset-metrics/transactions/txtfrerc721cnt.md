# ERC-721 Xfer Cnt

## Definition

The sum count of ERC-721 transfers in that interval. Only transfers between two distinct addresses are counted. ERC-165 is used to determine a contract’s compliance with ERC-721.

| Name             | MetricID       | Category     | Subcategory | Type | Unit      | Interval |
| ---------------- | -------------- | ------------ | ----------- | ---- | --------- | -------- |
| ERC-721 Xfer Cnt | TxTfrERC721Cnt | Transactions | Transfers   | Sum  | Transfers | 1 day    |

## Details

* This metric uses the ERC-721 specification Transfer event as definition for ERC-721 transfer.
* ERC-721 contracts are detected if they implement the ERC-165-compatible interface defined in the ERC-721 specification using the procedure specified in the ERC-165 specification.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrERC721Cnt" %}
