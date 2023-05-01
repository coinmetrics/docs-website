---
description: /timeseries/market-contract-prices
---

# Market Contract Prices

## **Definition**

Market contract prices are used as reference prices to estimate the value of a derivatives contract. The mark price is typically calculated as the average of the best bid and best ask, while the index price is the price of the underlying index (usually based on the current value of a corresponding perpetual futures contract).

## **Details**

Exchanges report the following contract prices:

* Mark price: The estimated 'fair value' of a derivatives contract. Usually, this is the average of the best bid and best ask price. However, for risk management purposes, exchanges often set additional limits on price bandwidth.&#x20;
* Index price: The price of the contract's underlying index, typically calculated using the current value of a corresponding perpetual futures contract.

## **Example**

A sample of contract price data from our [`/timeseries/market-contract-prices`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketContractPrices) API endpoint is shown below for the `deribit-ETH-25MAR22-1200-P-option` market.

```
{
  "data" : [ {
    "market" : "deribit-BTC-11NOV22-20000-C-option",
    "time" : "2022-10-20T08:03:00.000000000Z",
    "database_time" : "2022-10-20T08:03:52.831102000Z",
    "mark_price" : "0.0791",
    "index_price" : "19153.67",
    "settlement_price_estimated" : "19153.67",
    "exchange_time" : "2022-10-20T08:03:51.768000000Z"
  }, {
    "market" : "deribit-BTC-11NOV22-20000-C-option",
    "time" : "2022-10-20T08:04:00.000000000Z",
    "database_time" : "2022-10-20T08:04:15.834472000Z",
    "mark_price" : "0.0791",
    "index_price" : "19154.68",
    "settlement_price_estimated" : "19154.68",
    "exchange_time" : "2022-10-20T08:04:14.938000000Z"
  } ]
}
```

*   **`market`**:  The id of the market. Market ids use the following naming convention for options markets: `exchangeName-optionsSymbol-option`&#x20;


*   **`time`**: The time at which Coin Metrics queried the contract price from an exchange in ISO 8601 date-time format. Always with nanoseconds precision.


*   **`mark_price`**:  The instrument market price, representing the contract's estimated "fair value."


*   **`index_price`**:  The price of the underlying benchmark index.


*   **`settlement_price_estimated`**: Represents what the underlying index settlement price would be if the contract immediately expired, helpful in calculating estimated profit and loss prior to contract expiration.


*   **`database_time`**:  The timestamp when the data was saved in the database in ISO 8601 date-time format with nanoseconds precision. Always with nanoseconds precision.


* **`exchange_time`**:  The timestamp reported by the exchange.  Can be null if the exchange does not report a timestamp.

## Release History

* [**CM MDF v2.5 on November 22, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-5-release-notes/): We expanded our options coverage to include several new data types, including market contract prices, from Deribit and added several new API endpoints to serve this data.
* [**CM MDF v2.7 on October 24, 2022**](https://coinmetrics.io/cm-market-data-feed-v2-7-release-notes/): Began collecting and serving the settlement price and estimated settlement price for option markets. The settlement price is served in our `/catalog/markets` endpoint and is available shortly after an option market expires. And the estimated settlement price is updated once a minute and served in our `/timeseries/market-contract-prices` endpoint.
