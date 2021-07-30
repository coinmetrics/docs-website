---
description: /timeseries/market-candles
---

# Market Candles

## **Definition**

Candles consist of summary statistics that describe the trading activity of a market over an interval of time. Coin Metrics engineers six statistics based on trades data that occurred over an interval of time: opening price, high price, low price, close price, volume-weighted average price, and total volume. 

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
      <td style="text-align:left">Market candles</td>
      <td style="text-align:left">Market</td>
      <td style="text-align:left">Candles</td>
      <td style="text-align:left">Market data</td>
      <td style="text-align:left">
        <p>Price/VWAP: quote asset</p>
        <p>Volume: units of base asset</p>
      </td>
      <td style="text-align:left">5 minutes, 10 minutes, 15 minutes, 30 minutes, 1 hour, 4 hours, 1 day</td>
    </tr>
  </tbody>
</table>

## **Details**

* Markets can be categorized in spots or derivatives markets.  Currently the market types available are ‘spot’ and ‘future’.
* A spot market represents a trading pair in which the buyer exchanges units of one asset in return for units of another asset in amounts specified by the market’s price or exchange rate.  By convention, the exchange rate consists of a base asset and a quote asset and represents the number of units of the quote asset needed to buy one unit of the base asset.  Cryptoassets and fiat currencies can serve as either base or quote assets, depending on the market.
* A derivatives market represents a venue where contracts of a financial derivative are bought and sold.  Instead of an exchange rate, the price of a derivative represents the price of one contract.  Each financial derivatives contract has unique contract specifications which describe how the contract is quoted and the amount of notional exposure that a contract represents.  
* Candles are generated at regular time intervals and at a time granularity that is suitable for charting and analysis. For instance, several technical analysis indicators can be calculated using data in candles format. 
* The volume-weighted average price \(VWAP\) is the average price of an asset over an interval weighted by volume. 

## **Example**

An sample of the candles data from Coinbase’s Bitcoin-US Dollar Spot Market is provided below:

![Source: CM Market Data Feed](../.gitbook/assets/0%20%288%29.png)

* market:  The IDs of the market.  Market IDs use the following naming convention:  exchangeName-baseAsset-quoteAsset-spot for spot markets and exchangeName-futuresSymbol-future for futures markets. 
* time:  The exchange-reported time in ISO 8601 date-time format.
* price\_open:   The opening price of the candle.
* price\_high:  The high price of the candle.
* price\_low:  The low price of the candle.
* price\_close: The close price of the candle.
* vwap:  The volume-weighted average price of the candle.
* volume: The volume of the candle in units of the base asset.

## **Release History**

* Release Version: CM MDF v1.0 \(April 2019\) - initial version
* Release Version: CM MDF v2.0 \(Dec 9, 2019\) - candles for futures instruments for BitMEX and Huobi, candles for all spot pairs traded on Binance US
* Release Version: CM MDF v2.1 \(May 5, 2020\) - candles for spot markets from Kucoin and FTX, trades for futures markets from Deribit, OKex, Binance, FTX and BItfinex 

## **Availability**

Community and pro _market_ availability does not differ.  However, only daily candles are available for the community.  Community data is available via the HTTP API only and is limited to 1,000 API requests per 10 minutes per IP address.

For a full list of assets, exchanges, spot markets, and futures markets, please consult the Coin Metrics Data Coverage file or the ‘/catalog-all/markets’ via the API.

### Markets, Assets, Exchanges

{% embed url="https://docs.coinmetrics.io/info/markets/trades" %}

