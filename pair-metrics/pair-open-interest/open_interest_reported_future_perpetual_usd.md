# Reported Perpetual Future Open Interest

## Definition

The sum of all reported future open interest from all perpetual futures markets containing the specified pair in units of U.S. dollars. Perpetual futures markets are futures markets that do not expire, sometimes also called perpetual swaps.[\
](https://docs.coinmetrics.io/asset-metrics/volume/volume\_reported\_future\_coin\_margined\_usd\_1d)

| Name                                    | Metric                                           | Category      | Subcategory | Type | Unit | Frequency |
| --------------------------------------- | ------------------------------------------------ | ------------- | ----------- | ---- | ---- | --------- |
| Reported Perpetual Future Open Interest | open\_interest\_reported\_future\_perpetual\_usd | Open Interest | Future      | Sum  | USD  | 1h, 1d    |

## Details

Our reported perpetual future open interest metric is an aggregation of the reported future open interest for all perpetual futures markets containing the specified pair in CM's coverage universe. Covered exchanges can be found [here](../../exchanges/all-exchanges.md).

We use the open interest we collect for markets as input into the calculation of this metric. For more information on our market-level open interest data, please see the page below.

{% content-ref url="../../market-data/market-open-interest.md" %}
[market-open-interest.md](../../market-data/market-open-interest.md)
{% endcontent-ref %}

## Example

A sample of the metric `open_interest_reported_future_perpetual_usd` for pair `btc-usd` from our `/timeseries/pair-metrics` API endpoint is provided below.

```
{
  "data" : [ {
    "pair" : "btc-usd",
    "time" : "2023-04-01T00:00:00.000000000Z",
    "open_interest_reported_future_perpetual_usd" : "2034303799.94228"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-02T00:00:00.000000000Z",
    "open_interest_reported_future_perpetual_usd" : "2071902762.99073"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-03T00:00:00.000000000Z",
    "open_interest_reported_future_perpetual_usd" : "2060155062.79015"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-04T00:00:00.000000000Z",
    "open_interest_reported_future_perpetual_usd" : "2012816424.18946"
  }, {
    "pair" : "btc-usd",
    "time" : "2023-04-05T00:00:00.000000000Z",
    "open_interest_reported_future_perpetual_usd" : "2047672544.63536"
  } ]
}
```

* **`pair`**: The id of the pair. Pair ids use the following naming convention: `baseAsset-quoteAsset`.\

* **`time`**: The time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`open_interest_reported_future_perpetual_usd`**: The open interest for all perpetual futures markets containing the pair in U.S. dollars.

## Release History

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/): Added open interest for futures markets on Bybit. Added open interest for options markets on Deribit. Extended open interest for Ethereum markets on CME. Created several open interest metrics. Added enhanced open interest deduplication logic.

## Availability for Pairs

{% embed url="https://coverage.coinmetrics.io/pair-metrics/open_interest_reported_future_perpetual_usd" %}

## See Also

{% content-ref url="../../market-data-timeseries/market-metadata.md" %}
[market-metadata.md](../../market-data-timeseries/market-metadata.md)
{% endcontent-ref %}

{% content-ref url="../../market-data/market-open-interest.md" %}
[market-open-interest.md](../../market-data/market-open-interest.md)
{% endcontent-ref %}
