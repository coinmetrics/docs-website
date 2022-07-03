# Difficulty

## Definition

The difficulty of the last block in the considered time period. Difficulty represents how hard it is to find a hash that meets the protocol-designated requirement (i.e., the difficulty of finding a new block) that day. The requirement is unique to each applicable cryptocurrency protocol. Difficulty is adjusted periodically by the protocol as a function of how much hashing power is being deployed by miners.

| Name       | MetricID | Category | Subcategory | Type | Unit          | Interval |
| ---------- | -------- | -------- | ----------- | ---- | ------------- | -------- |
| Difficulty | DiffLast | Mining   | Mining      | Mean | Dimensionless | 1 day    |

## Details

* This metric is not comparable across all chains as its value is dependent on the hashing function used by each chain.

## Asset-Specific Details

* This metric is only available for PoW chains.

## Release History

* Released in the 4.2 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/DiffLast" %}
