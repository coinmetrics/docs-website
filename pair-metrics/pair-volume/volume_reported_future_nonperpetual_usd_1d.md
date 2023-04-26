# Reported Non-Perpetual Future Volume

## Definition

The sum of all reported volume from all non-perpetual futures markets containing the specified pair in units of U.S. dollars. Non-perpetual futures markets are futures markets that expire.[\
](https://docs.coinmetrics.io/asset-metrics/volume/volume\_reported\_future\_coin\_margined\_usd\_1d)

| Name                                         | Metric                                                   | Category | Subcategory | Type | Unit | Frequency |
| -------------------------------------------- | -------------------------------------------------------- | -------- | ----------- | ---- | ---- | --------- |
| Reported Non-Perpetual Future Volume, 1 Day  | <p>volume_reported_future_</p><p>nonperpetual_usd_1d</p> | Volume   | Future      | Sum  | USD  | 1d        |
| Reported Non-Perpetual Future Volume, 1 Hour | <p>volume_reported_future_</p><p>nonperpetual_usd_1h</p> | Volume   | Future      | Sum  | USD  | 1h        |

## Details

Our reported spot volume metric is an aggregation of the reported volume for all non-perpetual futures markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the `candle_usd_volume` from our market candles as input into the calculation of this metric. For more information on our market candles, please see the page below.

{% content-ref url="../../market-data/market-candles.md" %}
[market-candles.md](../../market-data/market-candles.md)
{% endcontent-ref %}

## Example

A sample of the metric `volume_reported_future_nonperpetual_usd_1d` for pair `btc-usd` from our `/timeseries/pair-metrics` API endpoint is provided below.

```
{
  "data" : [ {
    "pair" : "btc-usd",
    "time" : "2023-04-21T00:00:00.000000000Z",
    "volume_reported_future_nonperpetual_usd_1d" : "1425539617.06"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-22T00:00:00.000000000Z",
    "volume_reported_future_nonperpetual_usd_1d" : "290515733"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-23T00:00:00.000000000Z",
    "volume_reported_future_nonperpetual_usd_1d" : "303388741.93"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-24T00:00:00.000000000Z",
    "volume_reported_future_nonperpetual_usd_1d" : "1174208756.83"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-25T00:00:00.000000000Z",
    "volume_reported_future_nonperpetual_usd_1d" : "1175557173.03"
  } ]
}
```

* **`pair`**: The id of the pair. Pair ids use the following naming convention: `baseAsset-quoteAsset`.\

* **`time`**: The time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`volume_reported_future_nonperpetual_usd_1d`**: The reported future non-perpetual volume in U.S. dollars over the interval of 1 day.

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/volume_reported_future_nonperpetual_usd_1d" %}
