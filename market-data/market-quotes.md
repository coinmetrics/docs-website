---
description: /timeseries/market-quotes
---

# Market Quotes

## **Definition**

Quotes consist of the best bid and the best ask for a market at a given point in time. The best bid represents the highest price that a buyer is willing to pay for one unit of the base asset for a spot market or one contract for a derivatives market. The best ask represents the lowest price that a seller is willing to sell. 

## Details

Quotes data is derived from our order book snapshot data by extracting the best bid and best ask. We serve quotes data through a separate endpoint as a convenience for users. 

Coin Metrics stores two types of order book snapshots. One type consists of a snapshot of the top 100 bids and top 100 asks taken once every 10 seconds.  The second type consists of a full order book snapshot \(every bid and every ask\) taken once every hour. Quotes derived from both of these snapshots are served through our HTTP API endpoint [`/timeseries/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketQuotes). 

Coin Metrics also serves quotes in real-time for major markets through our websocket API endpoint [`/timeseries-stream/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamMarketQuotes). 

## **Example**

An sample of the quotes data the `coinbase-btc-usd-spot` market is provided below:

![](../.gitbook/assets/0%20%283%29.png)

A sample of the quotes data in json format is also provided below. 

```text
{
  "data": [
    {
      "time": "2020-06-08T21:14:48.215145000Z",
      "market": "coinbase-btc-usd-spot",
      "coin_metrics_id": "1591479594286046-27326992",
      "ask_price": "9685.02",
      "ask_size": "0.04340557",
      "bid_price": "9685.01",
      "bid_size": "0.00484254"
    }
  ]
}
```

* **`market`**:  The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets. 

* **`time`**:  The exchange-reported time in ISO 8601 date-time format. 
* **`coin_metrics_id`**:   Unique identifier of the order snapshot. 
* **`ask_price`**:  The price of the ask on the order book in units of the quote currency. 
* **`ask_size`**: The size of the ask on the order book in units of the base asset for a spot market or number of contracts for a derivatives market. 
* **`bid_price`**:  The price of the bid on the order book in units of the quote currency. 
* **`bid_size`**: The size of the bid on the order book in units of the base asset for a spot market or number of contracts for a derivatives market.

## **Release History**

* **CM MDF v1.0 on April 2019:** Quotes for major `btc-usd` and `eth-usd` markets.  
* **CM MDF v1.0 on July 30, 2019:** Added support for websocket endpoint which serves quotes in real-time.  
* **CM MDF v2.0 on December 9, 2019:** Expanded coverage universe to include `cex.io-btc-usd` and  `bitflyer-btc-spot`. 
* \*\*\*\*[**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)**:** Expanded our coverage universe to additional markets on Coinbase, Binance, FTX, Bitfinex, itBit.

## **Availability**

The previous 24 hours of quotes data is available through our Community API.  Community data is available via HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address. All of our order book data is available through our professional API with higher rate limits.  

Our coverage universe is expanding rapidly. Please contact us at info@coinmetrics.io for the latest quotes coverage. 





