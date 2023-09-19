---
description: /security-master/markets
---

# Security Master Markets

## Definition

The Coin Metrics Security Master contains references data about all spot markets, futures markets, and options markets on which the assets in our coverage universe are traded on.

## Details

The reference data for markets includes the data availability, contract specifications, trading parameters, and latest prices for each market.

## Example

A sample of the futures and options contract specification data from our [`/security-master/markets`](https://docs.coinmetrics.io/api/v4/#tag/Security-Master/operation/getSecurityMasterMarkets) API endpoint is shown below.&#x20;

```
{
  "data" : [ {
  "market" : "coinbase-btc-usd-spot",
  "exchange" : "coinbase",
  "type" : "spot",
  "code" : "C758EA35B0",
  "pair" : "btc-usd",
  "trades_min_time" : "2014-12-01T05:33:56.761199000Z",
  "trades_max_time" : "2023-09-19T01:40:36.904919000Z",
  "orderbooks_min_time" : "2019-03-25T18:46:25.000000000Z",
  "orderbooks_max_time" : "2023-09-19T01:40:30.000000000Z",
  "quotes_min_time" : "2019-03-25T18:46:25.000000000Z",
  "quotes_max_time" : "2023-09-19T01:40:30.000000000Z",
  "base" : "btc",
  "quote" : "usd",
  "symbol" : "BTC-USD",
  "price_open" : "26569.69",
  "price_close" : "26530.95",
  "price_high" : "26626.49",
  "price_low" : "26405.04",
  "vwap" : "26521.61401947972",
  "volume" : "3252.26976131",
  "candle_usd_volume" : "86255443.296689279280656486854347",
  "candle_trades_count" : "121841"
}, {
  "market" : "binance-BTCUSDT-future",
  "exchange" : "binance",
  "type" : "future",
  "code" : "C758EA35B0",
  "pair" : "btc-usdt",
  "trades_min_time" : "2019-09-08T17:57:50.575000000Z",
  "trades_max_time" : "2023-09-19T01:40:37.892000000Z",
  "orderbooks_min_time" : "2021-08-18T16:07:20.000000000Z",
  "orderbooks_max_time" : "2023-09-19T01:40:30.000000000Z",
  "quotes_min_time" : "2021-08-18T16:07:20.000000000Z",
  "quotes_max_time" : "2023-09-19T01:40:30.000000000Z",
  "funding_rates_min_time" : "2019-09-10T08:00:00.000000000Z",
  "funding_rates_max_time" : "2023-09-19T00:00:00.000000000Z",
  "openinterest_min_time" : "2020-07-27T17:40:36.223000000Z",
  "openinterest_max_time" : "2023-09-19T01:39:00.000000000Z",
  "liquidations_min_time" : "2019-09-10T19:36:50.009000000Z",
  "liquidations_max_time" : "2023-09-19T01:06:39.140000000Z",
  "base" : "btc",
  "quote" : "usdt",
  "symbol" : "BTCUSDT",
  "size_asset" : "btc",
  "margin_asset" : "usdt",
  "contract_size" : "1",
  "tick_size" : "0.1",
  "listing" : "2019-09-25T08:00:00.000000000Z",
  "order_amount_increment" : "0.001",
  "order_amount_min" : "0.001",
  "order_amount_max" : "1000",
  "order_price_increment" : "0.10",
  "order_price_min" : "556.80",
  "order_price_max" : "4529764",
  "order_size_min" : "5",
  "price_open" : "26547",
  "price_close" : "26514.2",
  "price_high" : "26614.3",
  "price_low" : "26377.4",
  "vwap" : "26501.52761178513",
  "volume" : "114239.394",
  "candle_usd_volume" : "3029921015.78049",
  "candle_trades_count" : "1246715"
}, {
  "market" : "deribit-BTC-19SEP23-29000-C-option",
  "exchange" : "deribit",
  "type" : "option",
  "code" : "C758EA35B0",
  "pair" : "btc-usd",
  "trades_min_time" : "2023-09-16T18:32:17.597000000Z",
  "trades_max_time" : "2023-09-18T12:37:51.139000000Z",
  "orderbooks_min_time" : "2023-09-16T08:01:00.000000000Z",
  "orderbooks_max_time" : "2023-09-19T01:40:00.000000000Z",
  "quotes_min_time" : "2023-09-16T08:01:00.000000000Z",
  "quotes_max_time" : "2023-09-19T01:40:00.000000000Z",
  "openinterest_min_time" : "2023-09-16T08:01:00.000000000Z",
  "openinterest_max_time" : "2023-09-19T01:40:00.000000000Z",
  "base" : "btc",
  "quote" : "usd",
  "symbol" : "BTC-19SEP23-29000-C",
  "size_asset" : "btc",
  "strike" : "29000",
  "option_contract_type" : "call",
  "is_european" : true,
  "contract_size" : "1",
  "listing" : "2023-09-16T08:01:00.000000000Z",
  "expiration" : "2023-09-19T08:00:00.000000000Z",
  "status" : "online",
  "order_amount_min" : "0.1",
  "order_price_increment" : "0.0001",
  "order_taker_fee" : "0.0003",
  "order_maker_fee" : "0.0003"
} ]
}
```

* **`market`**:  Unique name of the market. \

* **`type`**: The type of the market. Can take values `spot` or `future` or `option`.\

* **`code`**: The unique and immutable code associated with the base asset of the market. Each code is 10 digit alphanumeric string that starts with C and ends with a checksum digit. This code is immutable so it will not change if an asset undergoes a rebranding or symbol change.\

* **`pair`**: The concatenation of the market's base and quote.\

* **`trades_min_time`**: The timestamp of the first trade in Coin Metrics historical dataset.\

* **`trades_max_time`**: The timestamp of the last trade in Coin Metrics historical dataset.\

* **`orderbooks_min_time`**: The timestamp of the first order book snapshot in Coin Metrics historical dataset.\

* **`orderbooks_max_time`**: The timestamp of the last order book snapshot in Coin Metrics historical dataset.\

* **`quotes_min_time`**: The timestamp of the first quotes snapshot in Coin Metrics historical dataset.\

* **`quotes_max_time`**: The timestamp of the last quotes snapshot in Coin Metrics historical dataset.\

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

* **`settlement_price`**: The settlement price of a derivatives contract at expiration. Only populated for derivatives markets that have expired. Also sometimes referred to as "delivery price".\

* **`price_open`**:   The opening price of the most recent daily candle.\

* **`price_high`**:  The high price of the most recent daily candle.\

* **`price_low`**:  The low price of the most recent daily candle.\

* **`price_close`**: The close price of the most recent daily candle.\

* **`vwap`**:  The volume-weighted average price of the most recent daily candle.\

* **`volume`**: The volume of the most recent daily candle in units of the base asset.\

* **`candle_usd_volume`**: The volume of the most recent daily candle in units of U.S. dollars. \

* **`candle_trades_count`**: The number of trades in the most recent daily candle interval.&#x20;

## Release History

* **Coin Metrics Security Master v1.0 on September 18, 2023**: Initial release.
