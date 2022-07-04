# Xfer'd by Contract Calls (native units)

## Definition

The sum of all native units transferred by contract calls on that interval. A contract call is the invocation of a contract’s code by another contract or non-contract address. Only successful calls are considered.

| Name                                    | MetricID            | Category     | Subcategory    | Type | Unit         | Interval |
| --------------------------------------- | ------------------- | ------------ | -------------- | ---- | ------------ | -------- |
| Xfer'd by Contract Calls (native units) | TxTfrValContCallNtv | Transactions | Transfer value | Sum  | Native units | 1 day    |

## Details

* Computed as TxTfrValAdjNtv / BlkSizeByte
* This metric estimates the economical density of an asset.

## Release History

* Released in the 4.2 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValContCallNtv" %}
