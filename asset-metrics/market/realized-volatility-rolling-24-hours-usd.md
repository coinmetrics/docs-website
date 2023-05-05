# Realized Volatility, Rolling 24 Hours (USD)

## Definition

The 24 hour rolling realized volatility, measured as the standard deviation of the natural log of returns calculated every 10 minutes over the past 24 hours.



| Name                                         | MetricID                                | Category | Subcategory | Type  | Unit          | Interval |
| -------------------------------------------- | --------------------------------------- | -------- | ----------- | ----- | ------------- | -------- |
| Volatility, realized, USD, rolling, 24 hours | volatility\_realized\_usd\_rolling\_24h | Market   | Volatility  | Ratio | Dimensionless | 24 hours |

## Details

Coin Metrics calculates realized volatility using our [CM Reference Rates](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology#reference-rates-calculation-methodology) with frequency of 1s as the price input. The CM Reference Rates have been tested against many out-of-sample periods of market stress and have been reliably producing prices under numerous market conditions for a period of three years. It utilizes our [Market Selection Framework](../../market-data/methodologies/coin-metrics-prices-methodology.md#data-inputs) which evaluates all markets in our coverage universe and uses a set of 38 qualitative and quantitative features to produce a unique set of constituent markets for each asset. It uses volume-weighted and inverse price variance-weighted techniques to produce a price that is robust to outliers and anomalies.&#x20;

Volatility is calculated using the close-to-close method, as this is optimal for continuous markets and is widely accepted across financial literature. For this calculation we use the population mean with zero drift, meaning the formula reduces to:

$$
RV=\sqrt{\frac{1}{N-1}\sum_{i=1}^{N}(ln(\frac{s_i}{s_i-1}) - 0)^2}\cdot\sqrt{T}
$$

Where $$RV$$is the realized volatility (annualized), $$N$$is the lookback window, $${s_i}$$ is the real-time reference rate price at timestep $$i$$, and $$T$$ is the time adjustment factor. Using an average return of 0 is standard in these calculations as it avoids misleading volatility numbers during sustained periods of substantially high or low return.

The real-time reference rates are resampled to calculate returns over a 10 minute period, as this frequency captures the rapid nature of volatility in cryptocurrency markets. Volatility is then annualized by setting $$T=6⋅24⋅365$$, as crypto markets trade 24 hours a day each day of the year. Volatility can then be calculated on a rolling window with a specified lookback.

## Example

```
{
  "data": [
    {
      "asset": "btc",
      "time": "2023-01-04T01:20:00.000000000Z",
      "volatility_realized_usd_rolling_24h": "0.152377"
    },
    {
      "asset": "btc",
      "time": "2023-01-04T01:30:00.000000000Z",
      "volatility_realized_usd_rolling_24h": "0.1522188"
    },
    {
      "asset": "btc",
      "time": "2023-01-04T01:40:00.000000000Z",
      "volatility_realized_usd_rolling_24h": "0.1521909"
    },
    {
      "asset": "btc",
      "time": "2023-01-04T01:50:00.000000000Z",
      "volatility_realized_usd_rolling_24h": "0.1520814"
    },
    {
      "asset": "btc",
      "time": "2023-01-04T02:00:00.000000000Z",
      "volatility_realized_usd_rolling_24h": "0.151912"
    }
  ]
}
```

* **`asset`**: The id of the asset.\

* **`time`**: The exchange-reported time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`volatility_realized_usd_rolling_24h`**: The annualized 24-hour rolling volatility.

## Release History

* Released on November 30th, 2022

## Availability for Assets

The realized volatility metrics are available for approximately 650 assets and is identical to the CM Reference Rates coverage universe.

{% embed url="https://coverage.coinmetrics.io/asset-metrics/volatility_realized_usd_rolling_24h" %}
