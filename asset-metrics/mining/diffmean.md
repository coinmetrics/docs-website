# Mean Difficulty

## Definition

The mean difficulty of finding a hash that meets the protocol-designated requirement (i.e., the difficulty of finding a new block) that day. The requirement is unique to each applicable cryptocurrency protocol. Difficulty is adjusted periodically by the protocol as a function of how much hashing power is being deployed by miners.

| Name            | MetricID | Category | Subcategory | Type | Unit          | Interval |
| --------------- | -------- | -------- | ----------- | ---- | ------------- | -------- |
| Mean Difficulty | DiffMean | Mining   | Mining      | Mean | Dimensionless | 1 day    |

## Details

* This metric is not comparable across all chains as its value is dependent on the hashing function used by each chain.

## Chart

<figure><img src="../../.gitbook/assets/BTC_Mean_Difficulty___Price (1).png" alt=""><figcaption><p>Source: CM Network Data Charts</p></figcaption></figure>

## Examples

* When the majority of the Bitcoin blocks are produced at 10 minutes, the difficulty adjustments will not be significant. This could indicate new miners are not getting online and existing ones are not shutting off their operations.

## Asset-Specific Details

* This metric is only available for PoW chains.

## Interpretation

* This measures how difficult and time consuming it is to find the right hash for each block

## Release History

* Released in the 1.0 release of NDP

## See Also

{% content-ref url="difflast.md" %}
[difflast.md](difflast.md)
{% endcontent-ref %}

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/DiffMean" %}
