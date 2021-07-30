---
description: /timeseries/market-liquidations
---

# Futures Liquidations

## **Definition**

Exchanges which offer futures markets utilize a risk management system that will attempt to liquidate a market participant’s position before the point at which the market participant begins to owe more than what is in his account. 

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Name</b>
      </th>
      <th style="text-align:left"><b>Category</b>
      </th>
      <th style="text-align:left"><b>Subcategory</b>
      </th>
      <th style="text-align:left"><b>Type</b>
      </th>
      <th style="text-align:left"><b>Unit</b>
      </th>
      <th style="text-align:left"><b>Interval</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Futures Liquidations</td>
      <td style="text-align:left">Market</td>
      <td style="text-align:left">Liquidations</td>
      <td style="text-align:left">Market Data</td>
      <td style="text-align:left">
        <p>Amount: units of base asset</p>
        <p>Price: price quote asset</p>
      </td>
      <td style="text-align:left">n/a</td>
    </tr>
  </tbody>
</table>

## **Details**

Futures contracts enable market participants to trade with leverage – that is, market participants are allowed to have a position with notional value greater than the amount of money they have in their account. This raises the possibility that market participants can lose more money than have in their account. To address this possibility, exchanges which offer futures products have a liquidation system that will attempt to close a market participant’s position before the point at which the market participant begins to owe more than what is in his account. A simplified example illustrates the process. Suppose a trader deposits $100 into an exchange and buys $10,000 worth of Bitcoin perpetual contracts resulting in a leverage of 100x. Also, suppose the current price of Bitcoin is $10,000. If the price declines to $9,900 \(the “bankruptcy price”\), the trader would be bankrupt. Therefore, the exchange sets the liquidation price for this trader’s position at $9,925 \(the “liquidation price”\). If the price declines to this liquidation price, the exchange will forcibly initiate a sell liquidation order to attempt to close the trader’s position.

### **Harmonization Discussion**

Our liquidation data harmonizes liquidation data across various exchanges. Here we discuss some differences in how various exchanges report their liquidations data.

* **Liquidation orders versus liquidation trades**: Some exchanges report “liquidations orders” in which they will report the creation of a liquidation order when a trader’s position initially enters liquidation. When a trader’s position enters liquidation, an exchange will typically enter a limit order at the price at which the trader will be bankruptcy price. The liquidation orders will show the amount of the position that is being liquidated and the liquidation price, but will not represent the matched trades that are executed as a result of the liquidation. Other exchanges will report “liquidation trades” which represent the actual matched trades as a result of a liquidation order but will not report liquidation orders. Some exchanges will report both liquidation orders and liquidation trades.
* **Aggregated liquidation trades versus individual liquidation trades**: For the exchanges that report liquidation trades, the exchange can report it in aggregated or individual format. Exchanges that report liquidation trades in aggregated format means that even if the liquidation involved several matched trades, the exchange will report it as one aggregated trade representing the sum of the amount liquidated and the average price of the liquidations. Other exchanges report liquidation trades in individual trade format such that one liquidation can be reported via multiple observations representing the multiple matched trades.
* **With original position data versus without original position data**: Some exchanges report data about the position that is liquidated such as the original quantity and the original price that the position was entered into while others do not.
* **With history versus without history**: Similar to trades data, certain exchanges allow us to query historical liquidation data while others do not.

To deal with the differences described above, here we harmonize the data in the following way:

* If an exchange reports both liquidation orders and liquidation trades, we store both types of observations and differentiate the two types with the type column.

## **Example**

![Source: CM Market Data Feed](../.gitbook/assets/0%20%289%29.png)

* market: The id of the market. Market ids use the following naming convention: exchangeName-baseAsset-quoteAsset-spot for spot markets and exchangeName-futuresSymbol-future for futures markets.
* time: The time at which Coin Metrics queried the open interest data from an exchange in ISO 8601 date-time format.
* coin\_metrics\_id: The id of a liquidation \(unique per exchange\). We are using exchange reported value if exchange reports a numeric liquidation id, otherwise we convert to numeric using Bijective mapping from exchange reported liquidation id’s string.
* amount: The amount of the base asset liquidated.
* price: The price of the base asset quoted in the quote asset that the liquidation was executed at.
* type: The liquidation type. “trade” means that liquidation was executed, “order” means that the order was placed for the liquidation at the timestamp of the data entry but it wasn’t necessarily executed yet.
* database\_time: The timestamp when the data was saved in the database in ISO 8601 date-time format with nanoseconds precision.
* side: The market order side. “buy” means that an ask was removed from the book by an incoming buy order, “sell” means that a bid was removed from the book by an incoming sell order.

## Release History

* Release Version: MDF v2.2 \(December 7, 2020\) - initial version

## **Availability**

### Markets

| Type | Number of Markets |
| :--- | :---: |
| Futures | 5645 |

### Exchanges

| Exchange | \# of Futures Markets | Start Date |
| :--- | :---: | :---: |
| Binance | 101 | 2019-09-08 |
| Bitfinex | 15 | 2019-07-03 |
| Bitflyer | 22 | 2020-07-27 |
| BitMEX | 226 | 2014-11-22 |
| Deribit | 54 | 2017-01-06 |
| FTX | 487 | 2019-03-05 |
| Huobi | 1236 | 2020-06-12 |
| Kraken | 29 | 2020-09-06 |
| OKEx | 778 | 2019-12-25 |



