# Xfer'd by Contract Calls (USD)

## Definition

The sum USD value transferred by contract calls on that interval. A contract call is the invocation of a contract’s code by another contract or non-contract address. Only successful calls are considered.

| Name                           | MetricID            | Category     | Subcategory    | Type | Unit         | Interval |
| ------------------------------ | ------------------- | ------------ | -------------- | ---- | ------------ | -------- |
| Xfer'd by Contract Calls (USD) | TxTfrValContCallUSD | Transactions | Transfer value | Sum  | Native units | 1 day    |

## Details

* Computed as TxTfrValAdjUSD / BlkSizeByte
* This metric estimates the economical density of an asset.

## Release History

* Released in the 4.2 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValContCallUSD" %}
