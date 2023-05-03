---
description: /timeseries-stream/pair-quotes
---

# Pair Quotes

## Definition

Coin Metrics collects quotes representing the best bid order and best ask order residing at the top of the order book for individual markets like `coinbase-btc-usd-spot`. To calculate our pair quotes, we aggregate the quotes across a selection of high-quality constituent markets to derive quotes for a pair like `btc-usd`.&#x20;

Our pair quotes are conceptually similar to the National Best Bid Offer (NBBO), a regulation issued by the United States Securities and Exchange Commission that requires brokers to execute customer trades at the best available price.

## Details

Our `/timeseries-stream/pair-quotes` endpoint supports multiple aggregation methods to aggregate the quotes data from individual constituent markets for a given pair. The different aggregation methods can be specified using the `aggregation_method` parameter.&#x20;

Currently, only the `aggregated_spread` method is implemented, and alternative methods will be implemented in the future.

### Aggregated Spread

The `aggregated_spread` method uses the following methodology:

For a given pair, select major spot markets where the market contains the given pair. For each market i, calculate the bid ask spread in percentage terms and the midprice:

$$
MidpointPrice_i = \frac{BestAskPrice_i + BestBidPrice_i}{2}
$$

$$
Spread_i = \frac{BestAskPrice_i - BestBidPrice_i}{MidpointPrice_i}
$$

Calculate the weighted-average bid-ask spread and weighted-average midprice where the weight is determined by Volume\_i, the cumulative volume over some time period \[t-1, t] on market i. The advantage of using a trailing volume as opposed to other volume measures, such as order size at the top of the book, is that volume indicates the real contribution of a given exchange to the market. Using order sizes from the book would allow for the random behavior of market participants to bias the aggregate in a way that does not represent the actual contribution of an exchange to the broader crypto market. Using these weights will measure the trading activity actually realized on a market at a given spread. In this way, the volume-weighted spread (as opposed to size-weighted spread) will indicate the spread that is realized via real volume for a given asset or asset-pair.

$$
AvgMidpointPrice = \frac{\sum_{i=1}^{n} Volume_i \times MidpointPrice_i}{\sum_{i=1}^{n} Volume_i}
$$

$$
AvgSpread = \frac{\sum_{i=1}^{n} Volume_i \times Spread_i}{\sum_{i=1}^{n} Volume_i}
$$

Using weighted-average midprice and weighted-average spread, calculate the aggregated bid and aggregated ask. The aggregated bid amount and aggregated ask amount are the sum of bid amounts and ask amounts from major markets, respectively.

$$
AggBidPrice = AvgMidpointPrice - 0.5 \times AvgSpread \times AvgMidpointPrice
$$

$$
AggAskPrice = AvgMidpointPrice + 0.5 \times AvgSpread \times AvgMidpointPrice
$$

$$
AggBidAmount = \sum_{i=1}^{n} BestBidAmount_i
$$

$$
AggAskAmount = \sum_{i=1}^{n} BestAskAmount_i
$$

## Example

```
{
  "time": "2020-06-08T21:15:45.771742000Z",
  "pair": "btc",
  "ask_price": "24343.725954328216",
  "ask_size": "2.96375165",
  "bid_price": "24342.036360171896",
  "bid_size": "12.00588437",
  "mid_price": "24342.881157250056",
  "spread": "0.0000694081421754166",
  "cm_sequence_id": "0"
}
```

* **`time`**:  The exchange-reported time in ISO 8601 date-time format. Always with nanoseconds precision.\

* **`pair`**: The id of the pair.\

* **`ask_price`**: The price of the ask order in units of the quote currency as determined by the aggregation method.\

* **`ask_size`**: The size of the ask order in units of the base asset as determined by the aggregation method.\

* **`bid_price`**: The price of the bid order in units of the quote currency as determined by the aggregation method.\

* **`bid_size`**: The size of the bid order in units of the base asset as determined by the aggregation method.\

* **`mid_price`**: The average of the **`ask_price`** and **`bid_price`**.\

* **`spread`**: The bid-ask spread in raw units.\

* **`cm_sequence_id`**: The sequence id number of the websocket message.

## Frequently Asked Questions

### What are the constituent markets used in the calculation?

Coin Metrics uses our [Trusted Exchange Framework v2.0](https://coinmetrics.io/special-insights/trusted-exchange-framework/) to seelct a set of high-quality and trustworthy exchanges in selection of our constituent markets. The set of exchanges includes `Bitstamp`, `Coinbase`, `Bitfinex`, `Binance`, `Gemini`, `Kraken`, `OKEx`, `Huobi`, `Binance.US`, `KuCoin`, `LMAX`, and `Bybit`.&#x20;

All markets from trusted exchanges that contain the given pair are selected.

### **How often is the data updated?**

Our websocket API will send a new message once every 250 milliseconds.

## Release History

* **CM Market Data Feed v2.8 on May 2023**.

## Availability

The asset quotes are currently available for the following assets: `btc`, `eth`, `ltc`, `xrp`, `bnb`, `usdt`, `trx` `link`, `doge`, `usdc`, `ada`, `atom`, `matic`, `dai`, `sol`, `dot`, `avax`, `uni`.
