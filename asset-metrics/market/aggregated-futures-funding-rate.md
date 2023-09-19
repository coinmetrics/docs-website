# Aggregated Futures Funding Rate

## Definition

The average funding rate weighted by open interest from futures markets converted to a specified time  period.

| Name                                                      | MetricID                                                     | Category | Subcategory | Type       | Unit          | Interval |
| --------------------------------------------------------- | ------------------------------------------------------------ | -------- | ----------- | ---------- | ------------- | -------- |
| Funding rate, aggregated, futures, USD-margined, 8 hours  | futures\_aggregate\_funding\_rate\_usd\_margin\_8h\_period   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, USD-margined, 1 day    | futures\_aggregate\_funding\_rate\_usd\_margin\_1d\_period   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, USD-margined, 30 days  | futures\_aggregate\_funding\_rate\_usd\_margin\_30d\_period  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, USD-margined, 1 year   | futures\_aggregate\_funding\_rate\_usd\_margin\_1y\_period   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, coin-margined, 8 hours | futures\_aggregate\_funding\_rate\_coin\_margin\_8h\_period  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, coin-margined, 1 day   | futures\_aggregate\_funding\_rate\_coin\_margin\_1d\_period  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, coin-margined, 30 days | futures\_aggregate\_funding\_rate\_coin\_margin\_30d\_period | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, coin-margined, 1 year  | futures\_aggregate\_funding\_rate\_coin\_margin\_1y\_period  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, all-margined, 8 hours  | futures\_aggregate\_funding\_rate\_all\_margin\_8h\_period   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, all-margined, 1 day    | futures\_aggregate\_funding\_rate\_all\_margin\_1d\_period   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, all-margined, 30 days  | futures\_aggregate\_funding\_rate\_all\_margin\_30d\_period  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, aggregated, futures, all-margined, 1 year   | futures\_aggregate\_funding\_rate\_all\_margin\_1y\_period   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |

## Details

The `futures_aggregate_funding_rate_usd_margin_*` metrics represent the average funding rate weighted by open interest from perpetual futures markets where the margin asset is U.S. dollars or stablecoins converted to a specified time period.

The `futures_aggregate_funding_rate_coin_margin_*` metrics represent the average funding rate weighted by open interest from perpetual futures markets where the margin asset is equivalent to the underlying base asset converted to a specified period.

The `futures_aggregate_funding_rate_all_margin_*` metrics represent the average funding rate weighted by open interest from all perpetual futures markets, regardless of the margin asset, converted to a specified time period.

These metrics have a publication frequency of once per hour and represent the average funding rate converted to 8 hour, 1 day, 30 day, and 1 year time periods.

Most, but not all, exchanges pay out the funding rate every 8 hours. Thus, standardizing the funding rate period is a step needed for each of the calculation of the funding rate metrics. For a funding rate $$FR$$ with an period $$P$$, expressed in hours, the 8-hour funding rate $$FR_{8}$$ is calculated as follows:

$$
FR_{8} = \frac{P}{8} FR
$$

For a list of markets $$X$$, where each market $$m$$ has funding rate $$FR_{m}$$ and open interest $$OI_{m}$$ converted to U.S. dollars, the aggregate funding rate $$AFR_{X}$$ is calculated as:

$$
AFR_{x} =  \frac{\sum_{m \in X} OI_{m} FR_{m,8}}{\sum_{m \in X} OI_{m}}
$$

## Example

```
{
  "data" : [ {
    "asset" : "btc",
    "time" : "2023-09-19T19:00:00.000000000Z",
    "futures_aggregate_funding_rate_all_margin_8h_period" : "0.0000301358130541726"
  }, {
    "asset" : "btc",
    "time" : "2023-09-19T20:00:00.000000000Z",
    "futures_aggregate_funding_rate_all_margin_8h_period" : "0.0000305589276681095"
  }, {
    "asset" : "btc",
    "time" : "2023-09-19T21:00:00.000000000Z",
    "futures_aggregate_funding_rate_all_margin_8h_period" : "0.0000327674045704149"
  }, {
    "asset" : "btc",
    "time" : "2023-09-19T22:00:00.000000000Z",
    "futures_aggregate_funding_rate_all_margin_8h_period" : "0.0000328893535861447"
  }, {
    "asset" : "btc",
    "time" : "2023-09-19T23:00:00.000000000Z",
    "futures_aggregate_funding_rate_all_margin_8h_period" : "0.0000328738735624742"
  } ]
}
```

* **`asset`**: The id of the asset.\

* **`time`**: The exchange-reported time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`futures_aggregate_funding_rate_all_margin_8h_period`**: The weighted-average funding rate.

## Release History

* Released on September 19, 2023

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/futures_aggregate_funding_rate_all_margin_8h_period" %}

