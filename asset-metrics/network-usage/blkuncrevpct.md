---
description: /timeseries/asset-metrics
---

# Miner Revenue from Uncle Blocks (%)

## Definition

The percentage of miner revenue exclusively derived from creating and including uncle blocks in that interval. This is equal to the sum of the uncle inclusion reward (for the main chain block miner) and the uncle rewards (for the uncle block miners) divided by the miner revenue.

| Name                                | MetricID     | Category      | Subcategory | Type       | Unit          | Interval |
| ----------------------------------- | ------------ | ------------- | ----------- | ---------- | ------------- | -------- |
| Miner Revenue from Uncle Blocks (%) | BlkUncRevPct | Network Usage | Blocks      | Percentage | Dimensionless | 1 day    |

## Details

* Uncle Blocks (also known as Ommer Blocks) are an intrinsic feature of Ethereum.
* Unlike Bitcoin, Ethereum does not discard blocks in situations where multiple miners find a valid block of the same height.
* Instead, Ethereum rewards secondary miners with so-called Uncle Blocks, which effectively represent a share of the work, as well as the reward, of processing transactions.
* This metric measures the proportion of rewards that resulted from Uncle Blocks.

## Asset-Specific Details

* This metric is only relevant to Ethereum and its replicas.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/BlkUncRevPct" %}
