# Reported Spot Volume

## Definition

The sum of all reported volume from the spot markets in Coin Metrics' coverage in units of U.S. dollars.

| Name                         | MetricID                        | Category | Subcategory | Type | Unit | Interval |
| ---------------------------- | ------------------------------- | -------- | ----------- | ---- | ---- | -------- |
| Reported Spot Volume         | volume\_reported\_spot\_usd\_1d | Volume   | Spot        | Sum  | USD  | 1d       |
| Reported Spot Volume, 1 Hour | volume\_reported\_spot\_usd\_1h | Volume   | Spot        | Sum  | USD  | 1h       |

## Details

Our reported volume metric is an aggregation of the reported volume from all exchanges in CM's coverage universe.  Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

## Examples

A sample of the daily reported spot volume for Bitcoin-USD is shown below:

| pair    | time                | volume\_reported\_spot\_usd\_1d |
| ------- | ------------------- | ------------------------------- |
| btc-usd | 2022-03-26 00:00:00 | 747285620.134155                |
| btc-usd | 2021-03-27 00:00:00 | 1516874968.35287                |
| btc-usd | 2021-03-28 00:00:00 | 2448850635.22872                |
| btc-usd | 2021-03-28 00:00:00 | 1859520817.29794                |

* pair. The IDs of the pair assets.
* time. The reference rate time in ISO 8601 date-time format.
* reported\_trusted\_spot\_usd\_1d. The reported volume value in units of U.S. dollars.

## Release History

* Release Version. Market Data Feed 2.4 (August 2021)&#x20;

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/volume_reported_spot_usd_1d" %}
