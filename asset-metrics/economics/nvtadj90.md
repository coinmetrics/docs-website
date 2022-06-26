# NVT 90-day Moving Avg

## Definition

The ratio of the network value (or market capitalization, current supply) to the 90-day moving average of the adjusted transfer value. Also referred to as NVT.

| Name                  | MetricID | Category  | Subcategory | Type  | Unit          | Interval |
| --------------------- | -------- | --------- | ----------- | ----- | ------------- | -------- |
| NVT 90-day Moving Avg | NVTAdj90 | Valuation | Valuation   | Ratio | Dimensionless | 1 day    |

## Details

* Computed as the current market cap over the 90-day moving average of USD adjusted transfer volume.
* Inspired by Kalichkin’s work.  [Kalichkin (2018a)](https://medium.com/cryptolab/https-medium-com-kalichkin-rethinking-nvt-ratio-2cf810df0ab0) extended the idea behind the NVT ratio by introducing additional smoothing to correct for certain shortcomings in the original formulation that prevent it from being used as a real-time trading indicator.



## Release History

* Released in the 1.0 release of NDP

## See Also

* [NVT](nvtadj.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/NVTAdj90" %}
