---
description: /timeseries/asset-metrics
---

# Uncle Reward (USD)

## Definition

The sum USD value rewarded to miners for creating and including uncle blocks in that interval. This includes the uncle inclusion reward (for the main chain block miner) and the uncle rewards (for the uncle block miners).

## Dictionary

| Name               | MetricID     | Category      | Subcategory | Type | Unit         | Interval       |
| ------------------ | ------------ | ------------- | ----------- | ---- | ------------ | -------------- |
| Uncle Reward (USD) | BlkUncRwdUSD | Network Usage | Blocks      | Sum  | Native Units | 1 block, 1 day |

## Details

* Uncle Blocks (also known as Ommer Blocks) are an intrinsic feature of Ethereum.
* Unlike Bitcoin, Ethereum does not discard blocks in situations where multiple miners find a valid block of the same height.
* Instead, Ethereum rewards secondary miners with so-called Uncle Blocks, which effectively represent a share of the work, as well as the reward, of processing transactions.
* Uncle blocks are not included in the asset’s main chain but are referenced by main chain blocks. Both the main chain block and uncle block miners get an extra reward for this.

## Asset-Specific Details

* This metric is only relevant to ETH and ETC

## Release History

* Released in the 4.3 release of NDP
* Deprecated post the Ethereum Merge

## See Also

* [Uncle Blocks Cnt](https://docs.coinmetrics.io/asset-metrics/network-usage/blkunccnt)
* [Miner Revenue from Uncle Blocks (%)](https://docs.coinmetrics.io/asset-metrics/network-usage/blkuncrevpct)
* [Uncle Reward (native units)](https://docs.coinmetrics.io/asset-metrics/network-usage/blkuncrwd)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/BlkUncRwdUSD" %}
