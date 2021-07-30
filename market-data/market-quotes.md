---
description: /timeseries/market-quotes
---

# Market Quotes

## **Definition**

Quotes consist of the best bid and the best ask for a market at a given point in time. The best bid represents the highest price that a buyer is willing to pay for one unit of the base asset for a spot market or one contract for a derivatives market. The best ask represents the lowest price that a seller is willing to sell. 

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
      <td style="text-align:left">Market quotes</td>
      <td style="text-align:left">Market</td>
      <td style="text-align:left">Quotes</td>
      <td style="text-align:left">Market data</td>
      <td style="text-align:left">
        <p>Price: quote asset</p>
        <p>Size: Units of base asset</p>
      </td>
      <td style="text-align:left">~ every 10 seconds</td>
    </tr>
  </tbody>
</table>

## Details

* Markets can be categorized in spots or derivatives markets.  Currently the market types available are ‘spot’ and ‘future’.
* A spot market represents a trading pair in which the buyer exchanges units of one asset in return for units of another asset in amounts specified by the market’s price or exchange rate.  By convention, the exchange rate consists of a base asset and a quote asset and represents the number of units of the quote asset needed to buy one unit of the base asset.  Cryptoassets and fiat currencies can serve as either base or quote assets, depending on the market.
* A derivatives market represents a venue where contracts of a financial derivative are bought and sold.  Instead of an exchange rate, the price of a derivative represents the price of one contract.  Each financial derivatives contract has unique contract specifications which describe how the contract is quoted and the amount of notional exposure that a contract represents.  

## **Example**

An sample of the quotes data from Coinbase’s Bitcoin-US Dollar Spot Market is provided below:

![Source: CM Market Data Feed](../.gitbook/assets/0%20%283%29.png)

* market:  The IDs of the market.  Market IDs use the following naming convention:  exchangeName-baseAsset-quoteAsset-spot for spot markets and exchangeName-futuresSymbol-future for futures markets. 
* time:  The exchange-reported time in ISO 8601 date-time format.
* coin\_metrics\_id:   Unique identifier of the quotes snapshot.
* ask\_price:  The limit price of the top ask on the order book.
* ask\_size: The size of the top ask on the order book in units of the base asset for a spot market or number of contracts for a derivatives market.
* bid\_price:  The limit price of the top bid on the order book .
* bid\_size: The size of the top bid on the order book in units of the base asset for a spot market or number of contracts for a derivatives market.

## **Release History**

* Release Version: CM MDF v1.0 \(April 2019\) - initial version
* Release Version: Updates to CM MDF v1.0 websocket \(July 30, 2019\) - faster quotes endpoint, minor changes for quotes
* Release Version: CM MDF v2.0 \(Dec 9, 2019\) - quotes for cex.io-btc-usd, bitflyer-btc-spot

## **Availability**

Community and pro market availability does not differ.  Community is available via HTTP API only, is limited to 1,000 API requests per 10 minutes per IP address and only showcases the last 24 hours of history. 

For a full list of assets, exchanges, spot markets, and futures markets, please consult the Coin Metrics Data Coverage file or the ‘/catalog-all/markets’ via the API.

Coin Metrics stores historical quotes snapshots approximately every 10-seconds. 

### Markets

| Market | Type | Base | Quote | Start Date |
| :--- | :---: | :---: | :---: | :---: |
| binance.us-btc-usd-spot | spot | btc | usd | 2020-01-27 |
| bitfinex-btc-usd-spot | spot | btc | usd | 2019-03-25 |
| bitfinex-eth-usd-spot | spot | eth | usd | 2019-03-25 |
| bitfinex-nexo-usd-spot | spot | nexo | usd | 2021-07-17 |
| bitflyer-btc-usd-spot | spot | btc | usd | 2019-12-06 |
| bitstamp-btc-usd-spot | spot | btc | usd | 2019-03-25 |
| bitstmap-eth-usd-spot | spot | eth | usd | 2019-03-25 |
| bittrex-btc-usd-spot | spot | btc | usd | 2019-03-25 |
| bittrex-eth-usd-spot | spot | eth | usd | 2019-03-25 |
| cex.io-btc-usd-spot | spot | btc | usd | 2019-12-06 |
| coinbase-btc-usd-spot | spot | btc | usd | 2019-03-25 |
| coinbase-eth-usd-spot | spot | eth | usd | 2019-03-25 |
| coinbase-aave-usd-spot | spot | aave | usd | 2021-07-17 |
| coinbase-atom-usd-spot | spot | atom | usd | 2021-07-17 |
| coinbase-bal-usd-spot | spot | bal | usd | 2021-07-17 |
| coinbase-bnt-usd-spot | spot | bnt | usd | 2021-07-17 |
| coinbase-mkr-usd-spot | spot | mkr | usd | 2021-07-17 |
| coinbase-snx-usd-spot | spot | snx | usd | 2021-07-17 |
| coinbase-sushi-usd-spot | spot | sushi | usd | 2021-07-17 |
| coinbase-uma-usd-spot | spot | uma | usd | 2021-07-17 |
| coinbase-uni-usd-spot | spot | uni | usd | 2021-07-17 |
| coinbase-yfi-usd-spot | spot | yfi | usd | 2021-07-17 |
| coinbase-zrx-usd-spot | spot | zrx | usd | 2021-07-17 |
| coinbase-comp-usd-spot | spot | comp | usd | 2021-07-17 |
| coinbase-dash-usd-spot | spot | dash | usd | 2021-07-17 |

### Exchanges

| Exchange | \# of Spot Markets | Start Date | \# of Futures Markets | Start Date |
| :--- | :---: | :---: | :---: | :--- |
| Binance.US | 1 | 2020-01-27 |  |  |
| Binfinex | 3 | 2019-03-25 |  |  |
| Bitflyer | 1 | 2019-12-06 |  |  |
| Bitstamp | 2 | 2019-03-25 |  |  |
| Bittrex | 2 | 2019-03-25 |  |  |
| CEX.IO | 1 | 2019-12-06 |  |  |
| Coinbase | 15 | 2019-03-25 |  |  |
| Gemini | 2 | 2019-03-25 |  |  |
| itBit | 2 | 2019-03-25 |  |  |
| Kraken | 2 | 2019-03-25 |  |  |
| Liquid | 2 | 2019-03-25 |  |  |



