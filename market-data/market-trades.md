---
description: /timeseries/market-trades
---

# Market Trades

## **Definition**

A trade is the exchange of a financial asset between a buyer and seller from a market on a trading exchange.  In this context, a financial asset can be a cryptoasset, a fiat currency, or a cryptoasset derivatives contract. 

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
      <td style="text-align:left">Market trades</td>
      <td style="text-align:left">Market</td>
      <td style="text-align:left">Trade</td>
      <td style="text-align:left">Market data</td>
      <td style="text-align:left">
        <p>Amount: units of base asset</p>
        <p>Price: quote asset</p>
      </td>
      <td style="text-align:left">n/a</td>
    </tr>
  </tbody>
</table>

## **Details**

* Markets can be categorized in spots or derivatives markets.  Currently the market types available are ‘spot’ and ‘future’.
* A spot market represents a trading pair in which the buyer exchanges units of one asset in return for units of another asset in amounts specified by the market’s price or exchange rate.  By convention, the exchange rate consists of a base asset and a quote asset and represents the number of units of the quote asset needed to buy one unit of the base asset.  Cryptoassets and fiat currencies can serve as either base or quote assets, depending on the market.
* A derivatives market represents a venue where contracts of a financial derivative are bought and sold.  Instead of an exchange rate, the price of a derivative represents the price of one contract.  Each financial derivatives contract has unique contract specifications which describe how the contract is quoted and the amount of notional exposure that a contract represents.  

## **Example**

An sample of the trades data from Coinbase’s Bitcoin-US Dollar Spot Market is provided below:

![Source: CM Market Data Feed](../.gitbook/assets/0%20%285%29.png)

* market:  The IDs of the market.  Market IDs use the following naming convention:  exchangeName-baseAsset-quoteAsset-spot for spot markets and exchangeName-futuresSymbol-future for futures markets. 
* time:  The exchange-reported time in ISO 8601 date-time format.
* coin\_metrics\_id:   Identifier of a trade that is unique per exchange.  We use the exchange-reported value if exchange reports a numeric trade ID, otherwise we convert to numeric using bijective mapping from exchange-reported trade ID’s string.
* amount:  The amount of the base asset traded for spot markets or the number of contracts of a financial derivative.
* price:  The price of the base asset quoted in the quote asset that the trade was executed at for spot markets or the price of one contract for derivatives markets.
* database\_time:  The time that the trade was inserted into our database in ISO 8601 date-time format.
* side: The side that is taking liquidity.  A value of “buy” means that an ask was removed from the order book by an incoming buy order, while “sell” means that a bid was removed from the order book by an incoming sell order.

## **Release History**

* Release Version: CM MDF v1.0 \(April 2019\) - initial version
* Release Version: Updates to CM MDF v1.0 websocket \(July 30, 2019\) - minor changes to trades messages
* Release Version: CM MDF v2.0 \(Dec 9, 2019\) - trades data for futures instruments for BitMEX and Huobi, trades data for all spot pairs traded on Binance US
* Release Version: CM MDF v2.1 \(May 5, 2020\) - trades for spot markets from Kucoin and FTX, trades for futures markets from Deribit, OKex, Binance, FTX and BItfinex 

## **Availability**

Community and pro market availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history. 

For a full list of assets, exchanges, spot markets, and futures markets, please consult the Coin Metrics Data Coverage file or the ‘/catalog-all/markets’ endpoint via the API.

### Markets, Assets, Exchanges

{% embed url="https://docs.coinmetrics.io/info/markets/trades" %}

