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

| market                | time                | liquidity\_depth\_2\_percent\_ask\_volume\_units |
| --------------------- | ------------------- | ------------------------------------------------ |
| coinbase-btc-usd-spot | 2023-01-01 00:00:00 | 17803089.955932498                               |
| coinbase-btc-usd-spot | 2023-01-01 01:00:00 | 16413608.359291492                               |
| coinbase-btc-usd-spot | 2023-01-01 02:00:00 | 13519972.010365777                               |
| coinbase-btc-usd-spot | 2023-01-01 03:00:00 | 13513309.854183163                               |

* market. The IDs of the markets.
* time. The time in ISO 8601 date-time format.
* liquidity\_depth\_2\_percent\_bid\_volume\_usd. The USD depth of orderbook asks within 2 percent of the mid price.

## Release History

* Release Version. Market Data Feed (January 2023)