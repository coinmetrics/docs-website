# Bid-Ask Spread Percent

## Definition

Spread, one of the most common measures of liquidity and transaction costs, is the difference between the price that buyers are bidding at and the price that sellers are asking for. A large spread indicates disagreement between market participants on price and lends to inefficiencies in the market.

| Name                                        | MetricID                                 | Category  | Subcategory | Type  | Unit          | Interval |
| ------------------------------------------- | ---------------------------------------- | --------- | ----------- | ----- | ------------- | -------- |
| Liquidity Bid/Ask Spread Percentage, 1 Min  | liquidity\_bid\_ask\_spread\_percent\_1m | Liquidity | Spread      | Ratio | Dimensionless | 1m       |
| Liquidity Bid/Ask Spread Percentage, 1 Hour | liquidity\_bid\_ask\_spread\_percent\_1h | Liquidity | Spread      | Ratio | Dimensionless | 1h       |
| Liquidity Bid/Ask Spread Percentage, 1 Day  | liquidity\_bid\_ask\_spread\_percent\_1d | Liquidity | Spread      | Ratio | Dimensionless | 1d       |

## Details

Spread is normally calculated using the prices listed at the top of the book— that is, comparing the highest bidding price and the lowest asking price. There are many variations on spread in the literature, such as an effective spread that only uses market candle data and taking into account a degree of orderbook depth. However, here we stick to the classical formulation of spread.

Spread, the difference between the quote asset’s ask and bid price, can be presented raw or as a percentage of a reference price. Typically this reference price is the midpoint between the bid and asking price. Here we represent it as a percentage of the mid price.

We offer the bid-ask spread over 1m, 1h, and 1d intervals. Each of these metrics represents the average bid-ask spread over the interval of time.

## Examples

A sample of the daily bid-ask spread for the `coinbase-btc-usd-spot` market is shown below:

```
{
  "data": [
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2023-04-30T00:00:00.000000000Z",
      "liquidity_bid_ask_spread_percent_1d": "0.00581714797972098"
    },
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2023-05-01T00:00:00.000000000Z",
      "liquidity_bid_ask_spread_percent_1d": "0.007762221844825188"
    },
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2023-05-02T00:00:00.000000000Z",
      "liquidity_bid_ask_spread_percent_1d": "0.007638642427878028"
    },
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2023-05-03T00:00:00.000000000Z",
      "liquidity_bid_ask_spread_percent_1d": "0.008122796665005141"
    },
    {
      "market": "coinbase-btc-usd-spot",
      "time": "2023-05-04T00:00:00.000000000Z",
      "liquidity_bid_ask_spread_percent_1d": "0.007612002413638571"
    }
  ]
}
```

* **`market`**: The IDs of the market.\

* **`time`**: The time in ISO 8601 date-time format.\

* **`liquidity_bid_ask_spread_percent_1d`**: The daily average spread between the bid-ask price, represented as a percentage of the mid price.

## Frequenty Asked Questions

### What units are the bid-ask spread metrics in?

The values are in percent units. For example, if the value is 0.0076, it should be interpreted as 0.0076%.

## Release History

* **Release Version. Market Data Feed v2.8 on May 2023**.

