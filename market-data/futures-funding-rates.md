---
description: /timeseries/market-funding-rates
---

# Market Funding Rates

## **Definition**

Funding rates are a mechanism that exchanges use to ensure that perpetual futures trade at a price that is close to the price of the underlying spot markets. The funding rate is used to calculate the funding fee which long position holders pay short position holders, or vice versa, as a way to incentivize market participants to take positions that keep perpetual futures prices close to the underlying.&#x20;

## **Details**

Traditional futures contracts expire at a specified date in the future. At expiration, traditional futures contracts will settle at a price based on the futures contract underlying’s spot price. This causes the futures contract’s price to converge to the underlying’s spot price at expiration.&#x20;

Perpetual futures contracts are similar to traditional futures contracts except that they never expire. To ensure that the perpetual futures contracts trade a price that is close to the underlying’s spot price, exchanges created a mechanism called the funding rate. Under this mechanism, there are periodic funding payments between long position holders and short position holders depending on whether the perpetual future’s price is higher or lower than the underlying’s spot price.&#x20;

While the formula for how the funding rate is calculated varies by exchange, the general principle is that the funding rate is positive if the perpetual futures’s price is higher than the underlying’s spot price and negative if the perpetual futures’s price is lower than the underlying’s spot price. If the funding rate is positive, long position holders will pay the funding payment to short position holders. If the funding rate is negative, short position holders will pay the funding payment to long position holders. Therefore, the funding rate mechanism encourages traders to take positions that keep perpetual futures’s prices in line with the underlying’s spot price.

## **Chart**

<figure><img src="../.gitbook/assets/BTC-FundingRates.png" alt=""><figcaption><p>Source: CM <a href="https://coinmetrics.io/insights/state-of-the-market/">State of the Market</a></p></figcaption></figure>

## **Example**

A sample of the funding rates data from the `bitmex-XBTUSD-future` market from our  [`/timeseries/market-funding-rates`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketFundingRates) API endpoint is provided below.&#x20;

```
{
  "data": [
    {
      "market": "bitmex-XBTUSD-future",
      "time": "2020-11-11T18:00:00.000000000Z",
      "rate": "-0.000007",
      "period": "08:00:00",
      "interval": "08:00:00",
      "database_time": "2020-12-02T10:49:31.262231000Z"
    },
    {
      "market": "bitmex-XBTUSD-future",
      "time": "2020-11-11T19:00:00.000000000Z",
      "rate": "0.2123",
      "period": "08:00:00",
      "interval": "08:00:00",
      "database_time": "2020-12-02T10:49:31.262231000Z"
    }
  ]
}
```

* **`market`**: The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets. \

*   **`time`**: The exchange-reported time in ISO 8601 date-time format. Always with nanoseconds precision.


* **`rate`**: The funding rate expressed as a percentage over the period. For example, if the funding rate is 0.10%, expressed as an 8 hour rate and calculated over the past 8 hours, the rate is `0.0010`.\

* **`period`**: The periodicity of the funding rate. If the rate is `0.0010`then this rate would be applied every period defined by this field. \

* **`interval`**: The interval of time over which the funding rate is calculated. \

* **`database_time`**: The timestamp when the data was saved in the database in ISO 8601 date-time format with nanoseconds precision.

## **Frequently Asked Questions**&#x20;

### **Can you help me understand the difference between the `period` and `interval` fields?**&#x20;

Each exchange has its own methodology for calculating the funding rate. Many exchanges use either a 1 hour or 8 hour interval of time where input data is measured used in the calculation of the funding rate. This interval of time is captured in the `interval` field. Some exchanges calculate the funding rate instantaneously and for these exchanges we set the interval to `00:00:00.001` by convention.&#x20;

Exchanges also differ in how they report the rate. For some exchanges, the rate represents an 8 hour rate. For others, it represents a 1 hour rate. This means that the funding rate is applied and funding payments are calculated and exchanged between long and short position holders every period as defined by the `period` field.&#x20;

### **Since exchanges follow different conventions, how can I annualize the funding rate so that funding rates across exchanges can be compared?**&#x20;

You can use the `period` field. The formula is to annualize the funding rate is `rate * (1 year) / (period in years)`. Please note that funding payments are always applied to the value of the long or short position and represent a payment that does not change the value of the long or short position, so funding rates are not compounded.&#x20;

### What determines the frequency of funding rates data?

Our funding rates data updates based on the funding interval.&#x20;

### **Why are there so many funding rate values of 0 for Bitfinex?**

Bitfinex funding rate allows for 0% funding rates or no funding payments. [Bitfinex's funding rate methodology](https://www.bitfinex.com/legal/derivative/funding) states that an obligation to make a funding payment arises whenever the average spread is greater than 0.05% or less than -0.05%. When the average spread over the funding period is equal to or within -0.05% and 0.05%, a funding payment will not be required.&#x20;

## **Harmonization Discussion**

Exchanges differ in their funding rate mechanism design and how they report the data through their API. This section will discuss the key differences between exchanges and our approach to creating a harmonized data model.

* **Realized funding rate versus predicted funding rate:** Many exchanges report two different funding rates. The realized funding rate represents the actual funding rate calculated over the previous funding interval that is used in determining the funding payment. The predicted funding rate is the current estimate of what the funding rate will be at the end of the current funding interval. Some exchanges refer to this as the real-time funding rate or the next funding rate. While the predicted funding rate could be important to certain users, in this data concept we are concerned about the realized funding rate. Any references to the term “funding rate” in this document refer to the realized funding rate.\

* **Funding rate period:** Interest rates represent the change over a defined period of time. Many interest rates we encounter in daily life are reported on an annualized basis (a period of one year) because it is a logical period of time. But exchanges can differ on the funding rate period that they use. For many exchanges, the funding rate represents an 8 hour interest rate, so the funding rate period is 8 hours, but not all exchanges report their funding rate with the same funding rate period. We store the funding rate period as a separate column described below. With this information, a user can compare funding rates between exchanges that have different funding rate periods by converting the funding rates to a common funding period.\

* **Funding interval:** The funding interval represents how often the funding rate and funding payments are calculated. For many exchanges, a funding rate is produced every 8 hours and it is calculated based on the difference between the futures’s price and the spot’s price over the previous 8 hours. In this case, the funding interval is 8 hours. For some exchanges, the funding rate and funding payments are calculated on a continuous basis, so the funding interval is set to 1 millisecond by convention.\

* **Exchange-reported timestamp:** Exchanges differ in the how they report the timestamp associated with funding rates. Many exchanges report the funding rate as a timeseries, that is, a series of data points with timestamps that are equally spaced through time. The timestamps represent the time when the funding rate and funding payments are calculated. Other exchanges report the funding rate as a snapshot in time (similar to order book snapshots) and the exchange-reported timestamp represents the timestamp of the query. This method of reporting the funding rate requires some transformation to convert it to a timeseries. Regardless of how the exchanges report the timestamp, we store the funding rates as a timeseries, with one observation at the end of every funding interval.

## Release History

* [**CM MDF v2.2 on December 2, 2020**](https://coinmetrics.io/cm-market-data-feed-futures-data-expansion/)**:** Added funding rates for futures markets on Binance, Bitfinex,  BitMEX, Deribit, FTX, Huobi, Kraken, and OKEx.\

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/): Added funding rates for futures markets on Bybit.

## **Availability**

The previous 24 hours of funding rates data is available through our community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our funding rates data is available through our professional API with higher rate limits. &#x20;

### **Availability by Market Type**

| Type              | Market Count |
| ----------------- | :----------: |
| Perpetual Futures |      683     |

### Availability by Exchange

| Exchange | Futures Market Count | Start Date |
| -------- | :------------------: | :--------: |
| Binance  |          143         | 2019-09-10 |
| Bitfinex |          26          | 2020-12-02 |
| BitMEX   |          24          | 2020-06-18 |
| Bybit    |          24          | 2018-11-15 |
| Deribit  |           2          | 2019-04-30 |
| FTX      |          150         | 2019-03-06 |
| Huobi    |          170         | 2020-03-25 |
| Kraken   |           5          | 2018-08-31 |
| OKEx     |          139         | 2020-10-30 |
