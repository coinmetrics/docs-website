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
* Gate.io
* Gemini
* itBit
* Kraken
* Liquid (New)
* Poloniex
* The Rock Trading (New)
* UpBit (New)

## Chart

![Trusted volume as a portion of total volume](../../.gitbook/assets/BTC\_Trusted\_and\_Non-Trusted\_Volume.png)

## Examples

A sample of the hourly trusted volumes data for Bitcoin is shown below:

| assets | time                | volume\_trusted\_spot\_usd\_1d |
| ------ | ------------------- | ------------------------------ |
| btc    | 2020-09-21 00:00:00 | 44395555400                    |
| btc    | 2020-09-22 00:00:00 | 60004540100                    |
| btc    | 2020-09-23 00:00:00 | 45919134800                    |

* asset. The IDs of the asset.
* time. The reference rate time in ISO 8601 date-time format.
* volume\_trusted\_spot\_usd\_1d. The trusted volume value in units of U.S. dollars.

## Release History

* Release Version. Market Data Feed v2.2 - Jan 21, 2021 rollout (not a separate MDF version)

## Interpretation

Fake trading volume is a persistent problem on crypto exchanges. With little regulatory oversight, it can be difficult to determine whether reported volume numbers are accurate or exaggerated. At Coin Metrics, we’ve taken a data driven approach to the problem and offer a trusted volume metric to help identify legitimate trading volume. Our trusted volume metric is an aggregation of the reported volume from exchanges that we consider the most accurate and trustworthy. This is based on a combination of both quantitative and qualitative features. Our framework for measuring the reporting quality of an exchange is broken down into three broad categories: volume correlation, web traffic analytics and qualitative features. Each of these three categories culminates in a pass/fail test. Exchanges that pass all three measures are included in our trusted volume set of metrics. The current set of trusted volume metrics consider spot markets only and do not include futures or options markets.

## See Also

* [Trusted Volume Framework](https://coinmetrics.io/q3-refresh-of-trusted-spot-volume-framework/)
* [Reported Spot Volume](volume\_reported\_spot\_usd\_1d.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/volume_trusted_spot_usd_1d" %}
