# Mean Hash Rate

## Definition

The mean rate at which miners are solving hashes that day. Hash rate is the speed at which computations are being completed across all miners in the network. The unit of measurement varies depending on the protocol.

| Name           | MetricID | Category | Subcategory | Type | Unit   | Interval |
| -------------- | -------- | -------- | ----------- | ---- | ------ | -------- |
| Mean Hash Rate | HashRate | Mining   | Hash Rate   | Mean | Varies | 1 day    |

## Asset-Specific Details

* Post Ethereum Merge, Miner Metrics are no longer calculated
* Hash rate is derived from difficulty (DiffMean), the rate at which block came in (BlkIntMean) and depending on the protocols, some other pieces of data. It gives an estimate of how much hash power is mining a given chain.

## Chart

<figure><img src="../../.gitbook/assets/Coin_Metrics_Network_Data_2022-09-15T15-37 (1).png" alt=""><figcaption><p>Source: CM Network Data Charts</p></figcaption></figure>

| Asset          | Formula                                               | Hash Rate Unit |
| -------------- | ----------------------------------------------------- | -------------- |
| BTC, BCH, BSV  | (BlkCnt / 144) \* DiffMean \* ((2^32 / 10^12) / 600)) | TH/s           |
| DASH, BTG, VTC | Daily chainwork / 86400 / 10^9                        | GH/s           |
| LTC            | (BlkCnt / 576) \* DiffMean \* ((2^32 / 10^12) / 150)) | TH/s           |
| XMR            | (BlkCnt / 720) \* DiffMean \* 1000000                 | MH/s           |
| ZEC            | ((DiffMean / 150) \* 7000) / 10^9                     | GH/s           |
| ETH, ETC       | (DiffMean / BlkIntMean) / 10^12                       | TH/s           |

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Given that proof-of-work cryptocurrencies share a great variety of algorithms, with widely diverging features, hashrate is not comparable between them. The exception is cases where distinct assets share the same hash function, as is the case with BTC, BCH, and BSV for instance. To benchmark security between assets with different hash functions, a metric like security spend (Issuance, Total, USD) might be consulted instead.

## See Also

* [Mean Hash Rate, 30 Day](hashrate30d.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/HashRate" %}
