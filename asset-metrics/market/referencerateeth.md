# Reference Rate (ETH)

## Definition

The CM Reference Rates represent the reference rate of one unit of the asset quoted in Ethereum.

| Name                | MetricID         | Category | Subcategory | Type | Unit | Interval                           |
| ------------------- | ---------------- | -------- | ----------- | ---- | ---- | ---------------------------------- |
| Reference Rate, ETH | ReferenceRateETH | Market   | Price       | n/a  | ETH  | 1d, 1d-ny-close, 1h, 1m, 1s, 200ms |

## Details

* The CM Reference Rates are published once a day, once an hour, once a minute, once a second, and once every 200 milliseconds and utilizes volume-weighted median, time-weighted average, and inverse price variance-weighted median techniques.\

* Common use cases for the CM Reference Rates include research, backtesting, calculating net asset value for investment funds, calculating closing prices for indexes or financial benchmarks, serving as a data source for on-chain price oracles, risk management, indicative intraday values for investment funds and financial benchmarks, and settling financial derivatives.\

* The CM Reference Rates supports multiple frequencies. The daily and hourly frequencies utilize one calculation methodology and the minute, second, and 200 millisecond frequencies ("real-time frequencies") utilize a separate calculation methodology.\

* The daily and hourly frequencies are calculated at the end of every hour and day, respectively, (the "Calculation Time") and are published within 5 minutes (the “Publication Time”). The real-time frequencies are published in real-time with no delay.\

* Please note that this metric is served through both the [/timeseries/asset-metrics](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) HTTP endpoint and the [/timeseries-stream/asset-metrics](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamAssetMetrics) websocket endpoint. The HTTP endpoint supports the frequencies 1d, 1h, 1m, and 1s. The websocket endpoint supports the frequencies 1s and 200ms.\

* Please see our [CM Prices Overview](../../market-data/cm-prices-overview.md) for more information on methodology and policies.

## Example

A sample of the reference rates data for Bitcoin with one hour frequency is shown below:

```
{
  "data" : [ {
    "asset" : "btc",
    "time" : "2023-03-23T10:00:00.000000000Z",
    "ReferenceRateETH" : "15.7589036393475"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T11:00:00.000000000Z",
    "ReferenceRateETH" : "15.7644408373932"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T12:00:00.000000000Z",
    "ReferenceRateETH" : "15.7242581065847"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T13:00:00.000000000Z",
    "ReferenceRateETH" : "15.7117656446775"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T14:00:00.000000000Z",
    "ReferenceRateETH" : "15.6681462588256"
  }
}
```

A sample of the reference rates data for Bitcoin with one second frequency is shown below:

```
{
  "data" : [ {
    "asset" : "btc",
    "time" : "2023-03-23T14:49:42.000000000Z",
    "ReferenceRateETH" : "15.5656945186602"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T14:49:43.000000000Z",
    "ReferenceRateETH" : "15.5638001214384"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T14:49:44.000000000Z",
    "ReferenceRateETH" : "15.5662555789142"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T14:49:45.000000000Z",
    "ReferenceRateETH" : "15.5621629524661"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T14:49:46.000000000Z",
    "ReferenceRateETH" : "15.5692889374008"
  }
}
```

* **`asset`**: The ID of the asset.\

* **`time`**: The reference rate time in ISO 8601 date-time format.\

* **`ReferenceRateETH`**: The published reference rate value quoted in Ethereum.

## **Release History**

* Please see the [Coin Metrics Prices Change Log](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology#change-log) for release history.&#x20;

## **Availability for Assets**

Community and pro asset availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history for the 1 hour, 1 minute and 1 second frequencies. The full history is available for daily frequencies.

Please see our Coin Metrics Coverage below for our asset coverage universe.

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ReferenceRateETH" %}
