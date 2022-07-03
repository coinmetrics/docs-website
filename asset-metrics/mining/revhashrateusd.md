# Miner Revenue per Hash per Sec (USD)

## Definition

The USD value of the mean daily miner reward per estimated hash unit per second performed during the period, also known as hashprice. The unit of hashpower measurement depends on the protocol.

## Details

* Hash rate calculations are specific to a protocol's mining algorithm, which often targets a time in between blocks.
* Below are formulas and measurement units associated with each of the supported assets.

| Asset          | Hashrate Formula                                      | Unit |
| -------------- | ----------------------------------------------------- | ---- |
| BTC, BCH, BSV  | (BlkCnt / 144) \* DiffMean \* ((2^32 / 10^12) / 600)) | TH/s |
| DASH, BTG, VTC | Daily chainwork / 86400 / 10^9                        | GH/s |
| LTC            | (BlkCnt / 576) \* DiffMean \* ((2^32 / 10^12) / 150)) | TH/s |
| XMR            | (BlkCnt / 720) \* DiffMean \* 1000000                 | MH/s |
| ZEC            | ((DiffMean / 150) \* 7000) / 10^9                     | GH/s |
| ETH, ETC       | (DiffMean / BlkIntMean) / 10^12                       | TH/s |

##

## Dictionary

| Name                                 | MetricID       | Category | Subcategory | Type | Unit | Interval |
| ------------------------------------ | -------------- | -------- | ----------- | ---- | ---- | -------- |
| Miner Revenue per Hash per Sec (USD) | RevHashRateUSD | Mining   | Hash Rate   | Mean | USD  | 1 day    |

## Release History

* Released in the version 4.9 of Network Data Pro

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/RevHashRateUSD" %}
