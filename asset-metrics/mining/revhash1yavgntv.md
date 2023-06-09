# Yearly Avg. Miner Revenue per Hash (native units)

## Definition

The trailing one-year average miner reward per estimated hash unit performed during the period, in native units. The unit of hashpower measurement depends on the protocol.

## Dictionary

| Name                                              | MetricID        | Category | Subcategory | Type | Unit         | Interval |
| ------------------------------------------------- | --------------- | -------- | ----------- | ---- | ------------ | -------- |
| Yearly Avg. Miner Revenue per Hash (native units) | RevHash1yAvgNtv | Mining   | Revenue     | Mean | Native Units | 1 day    |

## Details

* Hash rate calculations are specific to a protocol's mining algorithm, which often targets a time in between blocks.
* Below are formulas and measurement units associated with each of the supported assets.

<table><thead><tr><th>Asset</th><th width="218.7027804410355">Hashrate Formula</th><th>Unit</th></tr></thead><tbody><tr><td>BTC, BCH, BSV</td><td>(BlkCnt / 144) * DiffMean * ((2^32 / 10^12) / 600))</td><td>TH/s</td></tr><tr><td>DASH, BTG, VTC</td><td>Daily chainwork / 86400 / 10^9</td><td>GH/s</td></tr><tr><td>LTC</td><td>(BlkCnt / 576) * DiffMean * ((2^32 / 10^12) / 150))</td><td>TH/s</td></tr><tr><td>XMR</td><td>(BlkCnt / 720) * DiffMean * 1000000</td><td>MH/s</td></tr><tr><td>ZEC</td><td>((DiffMean / 150) * 7000) / 10^9</td><td>GH/s</td></tr><tr><td>ETH, ETC</td><td>(DiffMean / BlkIntMean) / 10^12</td><td>TH/s</td></tr></tbody></table>

## Release History

* Released in Network Data Pro (NDP) version 5.1&#x20;

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/RevHash1yAvgNtv" %}
