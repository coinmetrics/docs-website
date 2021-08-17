# Market Data FAQs

#### **What is the latency of your Real-Time Market Data Trades?**

Latency varies depending on the exchange, but we are confident that we capture more than 95% of trades after 0.3 seconds or so, and 99% of trades after 0.4 seconds. 

#### **In perpetual futures/swaps, is the margin\_asset the asset of settlement?** 

Yes, the margin\_asset is the asset of settlement. A trader must post this asset as the initial margin when opening a position**.** Unrealized gains and losses are calculated in this asset, and a trader receives gains or losses denominated in this asset when the trader closes the position or the contract expires. 

#### **In the liquidations data schema, how should I interpret the output “side”, and how is it different from the “side” in the trades data schema?**

The interpretation of the liquidation side is the side of the trade that liquidates the trader's position. For instance, if a trader is long a futures contract and the price declines such that the value of his position falls below the trader's maintenance margin, the exchange would execute a liquidation sell order to close the traders' position. So in liquidations, “side” is the side of the trade that liquidates the trader’s position.  And in trades, “side” is the side of the trade that removes an ask or a bid from the book.

#### **Is there a way to pull data for all markets of an exchange by just including the exchange name in the API query \(e.g., “exchange=Coinbase”\)?**  

You must query each market \(e.g., ‘markets=coinbase-btc-usd-spot’\) and aggregate the markets by exchange.  We do not currently support a call for all markets for an exchange.  

One workaround for efficiently pulling this data is by using the "exchange" parameter in our market catalogue endpoint. Here's a raw python example that would pull the markets from Coinbase:

```python
response = requests.get(
    'https://api.coinmetrics.io/v4/catalog/markets',
    params={'api_key': api_key,
           'exchange':'coinbase'},
)
```

This method will work via the API and you can use it in any language. The general outline of the process is:

1. Get a list of all desired markets from `v4/catalog/markets`
2. if more than 90 markets, break the list into chunks of 90 markets
3. Call the API endpoint for each chunk of markets
4. Combine the results for analysis

#### **Is there a way to pull data for trading volume across a specific exchange or asset?**

Yes, there is a way to query and calculate this via our API. With your API key you can pull candles data for all the markets listed on an exchange from our timeseries/market-candles endpoint.  Then you sum the volume by exchange. Here is a sample query that will pull candles from the coinbase-btc-usd-spot market: 

https://api.coinmetrics.io/v4/timeseries/market-candles?start\_time=2020-01-01&paging\_from=start&markets=coinbase-btc-usd-spot&pretty=true&api\_key=\[INSERT YOUR API KEY HERE\]

You can add all of the volumes across pair/exchange to come to a total trading volume across an asset/exchange. 

#### Is there a way to filter out just BTC-USD futures markets for analysis?

We use exchange-reported futures contract names, and unfortunately the exchanges haven't converged on any sort of standardized naming convention. For instance, BitMEX's BTC-USD perpetual contract is called XBTUSD.  To determine which futures contracts use BTC-USD as the underlying, you can take a look at our contract specifications from the /catalog/markets endpoint and keep markets that have type=future, base=btc, and quote=usd. You might also want to consider keeping markets with quote=usdt too since the futures based on BTC-USDT underlying are quite actively traded as well.   

#### **Why are there so many funding rate values of 0, particularly with Bitfinex?**

Bitfinex funding rate does allow for 0% funding rates or no funding payments. For their BTCF0-USTF0 contract, there are many periods of zero funding rate: [https://trading.bitfinex.com/t/BTCF0:USTF0/details](https://trading.bitfinex.com/t/BTCF0:USTF0/details)

Table 1 shows, for example, that for the Perpetual Contract on BTCF0:USTF0, an obligation to make a Funding Payment arises whenever the Average Spread is greater than 0.05% or less than -0.05%. When the Average Spread over the Funding Period is equal to or within -0.05% and 0.05%, a Funding Payment will not be required: [https://www.bitfinex.com/legal/derivative/funding](https://www.bitfinex.com/legal/derivative/funding) 

#### What are the exchanges that serve as constituents for your Trusted Volume metric? 

Our trusted volume metric is an aggregation of the reported volume from exchanges that we consider the most accurate and trustworthy.  The full list of constituent exchanges included in our Trusted Volume is [here](https://docs.coinmetrics.io/asset-metrics/volume/volume_trusted_spot_usd_1d). 

#### What determines the frequency/intervals of funding rates data?

Our funding rates data updates based on the funding interval. 

#### What determines the frequency/intervals of liquidations data?

There is no set time frequency for liquidations, since these are event-based just like trades. Whenever an exchange liquidates a traders position, that data is pulled in real time. In theory, if the market is trading flat and not moving much in either direction, you won't see many liquidations, whereas if there is high volatility you'll see a higher frequency stream of liquidations.

#### Why is there no way to set specific frequencies/intervals for open interest data?  

Nearly all exchanges only allow users to query the current open interest. So at the individual market level, our scrapers collect open interest snapshots at a high frequency -- roughly once every 1m, but it depends on network traffic and when it cycles. Currently no exchanges allow us to get open interest as a time-series with regularly spaced observations through time. 

#### What is the 'coin\_metrics\_id' when pulling trades or liquidations data, and what is its purpose?

'coin\_metrics\_id' is an identifier for an event that is unique per exchange. If an observation has a unique coin\_metrics\_id that means that the exchange reported it as a unique observation. For more background, our market data collection system is designed to use multiple instances of each scraper for redundancy purposes. Although we run multiple instances of each scraper, we deduplicate observations using a composite primary key. For trades and liquidations data, the primary key consists of exchange, futures symbol, and trade id. This ensures that each observation that we insert into our database is unique.

Exchanges serve each trades and liquidations observations with a unique identifier, typically labeled as trade id or uid. If an exchange’s unique identifier is an integer, we store the integer as is. If an exchange’s unique identifier is a base 16 encoded string, we convert the string to an integer and store that value. In general, if an exchange’s unique identifier is a string, we convert it to an integer using a bijective mapping function.

As such, when storing/ingesting our trades and liquidations data, we recommend adding the 'coin\_metrics\_id 'field to the table's composite primary key to ensure that you are not storing any duplicates. The coin\_metrics\_id is also useful when the exchange reports it as an incremental integer -- an integer that increments by 1 for every trade. Most exchanges will start this id at 1, so you can see how many trades have occurred in its lifetime. Also, it is useful for sequencing trades and determining whether all trades have been collected. Coinbase and Binance are two exchanges that report their trade ids in this format.

 **How does Coin Metrics ensure high levels of data quality and data integrity?**  
  
Coin Metrics utilizes a multifaceted approach to ensure high levels of data quality and data integrity. We carefully curate our exchange coverage universe, employ a market data collection system with high levels of redundancy and resiliency, use a robust system of logging and monitoring that alerts staff members in real-time to any anomalies, and our software releases are governed by a series of SOC 2-compliant policies that include extensive testing prior to release. For certain critical data types, such as our reference rates, we also employ regular human review to screen for data quality issues. Each of these facets is described in more detail below.

* **Exchange coverage universe**: While there are over 400 digital asset exchanges in existence, Coin Metrics has curated our exchange coverage universe to include only high quality exchanges with legitimate trading activity. The presence of fake volume and wash trading is widely acknowledged in the industry, and Coin Metrics has independently confirmed the findings of several prominent researchers who have studied this problem. When deciding whether to include an exchange in our coverage universe, we consult a series of qualitative and quantitative features that are described in our [Market Selection Framework](https://coinmetrics.io/reference-rates-market-selection-framework/) and our [Trusted Volume Framework](https://coinmetrics.io/introducing-coin-metrics-trusted-volume-framework/). We also consult feedback from our institutional user base. The exchanges in our coverage universe are widely recognized by market participants and researchers who have studied the fake volume problem to be of high quality. 
* **Market data collection system**: Our market data collection system is engineered to have high levels of redundancy and resiliency. We collect data from exchanges using two instances of each application each located in an independent data center. For certain data types, we collect data from an exchange's HTTP endpoint and websocket endpoint simultaneously as an added redundancy measure. Our market data collection system utilizes a fleet of proxy servers to circumvent rate limits imposed by the exchange. Each server that hosts our market data collection system has local database storage as a fault tolerant measure in case of a failure in our primary database. These measures ensure high levels of availability for our market data collection applications and that no observations are missed.   
* **Monitoring and logging**: A dedicated team of engineers monitor logs and telemetry from our servers, databases, and applications in real-time using a suite of dashboards and automated alerts. We also have dedicated monitoring to detect interruptions of service from an exchange. 
* **Deployment process**: Our deployment process is governed by a series of SOC 2-compliant policies that include code reviews, extensive testing, manual review and quality control of historical values, and approvals prior to release. We received our SOC 2 Type 1 certification from Deloitte in August 2021 in the areas of security, availability, and processing integrity.  
* **Human review**: For certain critical data types, we employ regular human review to detect anomalies and assess the quality of our data. For instance, our reference rates are reviewed by a dedicated staff member every day, 365 times a year, at 16:00 New York time. Our reference rates are checked for several issues, including timeliness, data anomalies, sufficient data inputs, and a comparison against external sources. 



