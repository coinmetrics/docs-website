# Bid/Ask Spread Percentage

## Definition

Spread, one of the most common measures of liquidity, is the difference between the price that buyers are bidding at and the price that sellers are asking for. A large spread indicates disagreement between market participants on price and lends to inefficiencies in the market.

| Name                                        | MetricID                                 | Category  | Subcategory | Type  | Unit          | Interval |
| ------------------------------------------- | ---------------------------------------- | --------- | ----------- | ----- | ------------- | -------- |
| Liquidity Bid/Ask Spread Percentage, 1 Min  | liquidity\_bid\_ask\_spread\_percent\_1m | Liquidity | Spread      | Ratio | Dimensionless | 1m       |
| Liquidity Bid/Ask Spread Percentage, 1 Hour | liquidity\_bid\_ask\_spread\_percent\_1h | Liquidity | Spread      | Ratio | Dimensionless | 1h       |
| Liquidity Bid/Ask Spread Percentage, 1 Day  | liquidity\_bid\_ask\_spread\_percent\_1d | Liquidity | Spread      | Ratio | Dimensionless | 1d       |

## Details

Spread is normally calculated using the prices listed at the top of the book— that is, comparing the highest bidding price and the lowest asking price. There are many variations on spread in the literature, such as an effective spread that only uses market candle data and taking into account a degree of orderbook depth. However, here we stick to the classical formulation of spread.

Spread, the difference between the quote asset’s ask and bid price, can be presented raw or as a percentage of a reference price. Typically this reference price is the midpoint between the bid and asking price. Here we represent it as a percentage of the mid price.

## Examples

A sample of the daily bid/ask spread for the Binance BTC-USDT spot market is shown below:

| market                | time                | liquidity\_bid\_ask\_spread\_percent\_1d |
| --------------------- | ------------------- | ---------------------------------------- |
| binance-btc-usdt-spot | 2023-01-01 00:00:00 | 0.0018301678456105772                    |
| binance-btc-usdt-spot | 2023-01-02 00:00:00 | 0.0018140166375616342                    |
| binance-btc-usdt-spot | 2023-01-03 00:00:00 | 0.0014764028562506938                    |
| binance-btc-usdt-spot | 2023-01-04 00:00:00 | 0.0018090893435908008                    |

* market. The IDs of the markets.
* time. The time in ISO 8601 date-time format.
* liquidity\_bid\_ask\_spread\_percent\_1d. The daily average spread between the bid/ask price and the mid price, represented as a percentage of the mid price.

## Release History

* Release Version. Market Data Feed (January 2023)
