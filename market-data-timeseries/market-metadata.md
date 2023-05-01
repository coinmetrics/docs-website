---
description: /catalog/markets and /catalog-all/markets
---

# Market Metadata

## **Definition**

Market metadata includes descriptive and reference data about the listed markets on an exchange. The market metadata can include data about the trading parameters that govern valid orders such as amount and price precision, fees, current status, and several fields that describe a derivatives market contract specifications.

This data is served through our[`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) and [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) HTTP API endpoints.

## Details

Coin Metrics collects and serves metadata for **spot**, **futures**, and **options** markets.

Some metadata is available for all three market types. This includes data about the base asset and quote asset (or underlying base asset and quote asset for derivatives), the exchange-reported symbol, the market status, amount precision, maximum and minimum amount size, price precision, maximum and minimum price, and fee fields.

Spot markets also have a field that indicates whether the market allows margin trading.

Futures markets have several fields that describe the futures market's contract specifications. Futures markets trade in standardized contracts that allow counterparties to enter into an agreement to buy or sell a standardized asset under contract specifications that are defined by the exchange. The futures contract specifications include information such as the underlying base and quote asset, the margin asset, the contract size, the listing time, expiration time, and other terms. Here we define futures to include both non-perpetual futures that expire and perpetual futures (sometimes called perpetual swaps).

Options markets also trade in standardized contracts similar to futures markets described above. Options markets have several fields that are specific to options such as the strike price and whether the option is an European or American style option.

## **Example**

A sample of the futures and options contract specification data from our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) and [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints is shown below.&#x20;

```
{
  "data": [
    {
      "market": "gate.io-btc-usdt-spot",
      "min_time": "2017-10-12T08:43:02.000000000Z",
      "max_time": "2023-04-01T17:31:34.146000000Z",
      "exchange": "gate.io",
      "type": "spot",
      "trades": {
        "min_time": "2017-10-12T08:43:02.000000000Z",
        "max_time": "2023-04-01T17:31:34.146000000Z"
      },
      "base": "btc",
      "quote": "usdt",
      "symbol": "BTC_USDT",
      "status": "online",
      "order_amount_increment": "0.0001",
      "order_amount_min": "0.0001",
      "order_price_increment": "0.1",
      "order_size_min": "1",
      "order_taker_fee": "0.002",
      "order_maker_fee": "0.002"
    },
    {
      "market": "binance-BTCUSDT-future",
      "min_time": "2019-09-08T17:57:50.575000000Z",
      "max_time": "2023-04-01T17:32:20.321000000Z",
      "exchange": "binance",
      "type": "future",
      "trades": {
        "min_time": "2019-09-08T17:57:50.575000000Z",
        "max_time": "2023-04-01T17:32:20.321000000Z"
      },
      "orderbooks": {
        "min_time": "2021-08-18T16:07:20.000000000Z",
        "max_time": "2023-04-01T17:31:30.000000000Z"
      },
      "quotes": {
        "min_time": "2021-08-18T16:07:20.000000000Z",
        "max_time": "2023-04-01T17:31:30.000000000Z"
      },
      "funding_rates": {
        "min_time": "2019-09-10T08:00:00.000000000Z",
        "max_time": "2023-04-01T16:00:00.018000000Z"
      },
      "openinterest": {
        "min_time": "2020-07-27T17:40:36.223000000Z",
        "max_time": "2023-04-01T17:31:00.000000000Z"
      },
      "liquidations": {
        "min_time": "2019-09-10T19:36:50.009000000Z",
        "max_time": "2023-04-01T16:53:30.311000000Z"
      },
      "base": "btc",
      "quote": "usdt",
      "symbol": "BTCUSDT",
      "size_asset": "btc",
      "margin_asset": "usdt",
      "contract_size": "1",
      "tick_size": "0.1",
      "listing": "2019-09-25T08:00:00.000000000Z",
      "order_amount_increment": "0.001",
      "order_amount_min": "0.001",
      "order_amount_max": "1000",
      "order_price_increment": "0.10",
      "order_price_min": "556.80",
      "order_price_max": "4529764",
      "order_size_min": "5"
    },
    {
      "market": "deribit-BTC-10APR21-50000-P-option",
      "min_time": "2021-04-08T08:13:28.493000000Z",
      "max_time": "2021-04-08T08:16:51.756000000Z",
      "exchange": "deribit",
      "type": "option",
      "trades": {
        "min_time": "2021-04-08T08:13:28.493000000Z",
        "max_time": "2021-04-08T08:16:51.756000000Z"
      },
      "base": "btc",
      "quote": "usd",
      "symbol": "BTC-10APR21-50000-P",
      "size_asset": "btc",
      "strike": "50000",
      "option_contract_type": "put",
      "is_european": true,
      "contract_size": "1",
      "listing": "2021-04-08T08:00:06.000000000Z",
      "expiration": "2021-04-10T08:00:00.000000000Z",
      "settlement_price": "60483.68",
      "order_price_increment": "0.0005"
    }
  ]
}
```

* **`market`**:  Unique name of the market. \

* **`min_time`**:  Minimal available time for data from this market in ISO 8601 date-time format.\

* **`max_time`**:  Maximal available time for data from this market in ISO 8601 date-time format.\

* **`exchange`**: Name of the exchange.\

* **`type`**: The type of the market. Can take values `spot` or `future` or `option`.\

* **`base`**:  The contract’s underlying base asset.\

* **`quote`**:  The contract's underlying quote asset.\

* **`symbol`**: The exchange-reported symbol for the market.\

* **`status`**: Indicates whether the market is online. Can only take values `online` or `offline`.\

* **`order_amount_increment`**: The minimum increment that the trade amount of an order can change in units of the base currency if a spot market or in contract units if a derivatives market.\

* **`order_amount_min`**: The minimum trade amount of an order in units of the base currency if a spot market or in contract units if a derivatives market.\

* **`order_amount_max`**: The maximum trade amount of an order in units of the base currency if a spot market or in contract units if a derivatives market.\

* **`order_price_increment`**: The minimum increment that the price of an order can change. The price is quoted in units of the quote currency.\

* **`order_price_min`**: The minimum price of an order. The price is quoted in units of the quote currency.\

* **`order_price_max`**: The maximum price of an order. The price is quoted in units of the quote currency.\

* **`order_size_min`**: The minimum order size amount in units of the quote currency. The order size is the order amount multiplied by the order price.\

* **`order_taker_fee`**: The taker order fee in raw units (not percent units).\

* **`order_maker_fee`**: The maker order fee in raw units (not percent units).\

* **`market_margin_trading_enabled`**: Indicates whether the market allows margin trading. Can take values `true` or `false`.\

* **`size_asset`**: The asset that the contract’s size is denominated in.\

* **`margin_asset`**:  The name of the asset that the contract’s margin is denominated in.\

* **`contract_size`**:   The number of units of `size_asset` that one contract represents. \

* **`tick_size`**:  The minimum price increment of the contract’s price.\

* **`listing`**:  The timestamp that the contract first became available for trading\

* **`expiration`**:  The timestamp that the contract expires; equals null if the contract is a perpetual future that never expires.\

* **`is_european`**: Shows if the options contract is european or not.\

* **`option_contract_type`**: The type of option. Can take values `call` or `put`.\

* **`strike`**: Strike price for option contract.\

* **`settlement_price`**: The settlement price of a derivatives contract at expiration. Only populated for derivatives markets that have expired. Also sometimes referred to as "delivery price".

## Frequently Asked Questions&#x20;

### Do all exchanges offer these metadata fields?

Exchanges vary in which fields they offer through their API. If an exchange does not offer a particular field, Coin Metrics will consult the exchange's published documentation and manually populate some fields. If neither the exchange's API nor documentation can be used to populate a field, then that field is omitted from the response for that particular market.

### **Is the `margin_asset` the asset of settlement?**&#x20;

Yes, the `margin_asset` is the asset of settlement. A trader must post this asset as the initial margin when opening a position**.** Unrealized gains and losses are calculated in this asset, and a trader receives gains or losses denominated in this asset when the trader closes the position or the contract expires.&#x20;

### **Is there a way to filter between perpetual, coin-margined, and tether-margined futures in the catalog?**

We are working on adding filtering parameters for the various futures contract types. In the meantime, perp contracts can be identified by null `expiration` time. Coin margined contracts can be identified where the `base` is identical to `margin_asset`. Tether margined contracts can be identified where the `margin_asset` is `usdt`.

## Harmonization Discussion&#x20;

Harmonization of derivatives contracts in the cryptoasset domain is difficult because there is wide disparity in contract design and exchange conventions. Some of the sources of difficulty include:

* The margin asset can be in the form of the underlying base asset, a stablecoin such as Tether, or a fiat currency. \

* The contract size (the amount of notional exposure that a single contract is worth) can be in the form of varying units such as the underlying base asset or a fiat currency. Some exchanges use exotic futures design (such as BitMEX's quanto contracts) where the contract size is not fixed but rather a function of the current price. \

* Some exchanges offer exotic futures contracts where the underlying is not a cryptoasset. Instead, it could be a custom index, an equity, or something else like Bitcoin's hash rate. \

* Some exchanges hide the complexity involved with contract sizes and do not use contract sizes. Instead, they allow users to define the amount of units of the underlying base asset when trading and allow users to purchase fractional contracts (representing fractional units of the underlying) to simulate spot trading. Other exchanges explicitly define contract sizes and do not allow users to purchase fractional contracts.\

* Some exchanges separate perpetual swap contracts that have no expiration date and traditional futures contracts with a specified expiration date. These exchanges serve contract information via two different endpoints with different response schema.\

* Some exchanges do not provide all contract specification data via their API but instead define it in documentation.

We harmonize the data in the following way:&#x20;

* For exchanges that do not explicitly define the contract size and implicitly use a contract size of 1 unit of the underlying base asset, we set the contract size to 1.\

* In instances where the exchange's API does not contain all fields that we wish to capture, we consult the exchange's documentation and manually populate the data.

## Release History

* [**CM MDF v2.2 on December 2, 2020**](https://coinmetrics.io/cm-market-data-feed-futures-data-expansion/)**:** Added futures contract specification data for Binance, BitMEX, bitFlyer, Bitfinex, Deribit, FTX, Huobi, and OKEx.\

* [**CM MDF v2.3 on April 25, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-3-release-notes/): Added futures contract specifications data for CME and Bybit. Added options contract specifications for Deribit and OKEx.\

* [**CM MDF v2.7 on October 24, 2022**](https://coinmetrics.io/cm-market-data-feed-v2-7-release-notes/): Added settlement price for option markets.

## **Availability**

Contract specification data is available through our community API.  Community data is available via HTTP API only and is limited to 10 API requests per 6 seconds per IP address. All of our contract specification data is available through our professional API with higher rate limits.

The contract specifications and our coverage can be found by querying our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) or [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints.

The availability below was last updated on April 1, 2023. For the most updated coverage, please visit [Coin Metrics Coverage](https://coverage.coinmetrics.io/).

### Availability by Market Type

| Market Type | Market Count |
| ----------- | ------------ |
| future      | 13163        |
| option      | 98950        |
| spot        | 27380        |

### Availability by Exchange

| Exchange           | Spot Market Count | Future Market Count | Option Market Count | Start Date |
| ------------------ | ----------------- | ------------------- | ------------------- | ---------- |
| bibox              | 714               |                     |                     | 2019-04-24 |
| binance            | 2171              | 422                 |                     | 2017-07-13 |
| binance.us         | 362               |                     |                     | 2019-09-04 |
| bitbank            | 32                |                     |                     | 2017-02-14 |
| bitfinex           | 738               | 76                  |                     | 2013-01-14 |
| bitflyer           | 11                | 144                 |                     | 2019-05-28 |
| bithumb            | 91                |                     |                     | 2013-12-27 |
| bitmex             |                   | 452                 |                     | 2014-11-22 |
| bitstamp           | 199               |                     |                     | 2011-08-18 |
| bittrex            | 1454              |                     |                     | 2019-03-21 |
| bullish            | 26                |                     |                     | 2023-03-07 |
| bybit              | 393               | 246                 |                     | 2018-11-15 |
| cex.io             | 321               |                     |                     | 2013-12-27 |
| cme                |                   | 465                 |                     | 2017-12-17 |
| coinbase           | 657               |                     |                     | 2014-12-01 |
| crypto.com         | 681               |                     |                     | 2022-06-24 |
| deribit            |                   | 335                 | 67550               | 2017-01-06 |
| ftx                | 625               | 1684                |                     | 2019-03-05 |
| ftx.us             | 67                |                     |                     | 2020-04-05 |
| gate.io            | 3117              | 281                 |                     | 2017-09-29 |
| gatecoin           | 80                |                     |                     | 2014-11-11 |
| gemini             | 146               |                     |                     | 2018-10-16 |
| hitbtc             | 2069              | 32                  |                     | 2013-12-27 |
| huobi              | 1559              | 4360                |                     | 2019-03-15 |
| itbit              | 14                |                     |                     | 2019-03-13 |
| kraken             | 686               | 266                 |                     | 2013-09-10 |
| kucoin             | 1630              | 159                 |                     | 2020-04-02 |
| lbank              | 2049              |                     |                     | 2017-09-29 |
| liquid             | 637               |                     |                     | 2014-07-24 |
| lmax               | 21                |                     |                     | 2021-02-18 |
| localbitcoins      | 122               |                     |                     | 2013-03-11 |
| mexc               | 2518              | 272                 |                     | 2022-10-13 |
| mt.gox             | 16                |                     |                     | 2010-07-17 |
| okex               | 952               | 3957                | 31400               | 2018-12-25 |
| poloniex           | 803               |                     |                     | 2014-01-18 |
| sushiswap\_v1\_eth | 146               |                     |                     | 2020-09-04 |
| therocktrading     | 44                |                     |                     | 2011-11-09 |
| uniswap\_v2\_eth   | 413               |                     |                     | 2020-05-05 |
| uniswap\_v3\_eth   | 657               |                     |                     | 2021-05-04 |
| upbit              | 532               |                     |                     | 2019-03-14 |
| zb.com             | 624               |                     |                     | 2019-03-04 |
