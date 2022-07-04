# Token Xfer Cnt

## Definition

The sum count of token (ERC-20 or ERC-721) transfers in that interval. Only non-zero transfers between two distinct addresses are counted. All ERC-20 or ERC-721 contracts are counted, as long as their transfers follow the ERC-20 or ERC-721 specification.

| Name           | MetricID    | Category     | Subcategory | Type | Unit      | Interval |
| -------------- | ----------- | ------------ | ----------- | ---- | --------- | -------- |
| Token Xfer Cnt | TxTfrTknCnt | Transactions | Transfers   | Sum  | Transfers | 1 day    |

## Details

* This metric uses the ERC-20 or ERC-721 specification Transfer event as definition for ERC-20 transfer.

## Asset-Specific Details

* This metric is only available for ETH and ETC.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrTknCnt" %}
