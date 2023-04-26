# Reported Spot Volume

## Definition

The sum of all reported volume from the spot markets that contain the specified pair in units of U.S. dollars.

| Name                         | Metric                          | Category | Subcategory | Type | Unit | Frequency |
| ---------------------------- | ------------------------------- | -------- | ----------- | ---- | ---- | --------- |
| Reported Spot Volume, 1 Day  | volume\_reported\_spot\_usd\_1d | Volume   | Spot        | Sum  | USD  | 1d        |
| Reported Spot Volume, 1 Hour | volume\_reported\_spot\_usd\_1h | Volume   | Spot        | Sum  | USD  | 1h        |

## Details

Our reported spot volume metric is an aggregation of the reported volume for all spot markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the `candle_usd_volume` from our market candles as input into the calculation of this metric. For more information on our market candles, please see the page below.

{% content-ref url="../../market-data/market-candles.md" %}
[market-candles.md](../../market-data/market-candles.md)
{% endcontent-ref %}

## Example

A sample of the metric `volume_reported_spot_usd_1d`for pair `btc-usd` from our `/timeseries/pair-metrics` API endpoint is provided below.

```
{
  "data" : [ {
    "pair" : "btc-usd",
    "time" : "2023-04-21T00:00:00.000000000Z",
    "volume_reported_spot_usd_1d" : "1160683534.5789"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-22T00:00:00.000000000Z",
    "volume_reported_spot_usd_1d" : "466567701.033749"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-23T00:00:00.000000000Z",
    "volume_reported_spot_usd_1d" : "481700913.701521"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-24T00:00:00.000000000Z",
    "volume_reported_spot_usd_1d" : "904720665.126761"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-25T00:00:00.000000000Z",
    "volume_reported_spot_usd_1d" : "834338864.99288"
  } ]
}
```

* **`pair`**: The id of the pair. Pair ids use the following naming convention: `baseAsset-quoteAsset`.\

* **`time`**: The time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`volume_reported_spot_usd_1d`**: The reported spot volume in U.S. dollars over the interval of 1 day.

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/volume_reported_spot_usd_1d" %}
