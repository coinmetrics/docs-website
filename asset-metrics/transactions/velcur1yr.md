# 1 Year Current Supply Velocity

## Definition

The ratio of the value transferred (i.e., the aggregate "size" of all transfers) in the trailing 1 year divided by the current supply on that day. It can be thought of as a rate of turnover -- the number of times that an average native unit has been transferred in the past 1 year.

| Name                           | MetricID  | Category     | Subcategory | Type  | Unit          | Interval |
| ------------------------------ | --------- | ------------ | ----------- | ----- | ------------- | -------- |
| 1 Year Current Supply Velocity | VelCur1yr | Transactions | Velocity    | Ratio | Dimensionless | 1 year   |

## Details

* [Xfer'd Value (native units)](txtfrvalntv.md) for trailing 1 year / [Current Supply (native units)](../supply/splycur.md)

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Velocity​ is a measurement of the rate at which an asset is exchanged. It can be thought of as a rate of turnover, or, in other words, the number of times that an average unit of an asset has been transferred within the last year. Our Adjusted Velocity metric removes noise and other artifacts from the transfer value in the numerator.

## See Also

* [1 Year Current Supply Velocity, Adj](velcuradj1yr.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/VelCur1yr" %}
