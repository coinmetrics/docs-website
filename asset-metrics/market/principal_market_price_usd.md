# Principal Market Price (USD)

## **Definition**

The Principal Market Price is the price of an asset quoted in U.S. dollars derived from the asset's principal market, the market with the most trading volume or activity.

<table data-header-hidden><thead><tr><th width="150">Name</th><th width="239">MetricID</th><th width="141">Category</th><th width="138">Subcategory</th><th>Type</th><th>Unit</th><th>Interval</th></tr></thead><tbody><tr><td>Name</td><td><strong>MetricID</strong></td><td><strong>Category</strong></td><td><strong>Subcategory</strong></td><td><strong>Type</strong></td><td><strong>Unit</strong></td><td><strong>Interval</strong></td></tr><tr><td>Principal Market Price</td><td>principal_market_price_usd</td><td>Market</td><td>Price</td><td>n/a</td><td>USD</td><td>1d, 1h, 1m, 1s</td></tr></tbody></table>

## Details

* The CM Principal Market Prices are published once a day, once an hour, once a minute, and once a second and adhere to the guidelines regarding fair value measurement issued by the International Financial Reporting Standards and the Association of International Certified Professional Accountants, specifically standards IFRS 13 and FASB ASC 820.\

* The Principal Market Prices identify a principal market for each asset and utilize the most recent price from this market. Common use cases are for fair value measurement, preparing financial statements, and calculating closing prices for indexes or financial benchmarks.\

* We also serve the identity of the principal market from which the principal market price is calculated. Please see the Principal Market (USD) page for more details.\

* Please see our [CM Prices Overview](../../market-data/cm-prices-overview.md) for more information on methodology and policies.

## **Example**

A sample of the Principal Market Price data for Bitcoin with daily frequency is shown below:

```
{
  "data" : [ {
    "asset" : "btc",
    "time" : "2023-03-19T00:00:00.000000000Z",
    "principal_market_price_usd" : "26980.35"
  }, {
    "asset" : "btc",
    "time" : "2023-03-20T00:00:00.000000000Z",
    "principal_market_price_usd" : "28054.46"
  }, {
    "asset" : "btc",
    "time" : "2023-03-21T00:00:00.000000000Z",
    "principal_market_price_usd" : "27823.32"
  }, {
    "asset" : "btc",
    "time" : "2023-03-22T00:00:00.000000000Z",
    "principal_market_price_usd" : "28207.33"
  }, {
    "asset" : "btc",
    "time" : "2023-03-23T00:00:00.000000000Z",
    "principal_market_price_usd" : "27325.15"
  }
}
```

* **`asset`**:  The ID of the asset.\
  &#x20; &#x20;
* **`time`**: The time in ISO 8601 date-time format.\

* **`principal_market_price_usd`**:  The principal market price value in U.S. Dollars.

## Release History

* Please see the [Coin Metrics Prices Change Log](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology#change-log) for release history.&#x20;

## **Availability for Assets**

Community and pro asset availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history for the 1 hour, 1 minute and 1 second frequencies. The full history is available for daily frequencies.

Please see our Coin Metrics Coverage below for our asset coverage universe.

{% embed url="https://coverage.coinmetrics.io/asset-metrics/principal_market_price_usd" %}
