# Trusted Spot Volume

## Definition

The sum of all volume from the spot markets of a set of trusted exchanges in units of U.S. dollars.[\
](https://docs.coinmetrics.io/info/metrics/volume\_trusted\_spot\_usd\_1d)

| Name                        | MetricID                       | Category | Subcategory | Type | Unit | Interval |
| --------------------------- | ------------------------------ | -------- | ----------- | ---- | ---- | -------- |
| Trusted Spot Volume         | volume\_trusted\_spot\_usd\_1d | Volume   | Spot        | Sum  | USD  | 1d       |
| Trusted Spot Volume, 1 Hour | volume\_trusted\_spot\_usd\_1h | Volume   | Spot        | Sum  | USD  | 1h       |

## Details

Our trusted volume metric is an aggregation of the reported volume from exchanges that we consider the most accurate and trustworthy.  The full list of constituent exchanges included in our Trusted Volume as of Q1 2022 are:

* Binance and Binance.us
* Bitbank
* Bitfinex
* Bitflyer
* Bitstamp
* Bittrex
* CEX.io
* Coinbase
* FTX (New)
* Gate.io
* Gemini
* itBit
* Kraken
* Liquid (New)
* Poloniex
* The Rock Trading (New)
* UpBit (New)

## Examples

A sample of the hourly trusted volumes data for Bitcoin-USD is shown below:

| pair    | time                | volume\_trusted\_spot\_usd\_1d |
| ------- | ------------------- | ------------------------------ |
| btc-usd | 2020-09-28 00:00:00 | 317000178.776577               |
| btc-usd | 2020-09-29 00:00:00 | 246153685.485477               |
| btc-usd | 2020-09-30 00:00:00 | 217972373.240482               |
| btc-usd | 2020-10-01 00:00:00 | 492203699.871197               |

* pair. The IDs of the pair assets.
* time. The reference rate time in ISO 8601 date-time format.
* volume\_trusted\_spot\_usd\_1d. The trusted volume value in units of U.S. dollars.

## Release History

* Release Version. Market Data Feed v2.2 - Jan 21, 2021 rollout (not a separate MDF version)

## Interpretation

Fake trading volume is a persistent problem on crypto exchanges. With little regulatory oversight, it can be difficult to determine whether reported volume numbers are accurate or exaggerated. At Coin Metrics, we’ve taken a data driven approach to the problem and offer a trusted volume metric to help identify legitimate trading volume. Our trusted volume metric is an aggregation of the reported volume from exchanges that we consider the most accurate and trustworthy. This is based on a combination of both quantitative and qualitative features. Our framework for measuring the reporting quality of an exchange is broken down into three broad categories: volume correlation, web traffic analytics and qualitative features. Each of these three categories culminates in a pass/fail test. Exchanges that pass all three measures are included in our trusted volume set of metrics. The current set of trusted volume metrics consider spot markets only and do not include futures or options markets.

## See Also

* [Trusted Volume Framework](https://coinmetrics.io/q3-refresh-of-trusted-spot-volume-framework/)

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/volume_trusted_spot_usd_1d" %}
