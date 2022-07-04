---
description: /timeseries/asset-metrics
---

# Uncle Blocks Cnt

## Definition

The sum count of uncle blocks mined in that interval.

## Dictionary

| Name             | MetricID  | Category      | Subcategory | Type  | Unit   | Interval       |
| ---------------- | --------- | ------------- | ----------- | ----- | ------ | -------------- |
| Uncle Blocks Cnt | BlkUncCnt | Network Usage | Blocks      | Count | Uncles | 1 block, 1 day |

## Details

* Uncle Blocks (also known as Ommer Blocks) are an intrinsic feature of Ethereum.
* Unlike Bitcoin, Ethereum does not discard blocks in situations where multiple miners find a valid block of the same height.
* Instead, Ethereum rewards secondary miners with so-called Uncle Blocks, which effectively represent a share of the work, as well as the reward, of processing transactions.
* Uncle blocks are not included in the asset’s main chain but are referenced by main chain blocks. Both the main chain block and uncle block miners get an extra reward for this.

## Asset-Specific Details

* Only available for ETH and ETC

## Release History

* Released in the 4.3 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/BlkUncCnt" %}
