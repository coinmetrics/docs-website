---
description: /timeseries/asset-metrics
---

# Reference Rate (BTC)

## Definition

Reference Rates are designed to represent the price of a cryptoasset in an arms length transaction between a willing buyer and willing seller. It is designed to reflect the price where the majority of trades took place for a given cryptoasset using multiple markets as input data sources.

| Name                | MetricID         | Category | Subcategory | Type | Unit | Interval                           |
| ------------------- | ---------------- | -------- | ----------- | ---- | ---- | ---------------------------------- |
| Reference Rate, BTC | ReferenceRateBTC | Market   | Price       | n/a  | BTC  | 1d, 1d-ny-close, 1h, 1m, 1s, 200ms |

## Details

* Hourly (1h, 1d): A systematic framework evaluates and selects a unique set of constituent markets for each cryptoasset and the methodology utilizes volume-weighted median and time- weighted average price techniques. The Reference Rates utilizes a 61-minute window to calculate prices once an hour, every hour, including on weekends and holidays. The Reference Rates can be used for portfolio accounting, as settlement prices for financial derivative contracts, and as closing prices for investment products.
* Real-time (1s, 1m, 200ms):  Similar to the hourly Reference Rates, the Real-Time Reference Rates are designed to represent the price of a cryptoasset in an arms length transaction between a willing buyer and willing seller. Rather than being calculated once an hour, the Real-Time Reference Rates has a separate methodology that utilizes volume-weighted median and inverse price variance weighting techniques to calculate prices once a second, every second, including on weekends and holidays.
* Please note note that this metric is served through both the [/timeseries/asset-metrics](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) HTTP API endpoint and the [/timeseries-stream/asset-metrics](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamAssetMetrics) websocket endpoint. The HTTP endpoint supports the frequencies 1d, 1h, 1m, and 1s. The websocket endpoint supports the frequencies 1s and 200ms.
* View our [**Real-time**](https://coinmetrics.io/wp-content/uploads/2021/05/rtrr-methodology.pdf) and [**Hourly**](https://coinmetrics.io/wp-content/uploads/2021/05/reference-rates-methodology.pdf) reference rates methodology for more information.  Also, see our [**Market Selection Framework**](https://coinmetrics.io/wp-content/uploads/2021/04/reference-rates-market-selection-framework.pdf) **** for our exchange selection criteria.

## **Release History**

* Release Version: Reference Rates v2.11 (Feb 15, 2022) - added BTC-quoted reference rates and ETH-quoted reference rates

## **Availability for Assets**

Community and pro asset availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history for the 1 hour, 1 min and 1 second rates.&#x20;

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ReferenceRateEUR" %}
