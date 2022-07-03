# Mean Tx Fee per Byte (native units)

## Definition

The mean transaction fee per byte of all blocks that interval in native units.

| Name                                | MetricID       | Category         | Subcategory | Type | Unit         | Interval |
| ----------------------------------- | -------------- | ---------------- | ----------- | ---- | ------------ | -------- |
| Mean Tx Fee per Byte (native units) | FeeByteMeanNtv | Fees and Revenue | Fees        | Mean | Native units | 1 day    |

## Details

* 0-fee transactions are included
* Computed as FeeTotNtv / BlkSizeByte
* If there were no transactions that interval, this metric isn’t computed

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeByteMeanNtv" %}
