# Mean Tx Fee (native units)

## Definition

The mean fee per transaction in native units that interval.

| Name                       | MetricID   | Category         | Subcategory | Type | Unit         | Interval      |
| -------------------------- | ---------- | ---------------- | ----------- | ---- | ------------ | ------------- |
| Mean Tx Fee (native units) | FeeMeanNtv | Fees and revenue | Fees        | Mean | Native units | 1 day, 1 hour |

## Details

* 0-fee transactions are included
* Computed as FeeTotNtv / TxCnt
* If there were no transactions that interval, this metric isn’t computed

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeMeanNtv" %}
