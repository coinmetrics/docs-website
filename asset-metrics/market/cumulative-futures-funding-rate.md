# Cumulative Futures Funding Rate

## Definition

The cumulative funding rate is the total funding rate that would be accumulated by contract holders over a specified time period.

| Name                                                      | MetricID                                              | Category | Subcategory | Type       | Unit          | Interval |
| --------------------------------------------------------- | ----------------------------------------------------- | -------- | ----------- | ---------- | ------------- | -------- |
| Funding rate, cumulative, futures, USD-margined, 1 day    | futures\_cumulative\_funding\_rate\_usd\_margin\_1d   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, USD-margined, 7 days   | futures\_cumulative\_funding\_rate\_usd\_margin\_7d   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, USD-margined, 30 days  | futures\_cumulative\_funding\_rate\_usd\_margin\_30d  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, coin-margined, 1 day   | futures\_cumulative\_funding\_rate\_coin\_margin\_1d  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, coin-margined, 7 days  | futures\_cumulative\_funding\_rate\_coin\_margin\_7d  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, coin-margined, 30 days | futures\_cumulative\_funding\_rate\_coin\_margin\_30d | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, all-margined, 1 day    | futures\_cumulative\_funding\_rate\_all\_margin\_1d   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, all-margined, 7 days   | futures\_cumulative\_funding\_rate\_all\_margin\_7d   | Market   | Futures     | Percentage | Dimensionless | 1 hour   |
| Funding rate, cumulative, futures, all-margined, 30 days  | futures\_cumulative\_funding\_rate\_all\_margin\_30d  | Market   | Futures     | Percentage | Dimensionless | 1 hour   |

## Details

The `futures_cumulative_funding_rate_usd_margin_*` metrics represent the cumulative average funding rate weighted by open interest from futures markets where the margin asset is U.S. dollars or stablecoins over the previous specified time period.

The `futures_cumulative_funding_rate_coin_margin_*` metrics represent the cumulative average funding rate weighted by open interest from futures markets where the margin asset is equivalent to the underlying base asset over the previous specified time period.

The `futures_cumulative_funding_rate_all_margin_*` metrics represent the cumulative average funding rate weighted by open interest from all futures markets, regardless of the margin asset, over the previous specified time period.

These metrics have a publication frequency of once per hour and represent the cumulative realized funding rate over the previous 1 day, 7 day, and 30 day time periods.

For example, at the market level, the cumulative funding rate for `binance-BTCUSDT-future` over the course of one day would be the cumulative product of the three 8-hour funding settlement rates reported that day. For these metrics, with the CFR being calculated for assets, we leverage our [Aggregate Futures Funding Rate](aggregated-futures-funding-rate.md) to perform this calculation across all relevant markets.&#x20;

To accumulate the rates hour-over-hour, we first convert the AFR to an hourly rate, multiply the rates together, then convert the product back to the desired rate.



$$
CFR_{L}=\prod_{i=1}^{L} (1 + AFR_{1h,i}) - 1
$$

$$
AFR_{1h,i} = \frac{AFR_{8h,i}}{8}
$$

where $$AFR_{i}$$ is the Aggregate Funding Rate at timestamp $$i$$. The increments $$i$$ are hourly, as $$AFR$$ is published hourly. Thus, `futures_cumulative_funding_rate_usd_margin_1d`is the accumulation of funding rates over the last 24 hours,  `futures_cumulative_funding_rate_usd_margin_7d` is the accumulation of funding rates over the last 168 hours, etc.&#x20;

## Example

```
{
  "data" : [ {
    "asset" : "btc",
    "time" : "2023-09-18T19:00:00.000000000Z",
    "futures_cumulative_funding_rate_coin_margin_1d" : "0.0000748325509789538"
  }, {
    "asset" : "btc",
    "time" : "2023-09-18T20:00:00.000000000Z",
    "futures_cumulative_funding_rate_coin_margin_1d" : "0.0000725858255383738"
  }, {
    "asset" : "btc",
    "time" : "2023-09-18T21:00:00.000000000Z",
    "futures_cumulative_funding_rate_coin_margin_1d" : "0.0000703397006305284"
  }, {
    "asset" : "btc",
    "time" : "2023-09-18T22:00:00.000000000Z",
    "futures_cumulative_funding_rate_coin_margin_1d" : "0.0000678449650222124"
  }, {
    "asset" : "btc",
    "time" : "2023-09-18T23:00:00.000000000Z",
    "futures_cumulative_funding_rate_coin_margin_1d" : "0.0000653489780522154"
  } ]
}
```

* **`asset`**: The id of the asset.\

* **`time`**: The exchange-reported time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`futures_cumulative_funding_rate_coin_margin_1d`**: The cumulative funding rate.

## Release History

* Released on September 19, 2023

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/futures_cumulative_funding_rate_coin_margin_1d" %}

