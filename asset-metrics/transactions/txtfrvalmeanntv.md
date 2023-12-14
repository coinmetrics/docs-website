# Mean Tx Size (native units)

## Definition

The sum value of native units transferred divided by the count of transfers (i.e., the mean size of a transfer) between distinct addresses that interval.

| Name                        | MetricID        | Category     | Subcategory    | Type | Unit         | Interval      |
| --------------------------- | --------------- | ------------ | -------------- | ---- | ------------ | ------------- |
| Mean Tx Size (native units) | TxTfrValMeanNtv | Transactions | Transfer value | Mean | Native units | 1 day, 1 hour |

## Details

* Computed as TxTfrValNtv / TxTfrCnt

## Asset-Specific Details

* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValMeanNtv" %}
