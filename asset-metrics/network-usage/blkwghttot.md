# Sum Block Weight

## Definition

The mean weight of all blocks created that interval. Weight is a dimensionless measure of a block’s “size”. It is only applicable for chains that use SegWit \(segregated witness\).

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Sum Block Weight | BlkWghtTot | Network Usage | Blocks | Mean | Dimensionless | 1 day |

## Details

* Only mainchain \(non-orphaned/uncles\) blocks are counted.
* For chains that use median time, the day is defined using it, otherwise, it’s defined using the block’s timestamps.

## Asset-Specific Details

* This metric is only available for assets that support SegWit.

## Release History

* Released in the 4.9 release of NDP

## Interpretation

Block weight is useful to determine how used a chain is.

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/BlkWghtTot" %}



