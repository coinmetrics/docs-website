# Mean Xfer'd Days Destroyed

## Definition

The mean per transaction of the sum of all native units transferred multiplied by the sum of days since those native units were last transferred that interval.

| Name                       | MetricID           | Category     | Subcategory    | Type | Unit          | Interval |
| -------------------------- | ------------------ | ------------ | -------------- | ---- | ------------- | -------- |
| Mean Xfer'd Days Destroyed | TxTfrValDayDstMean | Transactions | Transfer value | Mean | Dimensionless | 1 day    |

## Details

* Computed as TxTfrValDayDst / TxCnt

## Asset-Specific Details

* Only available for UTXO chains
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrValDayDstMean" %}
