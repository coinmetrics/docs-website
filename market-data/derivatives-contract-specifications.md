---
description: /catalog/markets and /catalog-all/markets
---

# Derivatives Contract Specifications

## **Definition**

Derivatives contracts can be described by their contract specifications which define the standardized legal agreement that market participants enter into. 

## Details

Futures and options contracts are standardized contracts that allow counterparties to enter into an agreement to buy or sell a standardized asset under contract specifications that are defined by the exchange. Each specific futures contract offered by a specific exchange will have identical contract specifications regardless of the who is counterparty. 

The contract specifications include information such as the underlying base and quote asset, the margin asset, the contract size, the listing time, expiration time, and other terms. 

Coin Metrics offers contract specifications for both **futures** and **options**. Here we define **futures** to include both non-perpetual futures that expire and perpetual futures.  

## Harmonization Discussion 

Harmonization of derivatives contracts in the cryptoasset domain is difficult because there is wide disparity in contract design and exchange conventions. Some of the sources of difficulty include:

* The margin asset can be in the form of the underlying base asset, a stablecoin such as Tether, or a fiat currency.  
* The contract size \(the amount of notional exposure that a single contract is worth\) can be in the form of varying units such as the underlying base asset or a fiat currency. Some exchanges use exotic futures design \(such as BitMEX's quanto contracts\) where the contract size is not fixed but rather a function of the current price.  
* Some exchanges offer exotic futures contracts where the underlying is not a cryptoasset. Instead, it could be a custom index, an equity, or something else like Bitcoin's hash rate.  
* Some exchanges hide the complexity involved with contract sizes and do not use contract sizes. Instead, they allow users to define the amount of units of the underlying base asset when trading and allow users to purchase fractional contracts \(representing fractional units of the underlying\) to simulate spot trading. Other exchanges explicitly define contract sizes and do not allow users to purchase fractional contracts. 
* Some exchanges separate perpetual swap contracts that have no expiration date and traditional futures contracts with a specified expiration date. These exchanges serve contract information via two different endpoints with different response schema. 
* Some exchanges do not provide all contract specification data via their API but instead define it in documentation.

We harmonize the data in the following way: 

* For exchanges that do not explicitly define the contract size and implicitly use a contract size of 1 unit of the underlying base asset, we set the contract size to 1.  
* In instances where the exchange's API does not contain all fields that we wish to capture, we consult the exchange's documentation and manually populate the data.   

## **Example**

A sample of the futures and options contract specification data from our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) and [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints.is shown below. 

```text
{
  "data": [
    {
      "market": "binance-BTCUSDT-future",
      "min_time": "2019-09-08T17:57:50.575000000Z",
      "max_time": "2021-09-20T22:14:51.113000000Z",
      "exchange": "binance",
      "type": "future",
      "base": "btc",
      "quote": "usdt",
      "symbol": "BTCUSDT",
      "size_asset": "btc",
      "margin_asset": "usdt",
      "contract_size": "1",
      "tick_size": "0.01",
      "listing": "2019-09-25T08:00:00.000000000Z"
    },
    {
      "market": "binance-BTCUSDT_210326-future",
      "min_time": "2021-02-03T08:20:24.560000000Z",
      "max_time": "2021-03-26T07:51:05.584000000Z",
      "exchange": "binance",
      "type": "future",
      "base": "btc",
      "quote": "usdt",
      "symbol": "BTCUSDT_210326",
      "size_asset": "btc",
      "margin_asset": "usdt",
      "contract_size": "1",
      "tick_size": "0.1",
      "listing": "2021-02-02T08:00:00.000000000Z",
      "expiration": "2021-03-26T08:00:00.000000000Z"
    },
    {
      "market": "deribit-BTC-10APR21-50000-P-option",
      "min_time": "2021-04-08T08:13:28.493000000Z",
      "max_time": "2021-04-08T08:16:51.756000000Z",
      "exchange": "deribit",
      "type": "option",
      "base": "btc",
      "quote": "usd",
      "symbol": "BTC-10APR21-50000-P",
      "size_asset": "btc",
      "strike": "50000.0",
      "option_contract_type": "put",
      "is_european": true,
      "contract_size": "1",
      "listing": "2021-04-08T08:00:06.000000000Z",
      "expiration": "2021-04-10T08:00:00.000000000Z"
    }
  ]
}
```

* **`market`**:  Unique name of the market.  
* **`min_time`**:  Minimal available time for data from this market in ISO 8601 date-time format. 
* **`max_time`**:  Maximal available time for data from this market in ISO 8601 date-time format. 
* **`exchange`**: Name of the exchange. 
* **`base`**:  The contract’s underlying base asset. 
* **`quote`**:  The contract's underlying quote asset. 
* **`symbol`**: The unique name of the derivative market symbol. 
* **`type`**: The type of the market. Can take values `spot` or `future` or `option`. 
* **`size_asset`**: The asset that the contract’s size is denominated in. 
* **`margin_asset`**:  The name of the asset that the contract’s margin is denominated in. 
* **`strike`**: Strike price for option contract.  
* **`option_contract_type`**: The type of option. Can take values `call` or `put`. 
* **`is_european`**: Shows if the options contract is european or not.  
* **`contract_size`**:   The number of units of `size_asset` that one contract represents.  
* **`tick_size`**:  The minimum price increment of the contract’s price. 
* **`listing`**:  The timestamp that the contract first became available for trading 
* **`expiration`**:  The timestamp that the contract expires; equals null if the contract is a perpetual future that never expires.

## Release History

* **CM MDF v2.2 on December 7, 2020:** Added futures contract specification data for Binance, BitMEX, bitFlyer, Bitfinex, Deribit, FTX, Huobi, and OKEx.  
* \*\*\*\*[**CM MDF v2.3 on April 25, 2021**](https://coinmetrics.io/cm-market-data-feed-v2-3-release-notes/): Added futures contract specifications data for CME and Bybit. Added options contract specifications for Deribit and OKEx. 

## **Availability**

Contract specification data is available through our community API.  Community data is available via HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address. All of our contract specification data is available through our professional API with higher rate limits.  

The contract specifications and our coverage can be found by querying our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) or [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints.

### Markets

| Type | Market Count |
| :--- | :---: |
| Future | 6874 |
| Option | 18560 |

### Exchanges

| Exchange | Future Market Count | Option Market Count | Start Date |
| :--- | :---: | :---: | :---: |
| Binance | 220 |  | 2019-09-08 |
| Bitfinex | 35 |  | 2019-07-03 |
| Bitflyer | 64 |  | 2020-07-27 |
| BitMEX | 302 |  | 2014-11-22 |
| Bybit | 31 |  | 2019-10-01 |
| CME | 252 |  | 2017-12-17 |
| Deribit | 121 | 11894 | 2017-01-06 |
| FTX | 1189 |  | 2019-03-05 |
| Huobi | 2630 |  | 2019-10-11 |
| Kraken | 79 |  | 2020-08-24 |
| OKEx | 1951 | 6666 | 2019-12-25 |

