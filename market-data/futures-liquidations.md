---
description: /timeseries/market-liquidations
---

# Market Liquidations

## **Definition**

Exchanges which offer futures markets utilize a risk management system that will attempt to close a user’s position before the point at which the user begins to owe more than what is in the user's account. The trade or order that closes the user's position is referred to as a liquidation. 

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
        <p><code>amount</code>: amount in units of number of contracts</p>
        <p><code>price</code>: price in units of the underlying quote asset</p>
      </td>
      <td style="text-align:left">n/a</td>
    </tr>
  </tbody>
</table>

## **Details**

Futures contracts enable market participants to trade with leverage – that is, market participants are allowed to have a position with notional value greater than the amount of money they have in their account. This raises the possibility that market participants can lose more money than have in their account. To address this possibility, exchanges which offer futures products have a liquidation system that will attempt to close a market participant’s position before the point at which the market participant begins to owe more than what is in their account. 

A simplified example illustrates the process. Suppose a trader deposits $100 into an exchange and buys $10,000 worth of Bitcoin perpetual contracts resulting in a leverage of 100x. Also, suppose the current price of Bitcoin is $10,000. If the price declines to $9,900 \(the “bankruptcy price”\), the trader would be bankrupt. Therefore, the exchange sets the liquidation price for this trader’s position at $9,925 \(the “liquidation price”\). If the price declines to this liquidation price, the exchange will forcibly initiate a sell liquidation order to attempt to close the trader’s position.

## **Harmonization Discussion**

Our liquidation data harmonizes liquidation data across various exchanges. Here we discuss some differences in how various exchanges report their liquidations data.

* **Liquidation orders versus liquidation trades**: Some exchanges report “liquidations orders” in which they will report the creation of a liquidation order when a trader’s position initially enters liquidation. When a trader’s position enters liquidation, an exchange will typically enter a limit order at the price at which the trader will be bankruptcy price. The liquidation orders will show the amount of the position that is being liquidated and the liquidation price, but will not represent the matched trades that are executed as a result of the liquidation. Other exchanges will report “liquidation trades” which represent the actual matched trades as a result of a liquidation order but will not report liquidation orders. Some exchanges will report both liquidation orders and liquidation trades. 
* **Aggregated liquidation trades versus individual liquidation trades**: For the exchanges that report liquidation trades, the exchange can report it in aggregated or individual format. Exchanges that report liquidation trades in aggregated format means that even if the liquidation involved several matched trades, the exchange will report it as one aggregated trade representing the sum of the amount liquidated and the average price of the liquidations. Other exchanges report liquidation trades in individual trade format such that one liquidation can be reported via multiple observations representing the multiple matched trades. 
* **Side of original position versus side of liquidation:** Most exchanges report the side of the liquidation order or trade that is used to close the user's position \(i.e. whether the liquidation was a buy or sell action to close the position\). Some exchanges instead report the side of the original position that is under liquidation \(i.e. whether the original position that is under liquidation was a long or short position\).  
* **With original position data versus without original position data**: Some exchanges report data about the position that is liquidated such as the original quantity and the original price that the position was entered into while others do not. 
* **With history versus without history**: Similar to trades data, certain exchanges allow us to query historical liquidation data while others do not.

We harmonize the data in the following way:

* If an exchange reports both liquidation orders and liquidation trades, we store both types of observations and differentiate the two types with the type column.  
* Bybit is the only exchange in our coverage universe that reports the side of the original position under liquidation. Every other exchange reports the side of the liquidation. We adopt the convention of reporting the side of the liquidation, and we map Bybit's data to this convention by inverting the side reported by Bybit. 

## **Known Data Issues** 

* **Liquidations data from Binance are missing from 2021-04-27 to 2021-05-11** **due to a breaking change that was made to the Binance API on April 27, 2021.**  
* **Our liquidations data from Binance for an approximately four month window is underreported due to a breaking change that was made to the Binance API on April 27, 2021.** Prior to this date, Binance had reported every single liquidation. Our liquidations table was using the “last filled quantity” \(and price\), which was appropriate when all liquidations were reported. However, the change they implemented rendered their API to only report the latest liquidation within the last 1,000ms. As a result, our scrapers logic no longer fully captures every liquidation. We implemented a change to our scrapers on 2021-08-31. Rather than using the “last filled quantity” \(and price\), we will be using the total quantity of the liquidated orders that happened in that 1000ms interval \(and the average price of that interval\). Unfortunately, all liquidations data that was captured between 2021-05-11 and 2021-08-31 will remain underreported and there is no way for us to recover the data, as Binance does not permit the collection of historical liquidations. However, all liquidations that occurred before 2021-04-27 are still accurate. 

## **Example**

![Source: CM Market Data Feed](../.gitbook/assets/0%20%289%29.png)

* `market`: The id of the market. Market ids use the following naming convention: `exchangeName-baseAsset-quoteAsset-spot` for spot markets, `exchangeName-futuresSymbol-future` for futures markets, and `exchangeName-optionsSymbol-option` for options markets.  
* `time`: The time at which Coin Metrics queried the open interest data from an exchange in ISO 8601 date-time format. 
* `coin_metrics_id`: The id of a liquidation \(unique per exchange\). We are using exchange reported value if exchange reports a numeric liquidation id, otherwise we convert to numeric using Bijective mapping from exchange reported liquidation id’s string. 
* `amount`: The amount that is liquidated in units of number of contracts. 
* `price`: The price of the underlying base asset quoted in the underlying quote asset that the liquidation trade was executed at or liquidation order was set at. 
* `type`: The liquidation type. `trade` means that the liquidation was executed. `order` means that the order was placed for the liquidation at the timestamp of the data entry but it wasn’t necessarily executed yet. 
* `database_time`: The timestamp when the data was saved in the database in ISO 8601 date-time format with nanoseconds precision. 
* `side`: The market order side. `buy` means that an ask was removed from the book by an incoming buy order, `sell` means that a bid was removed from the book by an incoming sell order. We report the side of the trade or order that was used to close the position under liquidation -- not the side of the original position. 

## Frequently Asked Questions 

**What does the liquidation side represent?** 

We report the side of the trade or order that was used to close the position under liquidation -- not the side of the original position. ****For example, if a trader had a long position and the price suddenly declined that caused the trader's position to be liquidated, the result would be a liquidation with a side of `sell`.   

## Release History

* Release Version: MDF v2.2 \(December 7, 2020\) - initial version

## **Availability**

The previous 24 hours of liquidations data is available through our Community API.  Community data is available via HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address. All of our liquidations data is available through our professional API with higher rate limits.  

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



