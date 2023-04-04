---
description: /timeseries/pair-metrics
---

# Pair Metrics Overview

Coin Metrics calculates several metrics for asset pairs such as `btc-usd` and `eth-usd`. Our pair metrics represent an aggregation across markets that contain the specific pair.

For example, the metric `volume_reported_spot_usd_1d` for pair `btc-usd` represents the daily spot volume in U.S. dollars for all markets in our coverage universe that contain the `btc-usd` pair. This incudes the volume from markets such as `coinbase-btc-usd-spot`, `kraken-btc-usd-spot`, and all other spot markets that trade the `btc-usd` pair.

Pair metrics are available through the [`/timeseries/pair-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesPairMetrics) API endpoint.

## Pair Coverage

The pair coverage can be found by querying our [`/catalog/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssetPairs) or [`/catalog-all/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssetPairs) API endpoints or in our [Coin Metrics Coverage](https://coverage.coinmetrics.io/). We offer data on over 5,000 pairs, and the pair coverage is defined as the cartesian product of approximately the top 600 assets.

## Pair Metrics Coverage

The metrics categories listed below are available at the pair level.&#x20;

### Pair Open Interest

Our pair open interest category of metrics contain several measures of open interest of the various types of futures markets. Each pair open interest metric aggregates across certain futures markets (defined by the specific metric) that contain the pair.

{% content-ref url="pair-open-interest/" %}
[pair-open-interest](pair-open-interest/)
{% endcontent-ref %}

### Pair Volume

Similarly, our pair volume category of metrics contain several measures of volume in U.S. dollars. Each pair volume metric aggregates across certain markets (defined by the specific metric) that contain the pair.

{% content-ref url="pair-volume/" %}
[pair-volume](pair-volume/)
{% endcontent-ref %}

## Endpoint Response

The [`/timeseries/pair-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesPairMetrics) endpoint returns time series data for each pair and metric requested. A sample of the pair metrics data in json format is provided below.

```
{
  "data": [
    {
      "pair": "btc-usd",
      "time": "2020-09-28T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "317000178.776577"
    },
    {
      "pair": "btc-usd",
      "time": "2020-09-29T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "246153685.485477"
    },
    {
      "pair": "btc-usd",
      "time": "2020-09-30T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "217972373.240482"
    },
    {
      "pair": "btc-usd",
      "time": "2020-10-01T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "492203699.871197"
    }
  ]
}
```

* **`pair`**: The id of the pair. Pair ids use the following naming convention: `baseAsset-quoteAsset`.\

* **`time`**: The time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`metric`**: The metric value for the specific pair and timestamp.
