---
description: /timeseries/market-openinterest
---

# Market Open Interest

## **Definition**

Open interest represents the number of futures contracts that are currently outstanding and not settled. Each contract has a specified contract value that can be described by the size asset and contract size. 

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
      <td style="text-align:left">Market open interest</td>
      <td style="text-align:left">Market</td>
      <td style="text-align:left">Futures open interest</td>
      <td style="text-align:left">Market data</td>
      <td style="text-align:left">
        <p>Price: quote asset</p>
        <p>Size: Units of base asset</p>
      </td>
      <td style="text-align:left">1 min</td>
    </tr>
  </tbody>
</table>

## Details

* A derivatives market represents a venue where contracts of a financial derivative are bought and sold.  Instead of an exchange rate, the price of a derivative represents the price of one contract.  Each financial derivatives contract has unique contract specifications which describe how the contract is quoted and the amount of notional exposure that a contract represents.  
* A futures contract is a financial derivative traded on an exchange that allows a buyer and seller to enter into a legal agreement to buy or sell an underlying asset. The term futures contract refers to both traditional futures contracts, which specify a defined time when the futures contract expires, and perpetual futures which simulate a traditional futures contract with the exception that it never expires.
* Certain exchanges follow an integer contract size convention – buyers and sellers buy or sell a specified integer number of contracts and transacting in fractional contracts are not possible. However, some exchanges’s perpetual futures contracts do not follow the integer contract size convention. Instead, they allow traders to trade these futures contracts much like how spot markets trade. In- stead of buying and selling a specified integer number of contracts, traders can buy or sell a specified exposure in fractional units of the base asset. Therefore, certain exchanges report their open interest in fractional amounts. 
* Each contract has a specified contract value that can be described by the size asset and contract size.   For instance, one contract of BitMEX’s XBTUSD contract allows for notional exposure worth 1 USD. Other exchanges have their own contract specifications.

## **Example**

A sample of the futures open interest data from BitMEX is shown below. 

![Source: CM Market Data Feed](../.gitbook/assets/0%20%286%29.png)

* market:  The IDs of the market.  Market IDs use the following naming convention:  exchangeName-futuresSymbol-future for futures markets. 
* time: The time at which Coin Metrics queried the open interest data from an exchange in ISO 8601 date-time format.
* contract\_count:  The open interest denominated in number of contracts.
* value\_USD:  The open interest denominated in US dollars.
* database\_time:  The timestamp when the data was saved in the database in ISO 8601 date-time format with nanoseconds precision.
* exchange\_time:  The timestamp reported by the exchange.  Can be null if the exchange does not report a timestamp.

## Release History

* Release Version: MDF v2.2 \(December 7, 2020\) - initial version

## **Availability**

24 hours of futures open interest is available through our community API.  Community data is available via HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address. 

For a full list of assets, exchanges, and markets, please consult the Coin Metrics Data Coverage file or the ‘/catalog-all/markets’ via the API. 

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



