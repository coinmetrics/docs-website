---
description: /timeseries/pair-metrics
---

# Pair Metrics Overview

Coin Metrics calculates several metrics for asset pairs such as `btc-usd` and `eth-usd`. For example, the metric `volume_reported_spot_usd_1d` represents the daily spot volume in U.S. dollars for all markets in our coverage universe that contain the specific pair. Metrics available at the exchange-asset level is available through the [`/timeseries/pair-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesPairMetrics) API endpoint.

## Pair Coverage

The pair coverage can be found by querying our [`/catalog/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssetPairs) or [`/catalog-all/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssetPairs) API endpoints or in our [CM data coverage tool](https://coverage.coinmetrics.io/pairs). The pair coverage is defined as the combination (cartesian product) of all the top assets (approximately the top 300 assets by market capitalization).&#x20;

## Metrics Coverage

The metrics categories listed below are available at the pair level:&#x20;

{% content-ref url="open-interest/" %}
[open-interest](open-interest/)
{% endcontent-ref %}

{% content-ref url="volume.md" %}
[volume.md](volume.md)
{% endcontent-ref %}

## Endpoint Response

The [`/timeseries/pair-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesPairMetrics) endpoint returns time series data for each pair and metric requested.  The response is formatted as follows:

| Field      | Description                                                               |
| ---------- | ------------------------------------------------------------------------- |
| `pair`     | Pair name.                                                                |
| `time`     | The time in ISO 8601 date-time format. Always with nanoseconds precision. |
| `{metric}` | Metric value for the specific pair and timestamp.                         |

A sample of the pair metrics data in json format is also provided below.

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

