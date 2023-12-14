# Median Tx Fee (native units)

## Definition

The median fee per transaction in native units that interval.

| Name                         | MetricID  | Category         | Subcategory | Type   | Unit         | Interval      |
| ---------------------------- | --------- | ---------------- | ----------- | ------ | ------------ | ------------- |
| Median Tx Fee (native units) | FeeMedNtv | Fees and revenue | Fees        | Median | Native units | 1 day, 1 hour |

## Details

* 0-fee transactions are included
* If there were no transactions that interval, this metric isn’t computed
* If there’s an even number of fees, the median is computed by averaging the middle values of the sorted fees

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FeeMedNtv" %}
