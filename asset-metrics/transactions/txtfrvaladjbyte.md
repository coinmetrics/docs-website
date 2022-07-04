# Per Byte Xfer'd Mean Val, Adj (USD)

## Definition

The mean USD value per byte transferred for all transfers that day removing noise and certain artifacts.

| Name                                | MetricID        | Category     | Subcategory | Type | Unit | Interval |
| ----------------------------------- | --------------- | ------------ | ----------- | ---- | ---- | -------- |
| Per Byte Xfer'd Mean Val, Adj (USD) | TxTfrValAdjByte | Transactions | Transfers   | Sum  | USD  | 1 day    |

## Details

* Computed as TxTfrValAdjNtv / BlkSizeByte
* This metric estimates the economical density of an asset.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValAdjByte" %}
