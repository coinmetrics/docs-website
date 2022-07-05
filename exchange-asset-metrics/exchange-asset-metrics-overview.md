---
description: /timeseries/exchange-asset-metrics
---

# Exchange-Asset Metrics Overview

Coin Metrics calculates several metrics for exchange-asset pairs such as `coinbase-btc`, `binance-eth`, and `deribit-usdt`. For example, the metric `volume_reported_spot_usd_1d` represents the daily spot volume in U.S. dollars for a specific asset that trades on a specific exchange. Metrics available at the exchange-asset level is available through the [`/timeseries/exchange-asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeAssetMetrics) API endpoint.

## Exchange-Asset Coverage

The exchange-asset coverage can be found by querying our [`/catalog/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchangeAssets) or [`/catalog-all/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchangeAssets) API endpoints.&#x20;

The exchange-asset coverage is defined as the combination (cartesian product) of all the exchanges in our coverage universe and all of the top assets (approximately the top 300 assets by market capitalization). You can also find a list of the exchanges in our coverage universe, the start date of our coverage, and the types of markets we collect by going to our [Market Data Exchange Coverage](https://docs.coinmetrics.io/exchanges/all-exchanges).&#x20;

## Metrics Coverage

The metrics categories listed below are available at the exchange-asset level:&#x20;

{% content-ref url="basis/" %}
[basis](basis/)
{% endcontent-ref %}

{% content-ref url="open-interest.md" %}
[open-interest.md](open-interest.md)
{% endcontent-ref %}

{% content-ref url="volume.md" %}
[volume.md](volume.md)
{% endcontent-ref %}

## Endpoint Response

The [`/timeseries/exchange-asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeAssetMetrics) endpoint returns time series data for each exchange-asset and metric requested.  The response is formatted as follows:

| Field            | Description                                                               |
| ---------------- | ------------------------------------------------------------------------- |
| `exchange_asset` | Exchange-asset name.                                                      |
| `time`           | The time in ISO 8601 date-time format. Always with nanoseconds precision. |
| `{metric}`       | Metric value for the specific exchange-asset and timestamp.               |

A sample of the exchange-asset metrics data in json format is also provided below.

```
{
  "data": [
    {
      "exchange_asset": "binance",
      "time": "2020-09-28T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "317000178.776577"
    },
    {
      "exchange_asset": "binance",
      "time": "2020-09-29T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "246153685.485477"
    },
    {
      "exchange_asset": "binance",
      "time": "2020-09-30T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "217972373.240482"
    },
    {
      "exchange_asset": "binance",
      "time": "2020-10-01T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "492203699.871197"
    }
  ]
}
```
