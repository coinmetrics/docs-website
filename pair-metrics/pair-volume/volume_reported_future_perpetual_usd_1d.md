# Reported Perpetual Future Volume

## Definition

The sum of all reported volume from all perpetual futures markets containing the specified pair in units of U.S. dollars. Perpetual futures markets are futures markets that do not expire, sometimes also called perpetual swaps.[\
](https://docs.coinmetrics.io/asset-metrics/volume/volume\_reported\_future\_coin\_margined\_usd\_1d)

| Name                                     | Metric                                                | Category | Subcategory | Type | Unit | Frequency |
| ---------------------------------------- | ----------------------------------------------------- | -------- | ----------- | ---- | ---- | --------- |
| Reported Perpetual Future Volume, 1 Day  | <p>volume_reported_future_</p><p>perpetual_usd_1d</p> | Volume   | Future      | Sum  | USD  | 1d        |
| Reported Perpetual Future Volume, 1 Hour | <p>volume_reported_future_</p><p>perpetual_usd_1h</p> | Volume   | Future      | Sum  | USD  | 1h        |

## Details

Our reported spot volume metric is an aggregation of the reported volume for all perpetual futures markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the `candle_usd_volume` from our market candles as input into the calculation of this metric. For more information on our market candles, please see the page below.

{% content-ref url="../../market-data/market-candles.md" %}
[market-candles.md](../../market-data/market-candles.md)
{% endcontent-ref %}

## Example

A sample of the metric `volume_reported_future_perpetual_usd_1d` for pair `btc-usd` from our `/timeseries/pair-metrics` API endpoint is provided below.

```
{
  "data" : [ {
    "pair" : "btc-usd",
    "time" : "2023-04-21T00:00:00.000000000Z",
    "volume_reported_future_perpetual_usd_1d" : "5651422969.99453"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-22T00:00:00.000000000Z",
    "volume_reported_future_perpetual_usd_1d" : "2316378467.29551"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-23T00:00:00.000000000Z",
    "volume_reported_future_perpetual_usd_1d" : "2406900001.80996"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-24T00:00:00.000000000Z",
    "volume_reported_future_perpetual_usd_1d" : "4528479018.79825"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-25T00:00:00.000000000Z",
    "volume_reported_future_perpetual_usd_1d" : "3813804136.3796"
  } ]
}
```

* **`pair`**: The id of the pair. Pair ids use the following naming convention: `baseAsset-quoteAsset`.\

* **`time`**: The time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`volume_reported_future_perpetual_usd_1d`**: The reported future perpetual volume in U.S. dollars over the interval of 1 day.

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/volume_reported_future_perpetual_usd_1d" %}
