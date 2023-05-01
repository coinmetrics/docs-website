---
description: /timeseries/market-quotes
---

# Market Quotes

## **Definition**

Quotes consist of the best bid and the best ask for a market at a given point in time. The best bid represents the highest price that a buyer is willing to pay for one unit of the base asset for a spot market or one contract for a derivatives market. The best ask represents the lowest price that a seller is willing to sell.&#x20;

## Details

Quotes data is derived from our order book snapshot data by extracting the best bid and best ask. We serve quotes data through a separate endpoint as a convenience for users.&#x20;

Coin Metrics stores three types of order book snapshots. One type consists of a snapshot of the top 100 bids and top 100 asks taken once every 10 seconds for major markets. The second type includes all levels where the price is within 10 percent of the midprice taken once every 10 seconds. The third type consists of a full order book snapshot (every bid and every ask) taken once every hour for all markets that we are collecting order book data for. Quotes derived from these snapshots are served through our HTTP API endpoint [`/timeseries/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketQuotes).&#x20;

Coin Metrics also serves quotes in real-time for major markets through our websocket API endpoint [`/timeseries-stream/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesStreamMarketQuotes).&#x20;

For more information about our quotes data, please reference our [market order book](https://docs.coinmetrics.io/market-data/market-order-book) page.&#x20;

## **Example**

An sample of the quotes data the `coinbase-btc-usd-spot` market from our [`/timeseries/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketQuotes) API endpoint is provided below.

```
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

*   **`market`**:  The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets.&#x20;


* **`time`**:  The exchange-reported time in ISO 8601 date-time format.\

* **`coin_metrics_id`**:   Unique identifier of the order snapshot.\

* **`ask_price`**:  The price of the ask on the order book in units of the quote currency.\

* **`ask_size`**: The size of the ask on the order book in units of the base asset for a spot market or number of contracts for a derivatives market.\

* **`bid_price`**:  The price of the bid on the order book in units of the quote currency.\

* **`bid_size`**: The size of the bid on the order book in units of the base asset for a spot market or number of contracts for a derivatives market.

## Frequently Asked Questions&#x20;

Since our quotes data is derived from our order book data, please reference our [market order book](https://docs.coinmetrics.io/market-data/market-order-book) page for many frequently asked questions about order book data.&#x20;

{% content-ref url="market-order-book.md" %}
[market-order-book.md](market-order-book.md)
{% endcontent-ref %}

## **Release History**

* **CM MDF v1.0 on April 2019:** Quotes for major `btc-usd` and `eth-usd` markets. \

* **CM MDF v1.0 on July 30, 2019:** Added support for websocket endpoint which serves quotes in real-time. \

* [**CM MDF v2.0 on December 9, 2019**](https://coinmetrics.io/release-of-cm-market-data-feed-version-2-0/)**:** Expanded coverage universe to include `cex.io-btc-usd` and  `bitflyer-btc-spot`.\

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/)**:** Expanded our coverage universe to additional markets on Coinbase, Binance, FTX, Bitfinex, itBit. \

*   [**CM MDF v2.5 on November 22, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-5-release-notes/)**:** Expanded our coverage universe to additional spot markets on Binance, Binance.US, Bitfinex, bitFlyer, Bitstamp, Bittrex, CEX.io, Coinbase, FTX, Gemini, Huobi, itBit, Kraken, Kucoin, Liquid, and LMAX. Initiated coverage of futures markets on Binance, Bitfinex, bitFlyer, BitMEX, Bybit, Deribit, FTX, Huobi, Kraken, OKEx. Initiated real-time coverage of CME market quotes.        &#x20;

    &#x20;                                  &#x20;
* [**CM MDF v2.7 on October 24, 2022**](https://coinmetrics.io/cm-market-data-feed-v2-7-release-notes/)**:** Expanded our market coverage to include every single market, both spot and futures, on the following 12 exchanges: Binance, Binance.US, Bybit, Coinbase, Deribit, FTX, FTX.US, Gemini, HitBTC, Huobi, Kraken, OKEx. Began storing every single quote update in flat files starting in February 2022, suitable for any use cases that require historical data.

## **Availability**

The previous 24 hours of quotes data is available through our Community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our order book data is available through our professional API with higher rate limits. &#x20;

Our coverage universe is expanding rapidly. Please contact us at info@coinmetrics.io for the latest quotes coverage.&#x20;
