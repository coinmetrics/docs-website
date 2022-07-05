---
description: /timeseries/exchange-metrics
---

# Exchange Metrics Overview

Coin Metrics calculates several metrics for exchanges such as `coinbase`, `binance`, and `deribit`. For example, the metric `volume_reported_spot_usd_1d` represents the daily spot volume in U.S. dollars for a specific exchange. Metrics available at the exchange level is available through the [`/timeseries/exchange-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeMetrics).

## Exchange Coverage

The available exchanges and the metrics available for each exchange can be found by querying our [`/catalog/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchanges) or [`/catalog-all/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchanges) API endpoints or via our [CM data coverage tool](https://coverage.coinmetrics.io/exchanges). You can also find a list of the exchanges in our coverage universe, the start date of our coverage, and the types of markets we collect by going to our [Market Data Exchange Coverage](https://docs.coinmetrics.io/exchanges/all-exchanges).&#x20;

## Metrics Coverage

The metric categories listed below are available at the exchange level:&#x20;

{% content-ref url="open-interest/" %}
[open-interest](open-interest/)
{% endcontent-ref %}

{% content-ref url="volume/" %}
[volume](volume/)
{% endcontent-ref %}

## Endpoint Response

The [`/timeseries/exchange-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeMetrics) endpoint returns time series data for each exchange and metric requested.  The response is formatted as follows:

| Field      | Description                                                               |
| ---------- | ------------------------------------------------------------------------- |
| `exchange` | Exchange name.                                                            |
| `time`     | The time in ISO 8601 date-time format. Always with nanoseconds precision. |
| `{metric}` | Metric value for the specific exchange and timestamp.                     |

A sample of the exchange metrics data in json format is also provided below.

```
{
  "data": [
    {
      "exchange": "binance",
      "time": "2020-09-28T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "317000178.776577"
    },
    {
      "exchange": "binance",
      "time": "2020-09-29T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "246153685.485477"
    },
    {
      "exchange": "binance",
      "time": "2020-09-30T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "217972373.240482"
    },
    {
      "exchange": "binance",
      "time": "2020-10-01T00:00:00.000000000Z",
      "volume_reported_spot_usd_1d": "492203699.871197"
    }
  ]
}
```
