# Miner Revenue per Hash per Sec (USD)

## Definition

The USD value of the mean daily miner reward per estimated hash unit per second performed during the period, also known as hashprice. The unit of hashpower measurement depends on the protocol.

| Name                                 | MetricID       | Category | Subcategory | Type | Unit | Interval |
| ------------------------------------ | -------------- | -------- | ----------- | ---- | ---- | -------- |
| Miner Revenue per Hash per Sec (USD) | RevHashRateUSD | Mining   | Hash Rate   | Mean | USD  | 1 day    |

## Asset-Specific Details

* Post Ethereum Merge, Miner Metrics are no longer calculated
* Hash rate calculations are specific to a protocol's mining algorithm, which often targets a time in between blocks.
* Below are formulas and measurement units associated with each of the supported assets.

<table><thead><tr><th>Asset</th><th width="218.7027804410355">Hashrate Formula</th><th>Unit</th></tr></thead><tbody><tr><td>BTC, BCH, BSV</td><td>(BlkCnt / 144) * DiffMean * ((2^32 / 10^12) / 600))</td><td>TH/s</td></tr><tr><td>DASH, BTG, VTC</td><td>Daily chainwork / 86400 / 10^9</td><td>GH/s</td></tr><tr><td>LTC</td><td>(BlkCnt / 576) * DiffMean * ((2^32 / 10^12) / 150))</td><td>TH/s</td></tr><tr><td>XMR</td><td>(BlkCnt / 720) * DiffMean * 1000000</td><td>MH/s</td></tr><tr><td>ZEC</td><td>((DiffMean / 150) * 7000) / 10^9</td><td>GH/s</td></tr><tr><td>ETH, ETC</td><td>(DiffMean / BlkIntMean) / 10^12</td><td>TH/s</td></tr></tbody></table>

## Release History

* Released in the version 4.9 of Network Data Pro

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/RevHashRateUSD" %}
