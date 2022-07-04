# Total Issuance (native units)

## Definition

The sum of all new native units issued that day.

| Name                          | MetricID  | Category | Subcategory | Type | Unit         | Interval |
| ----------------------------- | --------- | -------- | ----------- | ---- | ------------ | -------- |
| Total Issuance (native units) | IssTotNtv | Supply   | Issuance    | Sum  | Native units | 1 day    |

## Details

* In this metric, compared to the continuous one, all sources of issuance are taken into account.
* This metric is the gross issuance: if in the same day, 100 units are issued and 10 burned, this metric’s value will be 100, not 90 (which would be the net issuance).

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/IssTotNtv" %}
