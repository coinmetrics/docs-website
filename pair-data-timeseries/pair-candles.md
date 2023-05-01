---
description: /timeseries/pair-candles
---

# Pair Candles

## **Definition**

Our pair candles consist of summary statistics derived from our [CM Reference Rates](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) for a specific pair like `btc-usd`.&#x20;

## **Details**

Coin Metrics engineers several statistics based on our [CM Reference Rates](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) over an interval of time: opening price, high price, low price, close price. Our pair candles use CM Reference Rates with one second frequency as the input data to engineer these statistics.&#x20;

Candles are generated at regular time intervals and at a time granularity that is suitable for charting and analysis. For instance, several technical analysis indicators can be calculated using data in candles format. We produce our candles at `1m`,  `5m`, `10m`, `15m`, `30m`, `1h`, `4h`, `1d` intervals.&#x20;

## **Example**

An sample of the pair candles data for the \`btc-usdfrom our [`/timeseries/pair-candles`](https://docs.coinmetrics.io/api/v4/#tag/Timeseries/operation/getTimeseriesPairCandles) API endpoint is provided below.&#x20;

```
{
  "data" : [ {
    "pair" : "btc-usd",
    "time" : "2023-04-26T00:00:00.000000000Z",
    "price_open" : "28304.42",
    "price_close" : "28426.08",
    "price_high" : "30018.97",
    "price_low" : "27261.85"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-27T00:00:00.000000000Z",
    "price_open" : "28426.08",
    "price_close" : "29486.73",
    "price_high" : "29890.83",
    "price_low" : "28390"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-28T00:00:00.000000000Z",
    "price_open" : "29486.96",
    "price_close" : "29338.63",
    "price_high" : "29606.45",
    "price_low" : "28917"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-29T00:00:00.000000000Z",
    "price_open" : "29338.63",
    "price_close" : "29248.18",
    "price_high" : "29464.59",
    "price_low" : "29059.33"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-30T00:00:00.000000000Z",
    "price_open" : "29249.45",
    "price_close" : "29238.87",
    "price_high" : "29969.22",
    "price_low" : "29106.68"
  } ]
}
```

* **`time`**:  The time of the beginning of the candle interval in ISO 8601 date-time format.\

* **`pair`**:  The id of the pair. \

* **`price_open`**:   The opening price of the candle.\

* **`price_high`**:  The high price of the candle.\

* **`price_low`**:  The low price of the candle.\

* **`price_close`**: The close price of the candle.

## Frequently Asked Questions

**How come the pair candles does not include volume?**

Our pair candles are calculated from our CM Reference Rates with 1 second frequency, not from all trades from markets that contain this particular pair. Therefore, since the underlying data only includes price, volume is not calculated. We understand this can be a limitation to some users and plan on adding volume in a future release.

**Why are pair candles calculated from CM Reference Rates instead of trades?**

We use our CM Reference Rates with 1 second frequency as the underlying data to calculate our pair candles to ensure that our pair candles represent a robust price that is resistant to outliers and anomalies. If we used trades data from all markets that contain a pair, the data would likely be adversely affected by flash crashes and outliers that may occur on a single market. These outliers and anomalies would show up in either the open, high, low, or close prices. Our CM Reference Rates are resistant to these outliers.

## **Release History**

* [CM Market Data Feed v2.6 on July 13, 2022](https://coinmetrics.io/cm-market-data-feed-v2-6-release-notes/)

## **Availability**

The availability for pair candles is identical to the coverage for our CM Reference Rates below. They are only available for pairs with `usd` as the quote currency.

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ReferenceRateUSD" %}
