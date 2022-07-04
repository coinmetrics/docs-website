---
description: /timeseries/asset-metrics
---

# Sum Block Size (in bytes)

## Definition

The sum of the size (in bytes) of all blocks created that interval.

| Name                      | MetricID    | Category      | Subcategory | Type | Unit  | Interval |
| ------------------------- | ----------- | ------------- | ----------- | ---- | ----- | -------- |
| Sum Block Size (in bytes) | BlkSizeByte | Network Usage | Blocks      | Sum  | Bytes | 1d, 1b   |

## Details

* Only mainchain (non-orphaned/uncles) blocks are counted.
* For chains that use median time, the day is defined using it, otherwise, it’s defined using the block’s timestamps.

## Asset-Specific Details

* This metric is not available for all assets, as some node’s RPC APIs do not expose the size of the blocks.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/BlkSizeByte" %}
