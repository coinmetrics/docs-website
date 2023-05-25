# Market Data FAQs

### **Can you explain your historical data coverage?**&#x20;

When we collect data from a new exchange, our general approach is to always collect the maximum history possible for every single instrument. The available history depends on the specific exchange and data type. For a given data type, some exchanges allow us to get the complete history, some exchanges allow us to get a short window of history, and some exchanges do not allow us to get any history.&#x20;

Our trades history for Bitcoin begins when it began trading on Mt.Gox in July 2010, so we have over 10 years of trades history. We also have full historical trades data from several other early exchanges such as Bitstamp, TheRockTrading, Bitfinex, and Kraken.&#x20;

Please take a look at our [Market Data Exchange Coverage](https://docs.coinmetrics.io/exchanges/all-exchanges) or the availability sections of each of our market data pages for more information on the history available for each exchange-data type combination.&#x20;

### **How does Coin Metrics ensure high levels of data quality and data integrity?**

Coin Metrics utilizes a multifaceted approach to ensure high levels of data quality and data integrity. We carefully curate our exchange coverage universe, employ a market data collection system with high levels of redundancy and resiliency, use a robust system of logging and monitoring that alerts staff members in real-time to any anomalies, and our software releases are governed by a series of SOC 2-compliant policies that include extensive testing prior to release. For certain critical data types, such as our reference rates, we also employ regular human review to screen for data quality issues. Each of these facets is described in more detail below.

* **Exchange coverage universe**: While there are over 400 digital asset exchanges in existence, Coin Metrics has curated our exchange coverage universe to include only high quality exchanges with legitimate trading activity. The presence of fake volume and wash trading is widely acknowledged in the industry, and Coin Metrics has independently confirmed the findings of several prominent researchers who have studied this problem. When deciding whether to include an exchange in our coverage universe, we consult a series of qualitative and quantitative features that are described in our [Market Selection Framework](methodologies/coin-metrics-prices-methodology.md#data-inputs) and our [Trusted Volume Framework](https://coinmetrics.io/special-insights/trusted-exchange-framework/). We also consult feedback from our institutional user base. The exchanges in our coverage universe are widely recognized by market participants and researchers who have studied the fake volume problem to be of high quality.\

* **Market data collection system**: Our market data collection system is engineered to have high levels of redundancy and resiliency. We collect data from exchanges using two instances of each application each located in an independent data center. For certain data types, we collect data from an exchange's HTTP endpoint and websocket endpoint simultaneously as an added redundancy measure. CM utilizes multiple proxy servers to ensure that rate limits imposed by some exchanges do not impact data collection. Each server that hosts our market data collection system has local database storage as a fault tolerant measure in case of a failure in our primary database. These measures ensure high levels of availability for our market data collection applications and that no observations are missed.\

* **Multiple data centers**: Coin Metrics utilizes two geographically-separated and vendor-independent data centers. Each data center contains an independent and complete collection of the infrastructure and applications needed to collect, process, and serve our data. In the case of failure of one of the data centers, our API will automatically failover to use our secondary data center with no action needed to be taken by our users.\

* **Internal monitoring**: A dedicated internal team of data quality and site reliability engineers monitor logs and telemetry from our servers, databases, and applications in real-time using a suite of dashboards and automated alerts. We also have dedicated monitoring to detect interruptions of service from an exchange, incidents reported by an exchange, or breaking changes to their API. This monitoring allows us to take swift corrective or mitigating action if necessary.\

* **External monitoring**: Coin Metrics maintains a dedicated external monitoring application that continuously polls our API endpoints to detect for interruptions in the data or unexpected responses from our API. This monitoring application allows us to continuously test the health of the entire pipeline of our systems from the perspective of our users. It is deployed in an external environment that is independent from our data centers so that it would not be affected in case of any degraded performance in our systems. Our internal team of data quality and site reliability engineers monitor the alerts generated by this application and take swift corrective or mitigating action if necessary.\

* **Deployment process**: Our deployment process is governed by a series of SOC 2-compliant policies that include code reviews, extensive testing, manual review and quality control of historical values, and approvals prior to release. We received our SOC 2 Type 1 certification from Deloitte in August 2021 in the areas of security, availability, and processing integrity.\

* **Human review**: For certain critical data types, we employ regular human review to detect anomalies and assess the quality of our data. For instance, our reference rates are reviewed by a dedicated staff member every day, 365 times a year, at 16:00 New York time. Our reference rates are checked for several issues, including timeliness, data anomalies, sufficient data inputs, and a comparison against external sources.

### **Is there a way to pull data for multiple markets (such as all the markets for a particular exchange) in one API call?**  &#x20;

Yes! All of our endpoints that accept the `markets` parameter will accept wildcards  like `exchange-*` or `exchange-*-spot` or `*USDT-future`. The wildcards will match any market which fits this pattern so users do not need to specify every individual market when querying data for multiple markets. The `markets` parameter will also accept a comma-separated string of individual markets.&#x20;

### **Is there a way to pull data for trading volume across a specific exchange or asset?**&#x20;

We have pre-calculated volume metrics that represent total volume by asset, by exchange, by pair, or by exchange-asset pair. Please take a look at the following volume metrics below.&#x20;

{% content-ref url="../asset-metrics/volume/" %}
[volume](../asset-metrics/volume/)
{% endcontent-ref %}

{% content-ref url="../exchange-metrics/volume/" %}
[volume](../exchange-metrics/volume/)
{% endcontent-ref %}

{% content-ref url="../exchange-asset-metrics/volume.md" %}
[volume.md](../exchange-asset-metrics/volume.md)
{% endcontent-ref %}

{% content-ref url="../pair-metrics/pair-volume/" %}
[pair-volume](../pair-metrics/pair-volume/)
{% endcontent-ref %}

### **What metric naming conventions does Coin Metrics use?**

In general, we use snake case (ex: snake\_case) when naming our metrics in which each space is placed by an underscore (\_) character, and the first letter of each word is written in lowercase.&#x20;

The order of terms is ordered from the most general to most specific and ends with the unit used, if applicable. For example, the order of terms in the metric `volume_reported_future_perpetual_usd_1d` is ordered such that the `volume` term is first and all subsequent terms are modifiers to what type of volume the metric represents.&#x20;

Some metrics are naturally represented as an aggregation (such as a sum or mean) over a time interval (such as a block, an hour, or day). If the metric represents an aggregation over a time interval, the interval is appended as a suffix to the metric name. If the metric represents a value at a point in time, there is no suffix. Please see the frequently asked question ["What timestamp conventions does Coin Metrics use?"](https://docs.coinmetrics.io/market-data/market-data-faqs#what-timestamp-conventions-does-coin-metrics-use).

The exception to this convention is that all Network Data Pro metrics use upper camel case (ex: CamelCase) in which names omit spaces and the separation of words is indicated by a single capitalized letter. The first word is also capitalized. Network Data Pro metrics used the upper camel case naming convention prior to our adoption of the snake case naming convention for all other metrics, so we maintain the upper camel case naming convention for Network Data Pro metrics for consistency and backwards compatibility.

### **What timestamp conventions does Coin Metrics use?**&#x20;

We use two timestamp conventions for our data types: point-in-time and beginning-of-interval.

For any data type where the value represents a measurement at a point in time, we set the timestamp to that specific point in time. This is referred to as the “point-in-time” timestamp convention. We use this timestamp convention for any data type that represents a discrete event (such as a trade or order book update) or any data type that represents the snapshot of the state of something (such as an open interest snapshot or order book snapshot). For instance, if the `time` for a trade is `2021-08-04 23:56:00.356749000`, that means that the trade was executed exactly at that timestamp.

For any data type that represents a summary statistic over an interval of time, we set the timestamp to the beginning of the time interval. This is referred to as the "beginning-of-interval" timestamp convention. Summary statistics can include transformations such as sum, mean, median, and count. Our candles is an example of a data type that follows this convention because it represents the open, high, low, close, and volume over an interval of time such as a day. For instance, if the `time` for a daily candle is `2021-08-04 00:00:00.000000000`, that means the candle represents the daily interval from `2021-08-04 00:00:00.000000000` to `2021-08-04 23:59:59.999999999`, inclusive. Here we represent `00:00:00.000000000` as the beginning of the day according to the [ISO 8601 standard](https://en.wikipedia.org/wiki/ISO\_8601).

The following API endpoints serve data using the point-in-time convention:

* `/timeseries/market-trades`
* `/timeseries/market-openinterest`
* `/timeseries/market-liquidations`
* `/timeseries/market-funding-rates`
* `/timeseries/market-orderbooks`
* `/timeseries/market-quotes`
* `/timeseries/market-contract-prices`
* `/timeseries/market-implied-volatility`
* `/timeseries/market-greeks`
* `/timeseries/index-levels`
* `/timeseries/index-constituents`
* Any metric in `/timeseries/asset-metrics`, `/timeseries/exchange-metrics`, `/timeseries/exchange-asset-metrics`, `/timeseries/pair-metrics`, `/timeseries/institution-metrics` , `/timeseries/market-metrics` with `snake_case` naming convention and without an interval suffix, such as `open_interest_reported_future_usd`

The following API endpoints serve data using the beginning-of-interval convention:

* `/timeseries/market-candles`
* Any metric in `/timeseries/asset-metrics` with upper camel case (ex: `UpperCamelCase`) naming convention
* Any metric in `/timeseries/asset-metrics`, `/timeseries/exchange-metrics`, `/timeseries/exchange-asset-metrics`, `/timeseries/pair-metrics`, `/timeseries/institution-metrics`, `/timeseries/market-metrics` with `snake_case` naming convention and with an interval suffix, such as `volume_reported_future_perpetual_usd_1d`

### What asset ticker naming conventions does Coin Metrics use?

Coin Metrics assigns a unique ticker symbol for each asset in our coverage universe using the following naming convention: `parentasset[_fullname][_network][_chain]`, where the `fullname`, `network`, and `chain` are optional. Market data and aggregated network data are assigned to the `parentasset` ticker, where aggregated network data consists of data from individual network or chain-specific forms of an asset.&#x20;

To understand our naming convention, we first introduce some important context surrounding the two primary considerations regarding unique ticker symbols.&#x20;

First, what is thought as a singular asset may actually exist in various forms across multiple layer one and layer two blockchains. From the perspective of the blockchain ledger, each form resides on a separate blockchain, and Coin Metrics collects and produces data for each form independently. To differentiate between the specific form, Coin Metrics appends the blockchain ticker as a suffix to the asset ticker. For example, Tether (`usdt`) exists on Tron, Ethereum, Solana, and several other blockchains. To track the network activity of each form, Coin Metrics uses `usdt_tron`, `usdt_eth`, and `usdt_sol` tickers, respectively.&#x20;

Centralized exchanges, however, do not typically differentiate between different forms of an asset. They will allow users to deposit several forms of an asset and credit users internally with a generic parent form of the asset. Trading then occurs using the generic form of the asset, and all market data collected by Coin Metrics is assigned to the parent ticker.&#x20;

Returning to the Tether example, a centralized exchange may allow a user to deposit the ERC-20 form of Tether, which resides on Ethereum, as well as the TRC-20 form of Tether, which resides on Tron. Regardless of which form a user deposits, the user is credited with a generic parent form of Tether which is traded on all markets on the centralized exchange. Therefore, market data such as trades are assigned to the parent asset `usdt`.

Coin Metrics also aggregates data from individual forms of an asset to the parent asset for certain metrics. Therefore, metrics under the parent asset `usdt` represent an aggregation across `usdt_tron`, `usdt_eth`, and the other individual forms of Tether.&#x20;

Second, some assets may share the same display ticker as another asset. To resolve these ticker conflicts, Coin Metrics ensures that each asset ticker in our coverage universe is unique by appending the full name of the asset as a suffix to the asset ticker. For example, both Starcoin and Starchain share the same display ticker of `stc`. Coin Metrics resolves this ticker conflict by assigning the tickers `stc_starcoin` and `stc_starchain`, respectively.&#x20;

### What market naming conventions does Coin Metrics use?

Coin Metrics refers to a market as a specific pair or instrument on a specific exchange.&#x20;

For spot markets, we use the `{exchange}-{base}-{quote}-spot` naming convention like `coinbase-btc-usd-spot`. The base and quote both use our harmonized asset tickers.

For futures markets, we use the `{exchange}-{symbol}-future` naming convention like `binance-BTCUSDT-future`. The symbol is the exchange-reported symbol.

For option markets, we also use the `{exchange}-{symbol}-option` naming convention like `deribit-BTC-15OCT21-60000-C-option`. The symbol is the exchange-reported symbol.

We use exchange-reported symbol for our derivative markets because of the difficulty in establishing a standard naming convention. Exchanges may list multiple different contracts that trade the same underlying but with different contract specifications. And exchanges may list exotic derivative contracts that do not conform to standard contracts. In general, exchanges are constantly experimenting with different contract specifications. To prevent any confusion in which contract we are referencing, we adopt the exchange-reported symbol. More metadata about our markets such as the contract specifications, price and amount precision, and fees can be found through our `/catalog/markets` endpoint.

For decentralized exchange liquidity pools, we use the the `{exchange}-{pool_config_id}-{base}-{quote}-spot` naming convention.

The `pool_config_id` is needed since for some decentralized exchanges like Uniswap v3, multiple pools can exist for a single base and quote asset pair with different pool configurations such as different fees. More metadata about our liquidity pools can also be found through our `/catalog/markets` endpoint.

The `pool_config_id` usually takes an integer value that represents the order in which a pool was created. For convenience, we also create a synthetic aggregated market where we set the `pool_config_id` to `agg` so that users can pull candles data that is aggregated across all pools.

### **Why does the candles closing price differ from the `ReferenceRate` metric or `PriceUSD` metric or an index value?**&#x20;

The difference is due to different timestamp conventions. Candles and `PriceUSD` use the beginning-of-interval timestamp convention while `ReferenceRate` and index values use the point-in-time timestamp convention.&#x20;

For more discussion on these timestamp conventions, please see the frequently asked question ["What timestamp conventions does Coin Metrics use?"](https://docs.coinmetrics.io/market-data/market-data-faqs#what-timestamp-conventions-does-coin-metrics-use).

### When a new asset or market is listed, how long does it take for the market to be present in our market data-related data types?

Generally, for many critical data types, Coin Metrics will support a new asset or market the moment that it is listed on an exchange. All of our derivatives-related data types are available immediately with no delay. There are some spot market-related data types which require some manual steps that often involve human review to ensure that we are mapping exchange-reported tickers to our tickers appropriately. For these data types, there will be a short delay between when the market is listed and when it is visible through our API.

Coin Metrics has the ability to make the short delay extremely short or to eliminate the delay entirely on a one-off basis for new assets or markets that are considered important. A more complete description of which data types are available immediately with no delay and which are available with a short delay follows below.

**Data types available immediately with no delay**:

* The presence of the market and its associated metadata served through **`/catalog/markets`** and **`/catalog-all/markets`**
* Trades served through **`/timeseries/market-trades`** and **`/timeseries-stream/market-trades`**
* Streaming order book served through **`/timeseries-stream/market-orderbooks`**
* Streaming quotes served through **`/timeseries-stream/market-quotes`**
* Futures candles served through **`/timeseries/market-candles`**
* Futures open interest served through **`/timeseries/market-openinterest`**
* Futures liquidations served through **`/timeseries/market-liquidations`**
* Futures Funding rates served through **`/timeseries/market-funding-rates`**
* Futures and options order book snapshots served through **`/timeseries/market-orderbooks`**
* Futures and options quote snapshots served through **`/timeseries/market-quotes`**
* Futures and options contract prices served through **`/timeseries/market-contract-prices`**
* Options implied volatility served through **`/timeseries/market-implied-volatility`**
* Options greeks through **`/timeseries/market-greeks`**

**Data types available with a short delay:**

* The presence of a new asset served through **`/catalog/assets`** and **`/catalog-all/assets`**.
* Spot order book snapshots served through **`/timeseries/market-orderbooks`**.
* Spot quote snapshots served through **`/timeseries/market-quotes`**.
* Spot candles served through **`/timeseries/market-candles`**.
* Reference Rates served through metric `ReferenceRate` served through **`/timeseries/asset-metrics`**.
* Market-data related metrics such as reported volume served through **`/timeseries/asset-metrics`**, **`/timeseries/pair-metrics`**, **`/timeseries/exchange-metrics`**, **`/timeseries/exchange-asset-metrics`**, and **`/timeseries/market-metrics`**.

### How do I interpret the value of your volume metrics like `volume_reported_spot_usd_1d`?

Coin Metrics calculates several volume metrics (and other metrics) at different levels of aggregation. Volume metrics are available at the asset, pair, exchange, and exchange-asset levels. This allows our users to query the volume for the different entities that exist in the cryptoasset domain.

We use our markets as the entity with the lowest level of aggregation. A market is defined as a specific listed instrument or pair on a specific exchange, like `coinbase-btc-usd-spot`.&#x20;

* For our volume metrics served through `/timeseries/asset-metrics`, the volume for a given asset (like `btc`) represents the sum of the volume from markets where the asset is either the base or quote.\

* For our volume metrics served through `/timeseries/pair-metrics`, the volume for a given pair (like `btc-usd`) represents the sum of the volume from markets that contain the given pair.\

* For our volume metrics served through `/timeseries/exchange`, the volume for a given exchange (like `coinbase`) represents the sum of the volume from all markets on the given exchange.\

* For our volume metrics served through `/timeseries/exchange-assets`, the volume for a given exchange-asset (like `coinbase-btc`) represents the sum of the volume from all markets on the given exchange where the given asset is either the base or quote.

Our other metrics are also aggregated using similar logic described above.

### Are the volume metrics like `volme_reported_spot_usd_1d` double counted?

Our volume metrics for assets and exchange-assets represents the sum of the volume from all markets where the given asset is either the base or quote. For example, the volume for market `coinbase-btc-usdt-spot` will be included in both the volume for `btc` and `usdt` because `btc` is the base asset of the market and `usdt` is the quote asset of the market. Some users have asked whether this represents double counting of volume.

This is a convention that we use that is widely adopted by other data providers. The reasoning behind our choice can be best illustrated using a simple example.

Suppose the world consists of only one market, `coinbase-btc-usdt-spot` and two assets, `btc` and `usdt`. A trader purchases `btc`by selling `usdt` in a transaction worth $100 U.S. dollars. If we only included markets where the given asset is the base currency, then the volume for `btc` would be $100 but the volume for `usdt` would be $0.

In reality, both $100 worth of `btc` and $100 worth of `usdt` were exchanged. So we report the volume for both `btc` and `usdt` to be $100.

