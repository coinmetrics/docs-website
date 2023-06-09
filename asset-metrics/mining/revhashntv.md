# Miner Revenue per Hash (native units)

## Definition

The mean miner reward per estimated hash unit performed during the period, in native units. The unit of hashpower measurement depends on the protocol.

| Name                                  | MetricID   | Category | Subcategory | Type | Unit         | Interval |
| ------------------------------------- | ---------- | -------- | ----------- | ---- | ------------ | -------- |
| Miner Revenue per Hash (native units) | RevHashNtv | Mining   | Revenue     | Mean | Native units | 1 day    |

## Asset-Specific Details

* Post Ethereum Merge, Miner Metrics have been deprecated&#x20;
* Hash rate calculations are specific to a protocol's mining algorithm, which often targets a time in between blocks.
* Below are formulas and measurement units associated with each of the supported assets.

<table><thead><tr><th>Asset</th><th width="218.7027804410355">Hashrate Formula</th><th>Unit</th></tr></thead><tbody><tr><td>BTC, BCH, BSV</td><td>(BlkCnt / 144) * DiffMean * ((2^32 / 10^12) / 600))</td><td>TH/s</td></tr><tr><td>DASH, BTG, VTC</td><td>Daily chainwork / 86400 / 10^9</td><td>GH/s</td></tr><tr><td>LTC</td><td>(BlkCnt / 576) * DiffMean * ((2^32 / 10^12) / 150))</td><td>TH/s</td></tr><tr><td>XMR</td><td>(BlkCnt / 720) * DiffMean * 1000000</td><td>MH/s</td></tr><tr><td>ZEC</td><td>((DiffMean / 150) * 7000) / 10^9</td><td>GH/s</td></tr><tr><td>ETH, ETC</td><td>(DiffMean / BlkIntMean) / 10^12</td><td>TH/s</td></tr></tbody></table>

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/RevHashNtv" %}
