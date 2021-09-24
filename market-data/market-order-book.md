---
description: /timeseries/market-orderbooks
---

# Market Order Book

## **Definition**

An order book represents the list of buy orders and the list of sell orders for a given market organized by price level.  In this context, a buy order or sell order indicates the amount of the base asset that a buyer or seller wishes to trade for a spot market or the amount of contracts for a derivatives market. 

## Details

The price and amount that a trader is willing to buy is referred to as the bid. The price and amount that a trader is willing to sell is referred to as the ask. When a trade is executed between a buyer and a seller, an order is removed from the order book. While an order book is constantly updated in real-time as traders post new orders and as orders are matched, this data type represents a snapshot of the order book at a given moment in time. 

Coin Metrics stores two types of order book snapshots. One type consists of a snapshot of the top 100 bids and top 100 asks taken once every 10 seconds.  The second type consists of a full order book snapshot \(every bid and every ask\) taken once every hour. Both of these snapshots are served through our HTTP API endpoint [`/timeseries/market-orderbooks`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketOrderbooks).

Coin Metrics also serves order book snapshots and updates for the top 100 bids and 100 asks for major markets through our websocket API endpoint [`/timeseries-stream/market-orderbooks`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamMarketOrderbooks). The first message that the client receives is an order book snapshot. All subsequent messages are updates to the order book. This allows a user to maintain the current state of the order book at all times by storing the order book state locally and applying updates to it.  

## **Example**

A sample of the order book snapshot data from the `coinbase-btc-usd-spot`market is provided below. 

```text
{
  "data": [
    {
      "time": "2020-06-08T21:01:23.283083000Z",
      "market": "coinbase-btc-usd-spot",
      "coin_metrics_id": "1591479594286046-27268420",
      "asks": [
        {
          "price": "9701.48",
          "size": "2.65178241"
        },
        {
          "price": "9701.49",
          "size": "0.10941481"
        }
      ],
      "bids": [
        {
          "price": "9701.4",
          "size": "4.43779413"
        },
        {
          "price": "9699.94",
          "size": "0.041"
        }
      ]
    }
  ]
}
```

* **`market`**:  The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets. 

* **`time`**:  The exchange-reported time in ISO 8601 date-time format. 
* **`coin_metrics_id`**:   Unique identifier of the order snapshot. 
* **`price`**:  The price of the bid or ask on the order book in units of the quote currency. 
* **`size`**: The size of the bid or ask on the order book in units of the base asset for a spot market or number of contracts for a derivatives market.

## Release History

* **CM MDF v1.0 on April 2019:** Partial snapshots for major `btc-usd` and `eth-usd` markets.  
* **CM MDF v1.0 on July 30, 2019:** Added support for websocket endpoint which serves an initial snapshot and order book updates.  
* \*\*\*\*[**CM MDF v2.0 on December 9, 2019**](https://coinmetrics.io/release-of-cm-market-data-feed-version-2-0/)**:** Expanded coverage universe to include `cex.io-btc-usd` and  `bitflyer-btc-spot`. 
* \*\*\*\*[**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)**:** Expanded both the depth of our order book snapshot coverage and our coverage universe. For important markets, we maintain a snapshot of the top 100 levels at 10 second intervals. Started storing full order book snapshots at hourly intervals. Expanded our coverage universe to additional markets on Coinbase, Binance, FTX, Bitfinex, itBit.

## **Availability**

The previous 24 hours of order book data is available through our community API.  Community data is available via HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address. All of our order book data is available through our professional API with higher rate limits.  

Our coverage universe is expanding rapidly. Please contact us at info@coinmetrics.io for the latest order book coverage. 





