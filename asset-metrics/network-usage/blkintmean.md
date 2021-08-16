---
description: /timeseries/asset-metrics
---

# Mean Block Interval \(seconds\)

## Definition

The mean time \(in seconds\) between all the blocks created that interval.

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Mean Time Block | BlkIntMean | Network Usage | Blocks | Mean | Seconds | 1 block, 1 day |

## Details

* Only mainchain \(non-orphaned/uncles\) blocks are counted.
* For chains that use median time, the day is defined using it, otherwise, it’s defined using the block’s timestamps.
* The absolute interval is used \(if block n+1 has a timestamp lower than block n, we use the absolute value of the difference in timestamps, see examples\).

## Example

If for a day, the blocks are:

![](../../.gitbook/assets/screen-shot-2020-12-13-at-10.45.13-pm.png)

The value of BlkIntMean would be \(120 + 20 + 160 + 60\) / 4 = 90 seconds

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Blockchains with shorter block time \(and hence a larger sample size per day\) will typically have less variance in mean block interval.

## Available for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/BlkIntMean" %}
