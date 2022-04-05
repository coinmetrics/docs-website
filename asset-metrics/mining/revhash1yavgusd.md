# Yearly Avg. Miner Revenue per Hash (USD)

## Definition

The trailing one-year average miner reward per estimated hash unit performed during the period, in native units. The unit of hashpower measurement depends on the protocol.

## Dictionary

| Name                                     | MetricID        | Category | Subcategory | Type | Unit | Interval |
| ---------------------------------------- | --------------- | -------- | ----------- | ---- | ---- | -------- |
| Yearly Avg. Miner Revenue per Hash (USD) | RevHash1yAvgUSD | Mining   | Revenue     | Mean | USD  | 1 day    |

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

## Release History

* Released in Network Data Pro (NDP) version 5.1&#x20;

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/RevHash1yAvgUSD" %}
