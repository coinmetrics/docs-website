---
description: /timeseries/market-metrics
---

# Market Metrics Overview

Coin Metrics calculates several aggregated metrics for markets such as `binance-BTCUSDT-future`. For example, the metric `liquidations_reported_future_buy_usd_1d` represents the daily volume in U.S. dollars of buy orders that were used to close short positions under liquidation for a specific market in our coverage universe. Aggregated metrics available at the market level are available through the [`/timeseries/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketMetrics) API endpoint.

## Market Coverage

We define a market as a specific listed pair or derivatives contract that trades on a specific exchange, like `coinbase-btc-usd-spot` or `binance-BTCUSDT-future` or `deribit-BTC-16MAY21-58000-C-option`. The market metrics coverage can be found by querying our [`/catalog/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarketMetrics)or [`/catalog-all/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarketMetrics) API endpoints.

## Metrics Coverage

The metrics categories listed below are available at the market level:&#x20;

{% embed url="https://docs.coinmetrics.io/market-metrics/liquidations" %}

## Endpoint Response

The [`/timeseries/market-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketMetrics)endpoint returns time series data for each market and metric requested.  The response is formatted as follows:

| Field      | Description                                                               |
| ---------- | ------------------------------------------------------------------------- |
| `market`   | Market name.                                                              |
| `time`     | The time in ISO 8601 date-time format. Always with nanoseconds precision. |
| `{metric}` | Metric value for the specific market and timestamp.                       |

A sample of the market metrics data in json format is also provided below.

```
{
  "data": [
    {
      "market": "binance-BTCUSDT-future",
      "time": "2022-01-19T20:00:00.000000000Z",
      "liquidations_reported_future_buy_usd_5m": "1298.36866"
    },
    {
      "market": "binance-BTCUSDT-future",
      "time": "2022-01-19T20:10:00.000000000Z",
      "liquidations_reported_future_buy_usd_5m": "39713.60016"
    },
    {
      "market": "binance-BTCUSDT-future",
      "time": "2022-01-19T20:30:00.000000000Z",
      "liquidations_reported_future_buy_usd_5m": "29084.10932"
    },
    {
      "market": "binance-BTCUSDT-future",
      "time": "2022-01-19T21:00:00.000000000Z",
      "liquidations_reported_future_buy_usd_5m": "46294.99528"
    }
  ]
}
```

