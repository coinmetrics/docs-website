# Liquidity Slippage Bid Percentage

## Definition

Price slippage is the difference between the quoted price of an asset and the execution price of a market order.&#x20;

| Name                                       | MetricID                                | Category  | Subcategory | Type  | Unit          | Interval |
| ------------------------------------------ | --------------------------------------- | --------- | ----------- | ----- | ------------- | -------- |
| Liquidity Slippage Percentage, $1K Bid     | liquidity\_slippage\_1K\_bid\_percent   | Liquidity | Slippage    | Ratio | Dimensionless | 1h       |
| Liquidity Slippage Percentage, $5K Bid     | liquidity\_slippage\_5K\_bid\_percent   | Liquidity | Slippage    | Ratio | Dimensionless | 1h       |
| Liquidity Slippage Percentage, $10K Bid    | liquidity\_slippage\_10K\_bid\_percent  | Liquidity | Slippage    | Ratio | Dimensionless | 1h       |
| Liquidity Slippage Percentage, $50K Bid    | liquidity\_slippage\_50K\_bid\_percent  | Liquidity | Slippage    | Ratio | Dimensionless | 1h       |
| Liquidity Slippage Percentage, $100K Bid   | liquidity\_slippage\_100K\_bid\_percent | Liquidity | Slippage    | Ratio | Dimensionless | 1h       |
| Liquidity Slippage Percentage, $1M Bid     | liquidity\_slippage\_1M\_bid\_percent   | Liquidity | Slippage    | Ratio | Dimensionless | 1h       |

## Details

Price slippage is the difference, often represented as a percentage, between the quoted price of an asset and the execution price of a market order. There can be many causes for slippage, but the primary cause is the size of a trade with respect to the composition of the limit orderbook. The bid slippage metrics represent the price slippage of a sell order. And the ask slippage metrics represent the price slippage of a buy order.

Let’s say an investor wishes to purchase 1 BTC at the best ask price of $25,000 and they submit a market order. The top of the order book has a sell order at this price for 0.25 BTC, so .25 BTC is purchased at $25,000 per BTC. The next order in the orderbook is for 0.5 BTC, but at a price of $25,250. This is executed and 0.5 BTC is purchased at $25,250 per BTC. 0.75 BTC has now been purchased, and 0.25 BTC remain. The investor completes his order at the next offer in the orderbook, 0.5 BTC for $25,500. As only 0.25 BTC are needed to complete the 1 BTC purchase, the investor fills 0.25 BTC at the price of $25,500 per BTC. The effective execution price of this purchase is the average price of the individual orders, weighted by quantity:&#x20;

### &#x20;                          $$\frac{0.25\times\$25,000 + 0.5\times\$25,250 + 0.25\times\$25,500}{0.25 + 0.5 + 0.25} = \$25,250$$

The slippage is the percentage difference in the market price and this execution price:

&#x20;                                                        $$\frac{\$25,250-\$25,000}{\$25,000} = 1\%$$

So this hypothetical purchase of 1 BTC incurred 1% slippage. If the trade size was different, then the slippage would change; that is, slippage is dependent on order size.

## Examples

A sample of the liquidity slippage percentage for a $100K sell order on the `coinbase-btc-usd-spot` market is shown below:

```
{
  "data" : [ {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T20:00:00.000000000Z",
    "liquidity_slippage_100K_bid_percent" : "0.0302420889601772"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T21:00:00.000000000Z",
    "liquidity_slippage_100K_bid_percent" : "0.018658001599947585"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T22:00:00.000000000Z",
    "liquidity_slippage_100K_bid_percent" : "0.02975123391334869"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T23:00:00.000000000Z",
    "liquidity_slippage_100K_bid_percent" : "0.019856484825922595"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-05T00:00:00.000000000Z",
    "liquidity_slippage_100K_bid_percent" : "0.025194922755210136"
  } ]
}
```

* **`market`**: The id of the markets.\

* **`time`**: The time in ISO 8601 date-time format.\

* **`liquidity_slippage_100K_bid_percent`**: The percent slippage of a $100K sell order executed at this time in this market.&#x20;

## Release History

* **Release Version. Market Data Feed v2.8 on May 2023**.
