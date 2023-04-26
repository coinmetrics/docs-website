# Reported Coin-Margined Future Volume

## Definition

The sum of all reported volume from all coin-margined futures markets containing the specified pair in units of U.S. dollars. Coin-margined futures markets are futures markets where the underlying base asset is identical to the margin asset.[\
](https://docs.coinmetrics.io/asset-metrics/volume/volume\_reported\_future\_coin\_margined\_usd\_1d)

| Name                                         | Metric                                                    | Category | Subcategory | Type | Unit | Frequency |
| -------------------------------------------- | --------------------------------------------------------- | -------- | ----------- | ---- | ---- | --------- |
| Reported Coin-Margined Future Volume, 1 Day  | <p>volume_reported_future_</p><p>coin_margined_usd_1d</p> | Volume   | Future      | Sum  | USD  | 1d        |
| Reported Coin-Margined Future Volume, 1 Hour | <p>volume_reported_future_</p><p>coin_margined_usd_1h</p> | Volume   | Future      | Sum  | USD  | 1h        |

## Details

Our reported spot volume metric is an aggregation of the reported volume for all coin-margined futures markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the `candle_usd_volume` from our market candles as input into the calculation of this metric. For more information on our market candles, please see the page below.

{% content-ref url="../../market-data/market-candles.md" %}
[market-candles.md](../../market-data/market-candles.md)
{% endcontent-ref %}

## Example

A sample of the metric `volume_reported_future_coin_margined_usd_1d` for pair `btc-usd` from our `/timeseries/pair-metrics` API endpoint is provided below.

```
{
  "data" : [ {
    "pair" : "btc-usd",
    "time" : "2023-04-21T00:00:00.000000000Z",
    "volume_reported_future_coin_margined_usd_1d" : "6237511679"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-22T00:00:00.000000000Z",
    "volume_reported_future_coin_margined_usd_1d" : "2572933751"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-23T00:00:00.000000000Z",
    "volume_reported_future_coin_margined_usd_1d" : "2666308456"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-24T00:00:00.000000000Z",
    "volume_reported_future_coin_margined_usd_1d" : "4947029622"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-25T00:00:00.000000000Z",
    "volume_reported_future_coin_margined_usd_1d" : "4179630976"
  } ]
}
```

* **`pair`**: The id of the pair. Pair ids use the following naming convention: `baseAsset-quoteAsset`.\

* **`time`**: The time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`volume_reported_future_coin_margined_usd_1d`**: The reported future coin-margined volume in U.S. dollars over the interval of 1 day.

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/volume_reported_future_coin_margined_usd_1d" %}
