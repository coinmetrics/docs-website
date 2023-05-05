# Liquidity Depth Ask Volume (Units)

## Definition

Depth refers to the volume of orders submitted on either side of the book.

| Name                                           | MetricID                                            | Category  | Subcategory | Type | Unit         | Interval |
| ---------------------------------------------- | --------------------------------------------------- | --------- | ----------- | ---- | ------------ | -------- |
| Liquidity Depth 0.1 Percent Ask Volume (Units) | liquidity\_depth\_0\_1\_percent\_ask\_volume\_units | Liquidity | Depth       | Sum  | Native Units | 1h       |
| Liquidity Depth 1 Percent Ask Volume (Units)   | liquidity\_depth\_1\_percent\_ask\_volume\_units    | Liquidity | Depth       | Sum  | Native Units | 1h       |
| Liquidity Depth 2 Percent Ask Volume (Units)   | liquidity\_depth\_2\_percent\_ask\_volume\_units    | Liquidity | Depth       | Sum  | Native Units | 1h       |
| Liquidity Depth 5 Percent Ask Volume (Units)   | liquidity\_depth\_5\_percent\_ask\_volume\_units    | Liquidity | Depth       | Sum  | Native Units | 1h       |
| Liquidity Depth 10 Percent Ask Volume (Units)  | liquidity\_depth\_10\_percent\_ask\_volume\_units   | Liquidity | Depth       | Sum  | Native Units | 1h       |

## Details

Depth refers to the volume of orders submitted on either side of the book. While full orderbook depth is always of interest, this number can often be skewed by large buy/sell orders at price levels far away from the current trading price. An example of this is institutions placing large limit orders to buy BTC at deep support prices. A more relevant measure of depth, then, is the volume in the orderbook within a certain percentage of a reference price. This shows the quantity of orders surrounding an actionable price range.

For example, let’s say Bitcoin is currently trading at $25,000 on exchange X. Large institutions may fill the book with large orders to buy at $20,000 just in case bitcoin hits that level. But this obscures the active, interested trading at the current price level. So instead, we calculate the 2% Depth, or the depth of the orderbook within 2% of $25,000. This would be the total volume of buy side of the orderbook from the top down to $24,500, and the total volume of the sell side of the orderbook from the top up to $25,500.

## Examples

A sample of the 2 percent liquidity ask depth (Units) for the Coinbase BTC-USD spot market is shown below:

```
{
  "data" : [ {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T20:00:00.000000000Z",
    "liquidity_depth_2_percent_ask_volume_units" : "9866859.984315595"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T21:00:00.000000000Z",
    "liquidity_depth_2_percent_ask_volume_units" : "10170729.085314134"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T22:00:00.000000000Z",
    "liquidity_depth_2_percent_ask_volume_units" : "10909944.294472648"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-04T23:00:00.000000000Z",
    "liquidity_depth_2_percent_ask_volume_units" : "10983104.902848331"
  }, {
    "market" : "coinbase-btc-usd-spot",
    "time" : "2023-05-05T00:00:00.000000000Z",
    "liquidity_depth_2_percent_ask_volume_units" : "11103789.859471431"
  } ]
}
```

* **`market`**: The id of the markets.\

* **`time`**: The time in ISO 8601 date-time format.\

* **`liquidity_depth_2_percent_bid_volume_usd`**: The USD depth of orderbook asks within 2 percent of the mid price.

## Frequently Asked Questions

### How often are the metrics calculated?

The depth metrics are calculated once an hour.

## Release History

* **Release Version. Market Data Feed v2.8 on May 2023**.
