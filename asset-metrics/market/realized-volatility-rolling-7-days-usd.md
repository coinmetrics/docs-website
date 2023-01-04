---
description: /timeseries/asset-metrics
---

# Realized Volatility, Rolling 7 Days (USD)

## Definition

The 7 days rolling realized volatility, measured as the standard deviation of the natural log of 10-minute returns over a 7-day period.

| Name                                      | MetricID                               | Category | Subcategory | Type  | Unit          | Interval |
| ----------------------------------------- | -------------------------------------- | -------- | ----------- | ----- | ------------- | -------- |
| Realized Volatility, Rolling 7 Days (USD) | volatility\_realized\_usd\_rolling\_7d | Market   | Volatility  | Ratio | Dimensionless | 7 days   |

## Details

* Realized volatility can be used to adjust risk parameters like collateralization ratios
* Volatility is calculated using the close-to-close method, as this is optimal for continuous markets and is widely accepted across financial literature
* CM's Real-Time Reference Rate is used as price input to calculate realized volatility
* Reference Rates are sampled on a 10-minute frequency to calculate returns. Volatility is calculated from these returns then annualized, as crypto markets run 24 hours a day each day of the year, which can then be calculated on a rolling window with a specified lookback
* This metric is updated once every hour

## Example

<figure><img src="../../.gitbook/assets/Screen Shot 2022-12-20 at 12.19.26 AM.png" alt=""><figcaption></figcaption></figure>

## Release History

* Released on November 30th, 2022

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/volatility_realized_usd_rolling_7d" %}
