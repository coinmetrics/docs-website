---
description: /timeseries/market-trades
---

# Market Trades

## **Definition**

A trade is the exchange of a financial asset between a buyer and seller from a market on a trading venue. A financial asset can be a cryptoasset, a fiat currency, or a cryptoasset derivatives contract.&#x20;

## **Details**

Market participants can submit a buy order or sell order that indicate the amount and price level that a buyer or seller wishes to trade at. When the exchange receives an order, the order can be matched with another order or placed on the order book. An order book represents the list of unmatched buy orders and the list of unmatched sell orders for a given market organized by price level. When a market participant submits an order that matches with an existing order on the order book, the result is a trade.&#x20;

Coin Metrics collects trades data from **spot**, **future**, and **option** markets from exchanges that are listed on our exchange coverage universe.&#x20;

## **Example**

A sample of the trades data from the `coinbase-btc-usd-spot` market from our [`/timeseries/market-trades`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketTrades) API endpoint is provided below.&#x20;

```
{
  "data": [
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2015-01-08T20:55:00.028749000Z",
      "coin_metrics_id": "100",
      "amount": "1000.01",
      "price": "10.61",
      "database_time": "2016-06-08T20:55:00.256754000Z",
      "side": "buy"
    },
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2021-06-08T20:55:00.758178000Z",
      "coin_metrics_id": "200000000",
      "amount": "1000.01",
      "price": "1000000.61",
      "database_time": "2021-06-08T20:55:01.053472000Z",
      "side": "sell"
    }
  ]
}
```

* **`market`**:  The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets. \

* **`time`**:  The exchange-reported time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`coin_metrics_id`**:   Identifier of a trade that is unique per exchange.  We use the exchange-reported value if exchange reports a numeric trade ID, otherwise we convert to numeric using bijective mapping from exchange-reported trade ID’s string.\

* **`amount`**:  The amount of the base asset traded for spot markets or the number of contracts of a financial derivative.\

* **`price`**:  The price of the base asset quoted in the quote asset that the trade was executed at for spot markets or the price of one contract for derivatives markets.\

* **`side`**: The market order side. "buy" means that an ask was removed from the book by an incoming buy order, "sell" means that a bid was removed from the book by an incoming sell order.\

* **`database_time`**:  The time when we saved the data in the database. The time is in ISO 8601 date-time format. Always with nanoseconds precision.

## Frequently Asked Questions

### **What is the latency of your trades data?**

The exact latency varies depending on the exchange, but our median latency is approximately 150 milliseconds. The 95th percentile latency is 300 milliseconds, and the 99th percentile latency is 400 milliseconds.&#x20;

### **What is the historical coverage of your trades data?**

Our trades history for Bitcoin begins when it began trading on Mt.Gox in July 2010, so we have over 10 years of trades history. We also have full historical trades data from several other early exchanges such as Bitstamp, TheRockTrading, Bitfinex, and Kraken.&#x20;

Some exchanges allow users to query all of their historical trades data while other exchanges only allow users to query a short amount of history such as the past 1,000 trades. Coin Metrics always attempts to collect the maximum backhistory possible. If an exchange allows us to query historical trades data, we will collect data from every market starting from the inception of the exchange.&#x20;

### **Can you tell me more information on how to interpret the `coin_metrics_id` field?**

Exchanges serve each trades data with a unique identifier, typically labeled as trade id or uid. If an exchange’s unique identifier is an integer, we store the integer as is. If an exchange’s unique identifier is a base 16-encoded string, we convert the string to an integer and store that value. In general, if an exchange’s unique identifier is a string, we convert it to an integer using a bijective mapping function.&#x20;

The `coin_metrics_id` field ensures that all of our observations are unique. Even if two adjacent trades have identical `time`, `price`, `amount` and `side` fields, they are two distinct trades if they have unique `coin_metrics_id` and do not represent duplicate trades.&#x20;

Some exchanges use an incremental trade id that is represented by an integer that increments by 1 for every trade. Most exchanges will start this id at 1, so you can see how many trades have occurred in its lifetime. Also, it is useful for sequencing trades and determining whether all trades have been collected. Coinbase and Binance are two examples of exchanges that report their trade ids in this format.&#x20;

### **How do you ensure that the data contains no duplicate trades?**

Our market data collection system is designed to use multiple instances of each scraper for redundancy purposes. Although we run multiple instances of each scraper, we deduplicate observations using a composite primary key. For trades and liquidations data, the primary key consists of exchange, market id, and trade id. This ensures that each observation that we insert into our database is unique.

### **Is there a way to pull data for multiple markets in one API call?**

Yes! All of our endpoints that accept the `markets` parameter will accept wildcards  like `exchange-*` or `exchange-*-spot` or `*USDT-future`. The wildcards will match any market which fits this pattern so users do not need to specify every individual market when querying data for multiple markets. The `markets` parameter will also accept a comma-separated string of individual markets.&#x20;

### **What is the timestamp resolution of your trades data?**&#x20;

We always preserve the exchange-reported timestamp resolution, and the maximum resolution reported by some exchanges is at microsecond level. Our API serves time always using nanosecond precision.&#x20;

### **What is the difference between `time` and `database_time`?**

`time` represents the time logged by the given exchange, whereas `database_time` represents the time logged by Coin Metrics' database.

### **How is `database_time` useful?**

`database_time` can be useful to show collection lag time, which can be important for users who are running  backtests and simulations, and need to know exactly what data was available in a given point in time.

### **How come there is no trades data for a particular market?**

When spot markets that involve a new asset are listed on an exchange, there is a short period of time before we can support it. It involves adding this new asset to our security master file so that our market data collection system recognizes it. Please contact us at info@coinmetrics.io if you do not see a particular market, and we will investigate it.&#x20;

We collect data for spot markets in real-time that consist of existing assets that are already in our security master file without any delay. We also collect data for new futures and options markets in real-time without any delay. &#x20;

### **How come there are multiple trades with the same timestamp for a particular market?**

Sometimes there may be multiple trades that all occur with the same timestamp. The likely explanation is that an incoming taker order simultaneously matched with multiple existing orders on the order book, although from the available data it is not possible to determine how a particular order is matched with other orders. However, we are certain that each trade is unique even if one or more trades have identical timestamp, price, and amount with other trades.

### **Do you support any dexes/decentralized exchanges?**

We are currently supporting all major liquidity pools on Uniswap v2, Uniswap v3, and Sushiswap v1, and are actively expanding our DeFi universe.

### **How does Coin Metrics ensure high levels of data quality and data integrity?**

Please take a look at this question in the Market Data FAQs page linked below.&#x20;

{% content-ref url="market-data-faqs.md" %}
[market-data-faqs.md](market-data-faqs.md)
{% endcontent-ref %}

## **Release History**

* **CM MDF v1.0 on April 2020**: Added trades data for all spot markets on major exchanges. \

* **CM MDF v1.0 update on July 30, 2019**: Minor changes to trades websocket messages. \

* [**CM MDF v2.0 on December 9, 2019**](https://coinmetrics.io/release-of-cm-market-data-feed-version-2-0/): Added trades data for spot markets on Binance.US. Added trades data for futures markets on BitMEX and Huobi. \

* [**CM MDF v2.1 on May 5, 2020**](https://coinmetrics.io/market-data-feed-v2-1-release-notes/): Added trades data for spot markets on Kucoin and FTX. Added trades data for futures markets on Deribit, OKEx, Binance, FTX, and Bitfinex. \

* [**CM MDF v2.2 on December 2, 2020**](https://coinmetrics.io/cm-market-data-feed-futures-data-expansion/)**:** Added trades data for futures markets on bitFlyer and Kraken. \

* [**CM MDF v2.3 on April 25, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-3-release-notes/): Added trades data for spot markets on LMAX. Added trades data for futures markets on CME and Bybit. Added trades data for option markets on Deribit and OKEx. \

* [**CM MDF v2.4 on September 1, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-4-release-notes/): Extended trades data for Ethereum futures markets on CME.&#x20;
* [**CM MDF v2.6 on July 13, 2022**](https://coinmetrics.io/cm-market-data-feed-v2-6-release-notes/): Added DeFi coverage, and upgrades in areas like order book, candles, and API, etc

## **Availability**

The previous 24 hours of trades data is available through our community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our trades data is available through our professional API with higher rate limits. The professional API supports trades data through both our HTTP API and websocket API.&#x20;

Our coverage can be found by querying our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) or [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints. Alternatively, you can query our [`/catalog/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchanges)or [`/catalog-all/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchanges) API endpoints which contain the same information but organized by exchange.&#x20;

### Availability by Market Type&#x20;

| Type    | Market Count |
| ------- | :----------: |
| Spot    |     13440    |
| Futures |     6874     |
| Option  |     18560    |

### Availability by Exchange

| Exchange       | Spot Market Count | Future Market Count | Option Market Count | Start Date |
| -------------- | :---------------: | :-----------------: | :-----------------: | :--------: |
| Bibox          |        202        |                     |                     | 2019-04-24 |
| Binance        |        1580       |         220         |                     | 2017-07-14 |
| Binance.US     |        119        |                     |                     | 2019-09-23 |
| Bitbank        |         11        |                     |                     | 2017-02-14 |
| Bitfinex       |        533        |          35         |                     | 2013-01-14 |
| bitFlyer       |         9         |          64         |                     | 2019-05-28 |
| Bithumb        |         91        |                     |                     | 2013-12-27 |
| BitMEX         |                   |         302         |                     | 2014-11-22 |
| Bitstamp       |        108        |                     |                     | 2011-08-18 |
| Bittrex        |        1068       |                     |                     | 2019-03-21 |
| Bybit          |                   |          31         |                     | 2019-10-01 |
| Cex.IO         |        240        |                     |                     | 2013-12-27 |
| CME            |                   |         252         |                     | 2017-12-17 |
| Coinbase       |        304        |                     |                     | 2014-12-01 |
| Deribit        |                   |         121         |        11894        | 2017-01-06 |
| FTX            |        440        |         1189        |         487         | 2019-03-05 |
| Gate.io        |        1603       |                     |                     | 2017-09-29 |
| Gatecoin       |         80        |                     |                     | 2014-11-11 |
| Gemini         |         78        |                     |                     | 2018-10-16 |
| HitBTC         |        1517       |                     |                     | 2013-12-27 |
| Huobi          |        961        |         2630        |                     | 2019-03-15 |
| Kraken         |        394        |          79         |                     | 2013-09-10 |
| Kucoin         |        914        |                     |                     | 2020-04-02 |
| LBank          |        527        |                     |                     | 2017-09-29 |
| Liquid         |        481        |                     |                     | 2014-07-17 |
| LMAX           |         21        |                     |                     | 2021-02-18 |
| LocalBitcoins  |        119        |                     |                     | 2013-03-11 |
| Mt.Gox         |         16        |                     |                     | 2010-07-17 |
| OKEx           |        629        |         1951        |         6666        | 2018-12-25 |
| Poloniex       |        448        |                     |                     | 2014-01-18 |
| TheRockTrading |         30        |                     |                     | 2011-11-09 |
| Upbit          |        452        |                     |                     | 2019-03-14 |
| ZB.com         |        456        |                     |                     | 2019-03-04 |
