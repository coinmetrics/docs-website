---
description: /timeseries/asset-metrics
---

# Block Height

## Definition

The count of blocks from the genesis \(first\) block to the last block of that interval on the main chain \(in other words, the total number of blocks ever created and included on the chain\).

## Dictionary

| Name | MetriID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Block Height | BlkHgt | Network Usage | Blocks | Sum | Blocks | 1 block, 1 day |

## Details

* Only mainchain \(non-orphaned/uncles\) blocks are counted.
* For chains that use median time, the day is defined using it, otherwise, it’s defined using the block’s timestamps

## Release History

* Released in the 4.3 release of NDP

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/BlkHgt" %}

