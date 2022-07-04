# Completion Time

## Definition

The time that the last metric for the asset was calculated, indicating that all metrics for that asset have been calculated  \


| Name             | MetricID               | Category     | Subcategory | Type      | Unit         | Interval |
| ---------------- | ---------------------- | ------------ | ----------- | --------- | ------------ | -------- |
| Completion Time  | AssetEODCompletionTime | Availability | NA          | Timestamp | EPOC seconds | 1d       |

## Details

Our metric calculation begins at 00:00 UTC.  Given that our asset metrics finish calculating at different times each asset AND each asset's last metric calculation will occur at different times, we've created a metric so users can determine when the entire metric set for a given asset is fully calculated (has completed its daily processing).&#x20;

The result provides a "time" string in EPOC seconds. &#x20;

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/AssetEODCompletionTime" %}
