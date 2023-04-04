# Reported Spot Volume

## Definition

The sum of all reported volume from the spot markets that contain the specified pair in units of U.S. dollars.

| Name                         | Metric                          | Category | Subcategory | Type | Unit | Frequency |
| ---------------------------- | ------------------------------- | -------- | ----------- | ---- | ---- | --------- |
| Reported Spot Volume, 1 Day  | volume\_reported\_spot\_usd\_1d | Volume   | Spot        | Sum  | USD  | 1d        |
| Reported Spot Volume, 1 Hour | volume\_reported\_spot\_usd\_1h | Volume   | Spot        | Sum  | USD  | 1h        |

## Details

Our reported spot volume metric is an aggregation of the reported volume for all spot markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

## Examples

A sample of the daily reported spot volume for Binance is shown below:

| exchange | time                | volume\_reported\_spot\_usd\_1d |
| -------- | ------------------- | ------------------------------- |
| binance  | 2022-01-01 00:00:00 | 8988114373.91716                |
| binance  | 2022-01-02 00:00:00 | 9686610104.12659                |
| binance  | 2022-01-03 00:00:00 | 13513437237.6032                |
| binance  | 2022-01-04 00:00:00 | 15006844836.1782                |

* exchange. The IDs of the exchanges.
* time. The reference rate time in ISO 8601 date-time format.
* reported\_trusted\_spot\_usd\_1d. The reported volume value in units of U.S. dollars.

## Release History

* Release Version. Market Data Feed 2.4 (August 2021)&#x20;

## Availability for Exchanges

{% embed url="https://coverage.coinmetrics.io/exchange-metrics/volume_reported_spot_usd_1d" %}
