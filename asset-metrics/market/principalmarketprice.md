# Principal Market Price (USD)

## **Definition**

The Principal Market Price is the price of an asset quoted in U.S. dollars derived from the asset's principal market, the market with the most trading volume or activity.

| Name                   | **MetricID**                  | **Category** | **Subcategory** | **Type** | **Unit** | **Interval**   |
| ---------------------- | ----------------------------- | ------------ | --------------- | -------- | -------- | -------------- |
| Principal Market Price | principal\_market\_price\_usd | Market       | Price           | n/a      | USD      | 1d, 1h, 1m, 1s |

## Details

* The CM Principal Market Prices are published once a day, once an hour, once a minute, and once a second and adhere to the guidelines regarding fair value measurement issued by the International Financial Reporting Standards and the Association of International Certified Professional Accountants, specifically standards IFRS 13 and FASB ASC 820. The Principal Market Prices identify a principal market for each asset and utilize the most recent price from this market. Common use cases are for fair value measurement, preparing financial statements, and calculating closing prices for indexes or financial benchmarks.\

* Please see our [CM Prices Overview](../../market-data/reference-rates-overview.md) for more information on methodology and policies.

## **Example**

A sample of the Principal Market Price data for Bitcoin is shown below:

<figure><img src="https://raw.githubusercontent.com/coinmetrics/docs-website/master/.gitbook/assets/btc-pmp.png" alt=""><figcaption></figcaption></figure>

* asset:  The IDs of the asset.  &#x20;
* time: The principal market price time in ISO 8601 date-time format.
* principal\_market\_price:  The principal market price value.

## Release History

* Release Version: Principal Market Price v1.0 (October 25, 2022) - initial version

## **Availability for Assets**

Community and pro asset availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history for the 1 hour, 1 min and 1 second prices.&#x20;

{% embed url="https://coverage.coinmetrics.io/asset-metrics/principal_market_price_usd" %}
