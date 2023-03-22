# Coin Metrics Prices Methodology

The full text of this methodology can be downloaded as a pdf document using the link below.&#x20;

{% file src="../../.gitbook/assets/coin-metrics-prices-methodology.pdf" %}

## Introduction

Coin Metrics publishes a collection of prices for a set of cryptocurrencies and fiat currencies consisting of the Coin Metrics Hourly Reference Rates (“Hourly Reference Rates”), the Coin Metrics Real-Time Reference Rates (“Real-Time Reference Rates”), and the Coin Metrics Principal Market Prices (“Principal Market Prices”), which are collectively referred to as the Coin Metrics Prices (“CM Prices”). This document describes the data inputs, calculation methodologies, and data exclusion rules for the CM Prices.

The Hourly Reference Rates are published once an hour and utlize volume-weighted median and time-weighted average techniques over a 61-minute calculation window. Common use cases for the Hourly Reference Rates include research, backtesting, calculating net asset value for investment funds, calculating closing prices for indexes or financial benchmarks, and settling financial derivatives.

The Real-Time Reference Rates are published once a second and once every 200 milliseconds and utilize volume-weighted median and inverse price variance-weighted median techniques. Common use cases for the Real-Time Reference rates include serving as a data source for on-chain price oracles, risk management, indicative intraday values for investment funds and financial benchmarks, and any use cases where real-time pricing is needed.

The Principal Market Prices are published once a second and adhere to the guidelines regarding fair value measurement issued by the International Financial Reporting Standards and the Association of International Certified Professional Accountants, specifically standards IFRS 13 and FASB ASC 820. The Principal Market Prices identify a principal market for each asset and utilize the most recent price from this market. Common use cases are for fair value measurement, preparing financial statements, and calculating closing prices for indexes or financial benchmarks.

The CM Prices are designed to serve as a set of transparent and independent pricing sources that promote the functioning of efficient markets, reduce information asymmetries among market participants, facilitate trading in standardized contracts, and accelerate the adoption of cryptocurrencies as an asset class with the highest standards. The CM Prices are calculated using robust and resilient methodologies that are resistant to manipulation and adhere to international best practices for financial benchmarks, including the International Organization of Securities Commissions’ (IOSCO) Principles for Financial Benchmarks. The Coin Metrics Oversight Committee (the “Oversight Committee”) and an independent governance structure protect the integrity of the CM Prices and ensure the CM Prices serve as a source of transparent and independent pricing.

## Other Documents

The CM Prices are collectively governed by policies described in [Coin Metrics Prices Policies](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-policies) which describes the administration, oversight, conflicts of interest, material changes and terminations, recalculations, internal controls, complaints, record retention, and compliance policies.

The CM Prices are supervised by the [Coin Metrics Oversight Committee Charter](coin-metrics-oversight-committee-charter.md) which defines the responsibilities of the Oversight Committee.

## Data Inputs

The Oversight Committee evaluates markets traded on digital asset exchanges as potential input data sources for the CM Prices using a Market Selection Framework. The framework consists of a fully-systematized process for evaluating markets along a wide set of criteria to determine if the data source reflects trading activity in a transparent and representative manner. In this framework, a market refers to a specific traded asset pair on a specific exchange. Only spot markets are considered. It produces a unique set of candidate selected markets for each asset in the coverage universe.

The Oversight Committee evaluates new markets for inclusion as a selected market and assesses already selected markets using the Market Selection Framework on a quarterly basis and during interim periods if market conditions warrant. Such market conditions include, but are not limited to, material changes in an exchange’s solvency risk, material changes in the degree of free capital flows in and out of an exchange, the presence of long-lasting price differences from other exchanges, and during times of market stress.

Markets that are approved by the Oversight Committee are added to a list of constituent markets (the “Constituent Markets”). A separate list of Constituent Markets is maintained for each of the assets in the coverage universe.

A candidate market can be nominated for inclusion and an existing constituent market can be nominated for exclusion by any member of the public or member of the Oversight Committee. Public nominations for inclusion or exclusion of a market can be submitted in writing to `support@coinmetrics.io`. The Oversight Committee may convene to apply the Market Selection Framework to evaluate the inclusion or exclusion of a market between regularly-scheduled quarterly meetings if market conditions or circumstances warrant. Coin Metrics publishes a current list of Constituent Markets for each asset in the coverage universe, as well as updates on inclusions or exclusions of constituent markets, and the rationale for making any change.

The data inputs for the calculation of the CM Prices are observable transactions in a constituent where the given asset is traded.

### Feature Descriptions

The Market Selection Framework consists of 45 features, 36 of which are in active use. Features represent individual measurable properties that provide an indication of the suitability for a market to serve as an input data source, which are combined to form a market rating.

Some of the features described in this section are indicator variables that encode qualitative information about a market or exchange. These indicator variables can require a degree of subjectivity in determining whether a market or exchange meets a certain criteria. In such cases, the indicator variable is set to true only if an unambiguous source is found that provides sufficient information to make an evaluation. In the absence of such a source, the indicator variable is set to false.

#### Technology

An assessment of whether the technology infrastructure of the market’s exchange provides sufficient availability and reliability for input data collection. Evaluates whether the exchange offers a REST API or websocket feed for data collection. Evaluates the performance of the API in terms of reliability.

1. **`has_rest_api`**: An indicator variable for the existence of a REST API.
2. **`has_websocket_feed`**: An indicator variable for the existence of a websocket feed.
3. **`has_fix_gateway`**: An indicator variable for the existence of a FIX gateway.
4. **`has_historical_trade_data`**: An indicator variable for whether the exchange offers historical trade data via its API.
5. **`has_real_time_trade_data`**: An indicator variable for whether the exchange offers real-time trade data via its API.
6. **`has_real_time_order_book_data`**: An indicator variable for whether the exchange offers real-time order book data via its API.
7. **`api_downtime_incidents`**: A feature that represents the stability of an API.

#### Legal and Compliance

An assessment of selected indicator variables relating to compliance and risk for each exchange. These indicator variables include whether the exchange has publicly-disclosed trading policies, uses market surveillance technology, obtains regulatory licenses, has fiat and crypto insurance, requires customers to verify their identity before opening an account as part of its KYC and AML process, and whether the exchange has functioning fiat and cryptocurrency withdrawals processed within a normal timeframe.

1. **`has_trading_policy`**: An indicator variable for whether the exchange has a trading policy to promote fair and transparent markets. The trading policy should explicitly address manipulative trading policies like front-running, wash trading, spoofing, layering, churning, and quote stuffing.
2. **`has_market_surveillance`**: An indicator variable for whether the exchange uses market surveillance technology to detect market manipulation practices, including front-running, wash trading, spoofing, layering, churning, and quote stuffing.
3. **`has_regulatory_oversight`**: An indicator variable for whether the exchange obtains licenses from national or regional regulatory organizations.
4. **`has_fiat_insurance`**: An indicator variable for whether the exchange maintains commercial insurance or is covered under government-provided insurance to insure against losses of customer funds denominated in fiat currencies.
5. **`has_crypto_insurance`**: An indicator variable for whether the exchange maintains commercial insurance to insure against losses of customer funds denominated in digital assets.
6. **`has_kycaml`**: An indicator variable for whether the exchange requires identity verification before being able to open an account as part of its KYC and AML process. For the purposes of this indicator variable, an exchange which requires identity verification only if a customer wishes to deposit or withdraw fiat or if a customer wishes to withdraw digital assets is determined to not have sufficient controls. An exchange must require customers to verify their identity when opening an account as part of its KYC and AML process.
7. **`has_free_capital_flows`**: An indicator variable for whether the exchange has had a history of free capital flows over the last quarter, including functioning fiat and digital asset deposits and withdrawals that are processed within a normal timeframe.

#### Business Model

An assessment of the market’s exchange with respect to its business model, including its fee structure and asset listing standards.

1. **`has_fiat_markets`**: An indicator variable that indicates whether the exchange has markets where the quote currency is a fiat currency.
2. **`has_fees`**: An indicator variable that indicates whether the exchange charges trading fees as a percentage of the trade size. Exchanges that charge zero fees or charge fees indirectly through a transaction mining model are determined to not charge fees.
3. **`has_listing_standards`**: An indicator variable that indicates whether the exchange has publicly disclosed a framework for deciding which assets to list.
4. **`has_usa_hq`**: An indicator variable for whether the company’s headquarters are domiciled in the United States.

#### Data Availability

An assessment of the available data the market’s exchange offers for the given digital asset, including the amount of historical data available for a market and the quoted currency of the market.

1. **`market_days_history`**: The number of days of historical data for the market.
2. **`market_quote_modifier`**: An optional modifier to give greater weight to a certain quote currency. Currently all quote currencies have equal weight.

#### Price

An assessment of the quality of the market’s price data, including testing for the occurrence of price outliers and impactful price deviations from other markets, and implementing tests that determine whether the exchange’s markets function as active markets in the underlying digital asset and are anchored by observable transactions entered into at arm’s length between buyers and sellers.

In this section, prices are compared to the global median price. The global median price is defined as the median price of all markets in which the digital asset is the base currency from the following list of exchanges: `["Coinbase", "Poloniex", "Bittrex", "Gemini", "Kraken", "Binance", "Bitstamp", "itBit"]`. This list of exchanges was selected by first calculating the market ratings for each market but without the price-related features below. The median market rating was then calculated for each exchange and the top 8 exchanges were selected.

1. **`market_open_mape_all`**: The mean absolute percentage error of the market’s daily open price compared to the global median’s daily open price over the last 90 days.
2. **`market_close_mape_all`**: The mean absolute percentage error of the market’s daily close price compared to the global median’s daily close price over the last 90 days.
3. **`market_low_mape_all`**: The mean absolute percentage error of the market’s daily low price compared to the global median’s daily low price over the last 90 days.
4. **`market_high_mape_all`**: The mean absolute percentage error of the market’s daily high price compared to the global median’s daily high price over the last 90 days.
5. **`market_open_mape_trimmed`**: The mean absolute percentage error of the market’s daily open price trimmed to exclude the bottom and top 5th percentiles compared to the global median’s daily open price over the last 90 days.
6. **`market_close_mape_trimmed`**: The mean absolute percentage error of the market’s daily close price trimmed to exclude the bottom and top 5th percentiles compared to the global median’s daily close price over the last 90 days.
7. **`market_low_mape_trimmed`**: The mean absolute percentage error of the market’s daily low price trimmed to exclude the bottom and top 5th percentiles compared to the global median’s daily low price over the last 90 days.
8. **`market_high_mape_trimmed`**: The mean absolute percentage error of the market’s daily high price trimmed to exclude the bottom and top 5th percentiles compared to the global median’s daily high price over the last 90 days.

#### Volume

An assessment of the quality of the market’s volume data, including testing for manipulated volume figures, and implementing tests that determine whether the exchange’s markets function as active markets in the underlying digital asset and are anchored by observable transactions entered into at arm’s length between buyers and sellers. The size of the exchange’s markets is also considered.

1. **`market_volume_usd`**: The total volume of the market over the past 90 days in U.S. dollars.
2. **`market_volume_dispersion`**: The coefficient of variation of the market’s daily volume in U.S. dollars over the past 90 days.
3. **`market_volume_price_corr_raw`**: The correlation of the market’s daily return to detrended daily volume where volume is quoted in raw units over the past 90 days.
4. **`market_volume_price_corr_usd`**: The correlation of the market’s daily return to detrended daily volume where volume is quoted in U.S. dollars over the past 90 days.
5. **`alexa_rank`**: The global rank of the exchange’s website as reported by Alexa.
6. **`alexa_page_views_per_million`**: The average page views per million visitors of the exchange’s website over the past month as reported by Alexa.
7. **`alexa_reach_per_million`**: The average reach per million visitors of the exchange’s website over the past month as reported by Alexa.
8. **`alexa_pvpmvu`**: The total U.S. dollar volume of the exchange over the past month divided by the page views per million visitors as reported by Alexa.
9. **`alexa_rpmvu`**: The total U.S. dollar volume of the exchange over the past month divided by the reach per million visitors as reported by Alexa.
10. **`similarweb_global_rank`**: The global rank of the exchange’s website as reported by SimilarWeb.
11. **`similarweb_visit_monthly`**: The number of monthly visits as reported by SimilarWeb.
12. **`similarweb_vmvu`**: The total U.S. dollar volume of the exchange over the past month divided by the monthly visits as reported by SimilarWeb.

#### Order Book

An assessment of the quality of the market’s order book data, including tests for manipulated orders, and implementing tests that determine whether the market functions as an active market in the underlying digital asset and are anchored by observable transactions entered into at arm’s length between buyers and sellers. The liquidity of the market is also considered.

1. **`order_book_depth`**: The total volume of bids and offers on the order book within 1 percent of the mid price of the exchange’s largest traded market where the given asset is the base currency reported in U.S. dollars.
2. **`slippage`**: The amount of slippage in percent terms if an immediate market sell order of $50,000 U.S. dollars is executed of the exchange’s largest traded market where the given asset is the base currency.
3. **`spread`**: The median of the spread calculated as the difference between the best bid minus the best ask divided by the mid-price over the past 30 days.
4. **`order_book_depth_residual`**: A regression model is fit by regressing volume on order book depth for the largest traded market for a collection of exchanges. Given an order book depth, an estimated volume is calculated and a residual is calculated as `actual_volume - estimated_volume`.
5. **`slippage_residual`**: A regression model is fit by regressing volume on slippage for the largest traded market for a collection of exchanges. Given a slippage, an estimated volume is calculated and a residual is calculated as `actual_volume - estimated_volume`.

### Feature Normalization

All features are normalized to between 0 and 1, with a number closer to 1 meaning that the feature contributes positively to the likelihood that the market will be selected. The qualitative features are all indicator variables that take values 0 or 1. For quantitative features, a separate empirical cumulative distribution function is calculated for all the markets for each asset. The quantitative feature is normalized by converting the value to its equivalent value on the empirical cumulative distribution function.

### Rating Algorithm

In order for a market to be eligible to receive a rating, the following three indicator variables for the market must be true: `has_rest_api`, `has_real_time_trade_data`, `has_real_time_order_book_data`. These indicator variables are required to be true because the ability to collect real-time trade data and real-time order book data via an API is necessary in order for the market to serve as an input data source.

The rating algorithm uses a weighted sum using a custom weighting function of the normalized features:

| Feature                          | Weight |
| -------------------------------- | ------ |
| has\_websocket\_feed             | 1      |
| has\_fix\_gateway                | 1      |
| has\_historical\_trade\_data     | 1      |
| has\_trading\_policy             | 1      |
| has\_market\_surveillance        | 1      |
| has\_regulatory\_oversight       | 1      |
| has\_kycaml                      | 1      |
| has\_fiat\_insurance             | 1      |
| has\_crypto\_insurance           | 1      |
| has\_free\_capital\_flows        | 3      |
| has\_fiat\_market                | 1      |
| has\_fees                        | 1      |
| has\_listing\_standards          | 1      |
| has\_usa\_hq                     | 3      |
| market\_days\_history            | 1      |
| market\_quote\_modifier          | 1      |
| market\_open\_mape\_all          | 1      |
| market\_close\_mape\_all         | 1      |
| market\_low\_mape\_all           | 1      |
| market\_high\_mape\_all          | 1      |
| market\_open\_mape\_trimmed      | 1      |
| market\_close\_mape\_trimmed     | 1      |
| market\_low\_mape\_trimmed       | 1      |
| market\_high\_mape\_trimmed      | 1      |
| market\_volume\_usd              | 3      |
| market\_volume\_dispersion       | 1      |
| market\_volume\_price\_corr\_raw | 1      |
| market\_volume\_price\_corr\_usd | 1      |
| alexa\_rank                      | 2      |
| alexa\_page\_views\_per\_million | 1      |
| alexa\_reach\_per\_million       | 1      |
| alexa\_pvpmvu                    | 1      |
| alexa\_rpmvu                     | 1      |
| similarweb\_global\_rank         | 2      |
| similarweb\_visit\_monthly       | 1      |
| similarweb\_vmvu                 | 1      |

### Selection Algorithm

Markets with a rating higher than 22.5 are selected. For each asset in the coverage universe, markets that are in the top 4 by rank are also selected, regardless of the market’s rating. Any market with volume, measured in U.S. dollars over the past 90 days, of less than 5 percent of the volume of the selected market with the largest volume is excluded.

### Candidate Markets

The pool of candidate markets that are evaluated by the Market Selection Framework are determined by a hierarchy of data inputs that varies depending on the given asset.

#### Bitcoin (BTC) and Ethereum (ETH)

The pool of candidate markets that are evaluated for the calculation of the CM Prices for Bitcoin (BTC) and Ethereum (ETH) are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given cryptocurrency is the base currency and the quote currency is U.S. dollars.
2. Markets where the given cryptocurrency is the base currency and the quote currency is not U.S. dollars are not considered, including markets quoted in other fiat currencies or markets quoted in stablecoins.

#### Other Cryptocurrencies Excluding Stablecoins

The pool of candidate markets that are evaluated for the calculation of the CM Prices for cryptocurrencies, excluding Bitcoin (BTC), Ethereum (ETH), and stablecoins are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given cryptocurrency is the base currency and the quote currency is U.S. dollars.
2. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is Bitcoin (BTC).
3. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is Ethereum (ETH).
4. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is USD Coin (USDC).
5. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where the given cryptocurrency is the base currency and quote currency is Tether (USDT).

#### Stablecoins

The pool of candidate markets that are evaluated for the calculation of the CM Prices for stablecoins are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given stablecoin is the base currency and the quote currency is U.S. dollars.
2. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where Bitcoin (BTC) is the base currency and quote currency is the given stablecoin.
3. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where Ethereum (ETH) is the base currency and quote currency is the given stablecoin.
4. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where the given stablecoin is the base currency and quote currency is USD Coin (USDC).
5. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where the given stablecoin is the base currency and quote currency is Tether (USDT).

The data hierarchy for stablecoins differs from other cryptocurrencies because market convention sets stablecoins as the quote currency for the majority of active markets. The following assets in the coverage universe are considered to be stablecoins:

| Name              | Ticker |
| ----------------- | ------ |
| Tether            | usdt   |
| TrueUSD           | tusd   |
| USD Coin          | usdc   |
| Paxos Standard    | pax    |
| Gemini Dollar     | gusd   |
| Binance USD       | busd   |
| Dai               | dai    |
| USDK              | usdk   |
| BIDR              | bidr   |
| sUSD              | susd   |
| Neutrino USD      | usdn   |
| TerraUSD          | ust    |
| Pax Dollar        | usdp   |
| USDD              | usdd   |
| Euro Coin         | euroc  |
| Staked Ether Lido | steth  |
| poundtoken        | gbpt   |

#### Fiat Currencies

The pool of candidate markets that are evaluated for the calculation of the CM Prices for fiat currencies are determined using the following data hierarchy:

1. The primary data input is observable transactions in an active market where the given fiat currency is the base currency and the quote currency is U.S. dollars.
2. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where Bitcoin (BTC) is the base currency and quote currency is the given fiat currency.
3. If the above data inputs do not exist or are insufficient to calculate the price, the universe of data inputs will expand to include observable transactions in an active market where Ethereum (ETH) is the base currency and quote currency is the given fiat currency.

The data hierarchy for fiat currencies differs from other cryptocurrencies because market convention sets fiat currencies as the quote currency for the majority of active markets. The following assets in the coverage universe are considered to be fiat currencies:

| Name              | Ticker |
| ----------------- | ------ |
| Euro              | eur    |
| British Pound     | gbp    |
| Japanese Yen      | jpy    |
| Canadian Dollar   | cad    |
| Korean won        | krw    |
| Russian Ruble     | rub    |
| Ukrainian Hryvnia | uah    |
| Turkish Lira      | try    |
| Australian Dollar | aud    |
| Brazilian Real    | brl    |
| Swiss Franc       | chf    |
| Hong Kong Dollar  | hkd    |
| Singapore Dollar  | sgd    |

## Hourly Reference Rates Calculation Methodology

The Hourly Reference Rates are published hourly, every day of the year, and represent the reference rate of one unit of the asset quoted in U.S. dollars or other currency. The Hourly Reference Rates are calculated at the end of every hour (the “Calculation Time”) and are published within 5 minutes (the “Publication Time”).

### Coverage Universe

The set of assets included in the Hourly Reference Rates coverage universe are included in Appendix A.

### Calculation Algorithm

The calculation algorithm of the Hourly Reference Rates is described below.

1. All observable transactions from Constituent Markets are combined and partitioned into time intervals, with each time interval spanning a period of one minute. The first one-minute time interval begins 60 minutes before the Calculation Time and the last one-minute time interval begins at the Calculation and ends one minute after the Calculation Time. In total, the calculation period spans a period of 61 minutes (the “Observation Window”). A total of 61 one-minute time intervals are created.
2. The price of each observable transaction for one unit of the given asset is converted to U.S. dollars if necessary using the Reference Rates calculated for Bitcoin (BTC), Ethereum (ETH), USD Coin (USDC), or Tether (USDT).
3. The volume-weighted median price (VWMP) of each time interval is calculated. The volume-weighted median rate is calculated by ordering the transactions from lowest to highest price, taking the cumulative sum of volumes of these transactions, and identifying the price associated with the trades at the 50th percentile of volume measured in native units.
4. The time-weighted average price (TWAP) of the 61 time intervals is calculated using a custom weight function. The weight function assigns a weight of 0 percent to the first time interval, subsequent time intervals are assigned a weight that increases linearly, and the last two time intervals are assigned a weight of 5 percent such that the sum of all weights equals 100 percent. The weight function assigns more weight to time slices that are closer to the Calculation Time. The resulting figure is the published reference rate.

A chart of the weights is included below and the exact weights for each time interval are listed in Appendix B:

<figure><img src="../../.gitbook/assets/reference-rates-weights (1).png" alt=""><figcaption></figcaption></figure>

### Data Contingency Rules

The following contingency rules are followed to address situations where data is delayed, missing, or unavailable due to periods of illiquidity, extraordinary market circumstances, or outside factors beyond the control of Coin Metrics.

1. If observable transactions from a constituent market are unable to be collected due to technical problems specific to the constituent market’s exchange during the calculation of a reference rate, the observable transactions from the constituent market are not included in the calculation of the specific instance of the given reference rate.
2. If no observable transactions from constituent markets occur during the first one-minute time interval, the next one-minute time interval’s volume-weighted median price is used as the volume-weighted median price. This contingency rule is applied recursively if necessary.
3. If no observable transactions from constituent markets occur during any one-minute time intervals, excluding the first and last one-minute time intervals in the Calculation Window, the next one-minute time interval’s volume-weighted median price is used as the volume-weighted median price. This contingency rule is applied recursively if necessary.
4. If no observable transactions from constituent markets occur during the last one-minute time interval, the previous time interval’s volume-weighted median price is used as the volume-weighted median price. This contingency rule is applied recursively if necessary.
5. If no observable transactions from constituent markets exist during the Calculation Period for a reference rate, the reference rate will be determined to equal the previous hourly reference rate in which there were trades during that hour’s Observation Window.

## Real-Time Reference Rates Calculation Methodology

The Real-Time Reference Rates (“Real-Time Reference Rates”) are published once per second and once per 200 milliseconds, every day of the year, and represent the reference rate of one unit of the asset quoted in U.S. dollars or other currency.

### Coverage Universe

The set of assets included in the Real-Time Reference Rates coverage universe are included in Appendix A.

### Calculation Algorithm

The calculation algorithm of the Real-Time Reference Rates is described below.

1. Calculate the volume denominated in units of the given asset from observable transactions that occurred over the trailing 60 minutes for each of the Constituent Markets. Calculate the volume weight for each of the Constituent Markets by dividing the volume figure for each of the Constituent Markets by the total volume across all Constituent Markets. The resulting figure is referred to as the volume weight.
2. Convert the trade price of all observable transactions over the trailing 60 minutes for each of the Constituent Markets to U.S. dollars if necessary using the Real-Time Reference Rate calculated for Bitcoin (BTC), Ethereum (ETH), USD Coin (USDC), or Tether (USDT). Calculate the inverse variance of the trade price converted to U.S. dollars for each of the Constituent Markets using the population mean in the calculation of variance, where the population mean is defined as the mean price of all trades from Constituent Markets over the trailing 60 minutes. If a Constituent Market has an infinite or undefined inverse price variance, the inverse price variance for that Constituent Market is set to zero. Calculate the inverse price variance weight for each of the Constituent Markets by dividing the inverse price variance by the total inverse price variance across all Constituent Markets. The resulting figure is referred to as the inverse price variance weight.
3. Calculate the final weight for each of the Constituent Markets by taking a mean of the volume weight and the inverse price variance weight.
4. Extract the most recent observable transaction from each of the Constituent Markets. Convert the trade price of the most recent observable transactions to U.S. dollars if necessary using the Real-Time Reference Rate calculated for Bitcoin (BTC), Ethereum (ETH), USD Coin (USDC), or Tether (USDT).
5. Calculate the weighted median price of the most recent observable transactions using the prices calculated in step 4 and the final weights calculated in step 3. The weighted median price is calculated by ordering the transactions from lowest to highest price, and identifying the price associated with the trades at the 50th percentile of final weight. The resulting figure is the Real-Time Reference Rate for the given asset.

### Data Contingency Rules

The following contingency rules are followed to address situations where data is delayed, missing, or unavailable due to periods of illiquidity, extraordinary market circumstances, or outside factors beyond the control of Coin Metrics.

1. If observable transactions from a constituent market are unable to be collected due to technical problems specific to the constituent market’s exchange during the calculation of a real-time reference rate, the observable transactions from the constituent market are not included in the calculation of the specific instance of the given real-time reference rate.
2. If no observable transactions from constituent markets exist during the trailing 60 minutes, the value of the real-time reference rate will be determined to equal the value calculated during the previous second.

## Principal Market Prices Calculation Methodology

The Principal Market Prices are published once per second, every day of the year, and represent the price of one unit of the asset quoted in U.S. dollars.

### Fair Market Valuation Background

The Principal Market Prices were developed taking into account the requirements of IFRS 13 and FASB ASC 820 accounting guidelines defining what a Principal Market is and how it should be selected. These guidelines also allow for additional controls to verify the market is active and trades are orderly.

As Coin Metrics already provides Hourly Reference Rates and Real-Time Reference Rates methodologies to price cryptocurrencies which we believe to be robust and stable, it is worth briefly describing the philosophy behind producing the Principal Market Prices to supplement the reference rates. The first and most significant criteria is that certain regulatory agencies require a methodology consistent with the aforementioned accounting principles. These principles clearly describe the preferred “fair market value” calculation as one which identifies a Principal Market by trade volume and tracks executed trades in that market.

Beyond external requirements, the benefits for a Principal Market Prices methodology are that it is clearly defined and auditable. The price is always taken from a single market, which tends to remain constant, and can easily be traced and verified for a given time stamp. We minimize computations being done on the price, which reduces the likelihood of unforeseen behavior. Additionally, the trades are always taken from the exchange where the most of the activity occurs, which is a characteristic users are interested in.

Like all things in life, this comes with some trade offs. Our Hourly Reference Rates and Real-Time Reference Rates look for a central tendency among several markets. In some cases this can avoid volatility and the presence of outliers if the Principal Market Prices deviate from the global average, but it also means that the final price may be taken from comparatively insignificant market where the price is between the prices of markets of larger volume. With these trade-offs in mind, our methodology seeks to err on the side of trusting the largest market by volume of trades and only excludes a market in extreme situations.

We also attempt to avoid numerical comparisons of the price between markets in the methodology, in order to minimize the possibility that a price anomaly in another market could affect the calculation. Our Hourly Reference Rates and Real-Time Reference Rates by contrast choose to combine multiple markets to identify a more stable price representative of the global environment.

### Coverage Universe

The set of assets included in the Principal Market Prices coverage universe are included in Appendix A.

### Calculation Algorithm

The calculation algorithm of the Principal Market Prices is described below.

1. Consider the list of Constituent Markets selected by the Market Selection Framework.
2.  Identify any inactive markets, and exclude all trades associated with the inactive market. A market is considered inactive if it meets the following conditions:

    The last trade was more than 1-minute ago and the last trade was either: longer than 10 minutes from the calculation time or longer than 100 \* \[mean trade interval].

    The mean trade interval is defined as the the average of all intervals between sequential trades in the window 0 to 60 minutes before the calculation time. For example, if trades occur at timestamps `[00:02, 00:12, 00:37, 01:15]`, the mean trade interval will be `mean([10 seconds, 25 seconds, 38 seconds]) = 23.3 seconds`.

    If there are no active markets, then the Principal Market Price will forward-fill the last non-null value available.
3.  Check if any trades in the markets are not considered orderly (IFRS 13.B37-B38). Exclude any non-orderly trades from the calculation.

    This is accomplished by examining the window 60 to 120 minutes before the calculation time to calculate a reference standard deviation of prices in each market separately. If there are insufficient trades to calculate a standard deviation, then all trades are considered orderly (i.e. no trades are dropped if there is sparse data).

    We then partition the calculation window 0 to 60 minutes before the calculation time into 60 one-minute time intervals and calculate how far each trade is from the mean price of trades from that market in the one-minute time interval the trade resides in.

    Finally, we exclude trades that occur more than three reference standard deviations from the mean price of trades within a particular one-minute time interval.

    We require at least five trades occur in a particular one-minute time interval in order to exclude trades. The two parameters (3 reference deviations and 5 trades) may be adjusted in the future.
4. Identify the active market with the largest volume of orderly trades in the calculation window 0 to 60 minutes before the calculation time. This will serve as the Principal Market (IFRS 13.16, FASB ASC 820-35-5).
5. Use the most recent orderly trade from the Principal Market and publish its price as the Principal Market Price.

## Data Exclusion Rules

All observable transactions from constituent markets are evaluated using a systematic data quality control process. If potential errors or anomalies in the data are detected, the exercise of expert judgment will be applied to determine if the potentially erroneous data is included in the calculation of the price. The exercise of expert judgment in this circumstance is used to determine if the potentially erroneous data reflects observable transactions that are entered into at arm’s length between buyers and sellers and constitute an active market in the underlying asset, whether the observable transactions in question are formed by the competitive forces of supply and demand, and whether the observable transactions in question are a credible indicator of executable prices in the underlying asset.

An investigation into the causes of the potential error, including whether any price deviations are specific to the exchange itself, is conducted. Any exercise of expert judgment is subject to dual approval by staff members, and is logged and reported to the Oversight Committee which periodically reviews the application of expert judgment to ensure consistency.

## Appendix A

The following table lists the current coverage universe:

| #   | Name                                 | Ticker                  |
| --- | ------------------------------------ | ----------------------- |
| 1   | Bitcoin                              | btc                     |
| 2   | Bitcoin Cash                         | bch                     |
| 3   | Litecoin                             | ltc                     |
| 4   | Euro                                 | eur                     |
| 5   | XRP                                  | xrp                     |
| 6   | Ethereum                             | eth                     |
| 7   | Ethereum Classic                     | etc                     |
| 8   | British Pound                        | gbp                     |
| 9   | Zcash                                | zec                     |
| 10  | Monero                               | xmr                     |
| 11  | Dash                                 | dash                    |
| 12  | Japanese Yen                         | jpy                     |
| 13  | IOTA                                 | miota                   |
| 14  | EOS                                  | eos                     |
| 15  | OMG Network                          | omg                     |
| 16  | Neo                                  | neo                     |
| 17  | Metaverse ETP                        | etp                     |
| 18  | Qtum                                 | qtum                    |
| 19  | Aventus                              | avt                     |
| 20  | Bitcoin Gold                         | btg                     |
| 21  | Streamr                              | data                    |
| 22  | QASH                                 | qash                    |
| 23  | Status                               | snt                     |
| 24  | Basic Attention Token                | bat                     |
| 25  | Decentraland                         | mana                    |
| 26  | FUNToken                             | fun                     |
| 27  | 0x                                   | zrx                     |
| 28  | Time New Bank                        | tnb                     |
| 29  | TRON                                 | trx                     |
| 30  | iExec RLC                            | rlc                     |
| 31  | Augur                                | rep                     |
| 32  | aelf                                 | elf                     |
| 33  | IOST                                 | iost                    |
| 34  | Aion                                 | aion                    |
| 35  | Request                              | req                     |
| 36  | Loopring                             | lrc                     |
| 37  | WAX                                  | waxp                    |
| 38  | Aragon                               | ant                     |
| 39  | Mithril                              | mith                    |
| 40  | Storj                                | storj                   |
| 41  | Stellar                              | xlm                     |
| 42  | Verge                                | xvg                     |
| 43  | Lympo                                | lym                     |
| 44  | Maker                                | mkr                     |
| 45  | VeChain                              | vet                     |
| 46  | Kyber Network Crystal                | knc                     |
| 47  | Utrust                               | utk                     |
| 48  | Ripio Credit Network                 | rcn\_ripiocreditnetwork |
| 49  | Polymath                             | poly                    |
| 50  | Fusion                               | fsn                     |
| 51  | Nitro Network                        | ncash                   |
| 52  | Cortex                               | ctxc                    |
| 53  | DATA                                 | dta                     |
| 54  | Zilliqa                              | zil                     |
| 55  | Bancor                               | bnt                     |
| 56  | MonaCoin                             | mona                    |
| 57  | NEM                                  | xem                     |
| 58  | BNB                                  | bnb                     |
| 59  | Gas                                  | gas                     |
| 60  | Tether                               | usdt                    |
| 61  | OAX                                  | oax                     |
| 62  | district0x                           | dnt                     |
| 63  | Waltonchain                          | wtc                     |
| 64  | Chainlink                            | link                    |
| 65  | Moeda Loyalty Points                 | mda                     |
| 66  | Metal DAO                            | mtl\_metal              |
| 67  | AirSwap                              | ast                     |
| 68  | Viberate                             | vib                     |
| 69  | Powerledger                          | powr                    |
| 70  | Ark                                  | ark                     |
| 71  | Enjin Coin                           | enj                     |
| 72  | Komodo                               | kmd                     |
| 73  | NULS                                 | nuls                    |
| 74  | AirDAO                               | amb                     |
| 75  | Quantstamp                           | qsp                     |
| 76  | BitShares                            | bts                     |
| 77  | Lisk                                 | lsk                     |
| 78  | Bitcoin Diamond                      | bcd                     |
| 79  | Ambire AdEx                          | adx                     |
| 80  | Cardano                              | ada                     |
| 81  | CyberMiles                           | cmt                     |
| 82  | Waves                                | waves                   |
| 83  | ICON                                 | icx                     |
| 84  | PIVX                                 | pivx                    |
| 85  | OST                                  | ost                     |
| 86  | ChatCoin                             | chat                    |
| 87  | Civic                                | cvc                     |
| 88  | Steem                                | steem                   |
| 89  | Nano (New)                           | nano                    |
| 90  | Bluzelle                             | blz                     |
| 91  | Aeternity                            | ae                      |
| 92  | Ontology                             | ont                     |
| 93  | Wanchain                             | wan                     |
| 94  | Kepple                               | qlc                     |
| 95  | Syscoin                              | sys                     |
| 96  | Ardor                                | ardr                    |
| 97  | Holo                                 | hot\_holo               |
| 98  | Loom Network                         | loom                    |
| 99  | Bytecoin                             | bcn                     |
| 100 | TrueUSD                              | tusd                    |
| 101 | Horizen                              | zen                     |
| 102 | Theta Network                        | theta                   |
| 103 | IoTeX                                | iotx                    |
| 104 | QuarkChain                           | qkc                     |
| 105 | SelfKey                              | key                     |
| 106 | Siacoin                              | sc                      |
| 107 | Nebulas                              | nas                     |
| 108 | Dent                                 | dent                    |
| 109 | Dock                                 | dock                    |
| 110 | Gnosis                               | gno                     |
| 111 | Canadian Dollar                      | cad                     |
| 112 | Enzyme                               | mln                     |
| 113 | Dogecoin                             | doge                    |
| 114 | Bytom                                | btm                     |
| 115 | BitKan                               | kan                     |
| 116 | Arcblock                             | abt                     |
| 117 | Auto                                 | auto                    |
| 118 | CyberVein                            | cvt                     |
| 119 | Decred                               | dcr                     |
| 120 | DigiByte                             | dgb                     |
| 121 | Cred                                 | lba                     |
| 122 | Measurable Data Token                | mdt                     |
| 123 | Molecular Future                     | mof                     |
| 124 | TenX                                 | pay                     |
| 125 | Revain                               | rev                     |
| 126 | Ren                                  | ren                     |
| 127 | SwftCoin                             | swftc                   |
| 128 | Nxt                                  | nxt                     |
| 129 | VITE                                 | vite                    |
| 130 | Odyssey                              | ocn                     |
| 131 | Huobi Token                          | ht                      |
| 132 | Elastos                              | ela                     |
| 133 | WaykiChain                           | wicc                    |
| 134 | SIRIN LABS Token                     | srn                     |
| 135 | DeepBrain Chain                      | dbc                     |
| 136 | Propy                                | pro                     |
| 137 | Bibox Token                          | bix                     |
| 138 | HyperCash                            | hc\_hypercash           |
| 139 | MaidSafeCoin                         | maid                    |
| 140 | Amp                                  | amp                     |
| 141 | Chrono.tech                          | time                    |
| 142 | Pluton                               | plu                     |
| 143 | Tezos                                | xtz                     |
| 144 | Stacks                               | stx                     |
| 145 | Ignis                                | ignis                   |
| 146 | Atletico De Madrid Fan Token         | atm                     |
| 147 | PolySwarm                            | nct                     |
| 148 | Kin                                  | kin                     |
| 149 | IndiGG                               | indi                    |
| 150 | SwissBorg                            | chsb                    |
| 151 | OriginTrail                          | trac                    |
| 152 | Nexo                                 | nexo                    |
| 153 | Telcoin                              | tel                     |
| 154 | Berry                                | berry                   |
| 155 | Crypterium                           | crpt                    |
| 156 | IHT Real Estate Protocol             | iht                     |
| 157 | VeThor Token                         | vtho                    |
| 158 | DxChain Token                        | dx                      |
| 159 | CEEK VR                              | ceek                    |
| 160 | Oxygen                               | oxy                     |
| 161 | UNUS SED LEO                         | leo                     |
| 162 | Vertcoin                             | vtc                     |
| 163 | Game.com                             | gtc\_gamecom            |
| 164 | MediBloc                             | med                     |
| 165 | Creditcoin                           | ctc                     |
| 166 | NKN                                  | nkn                     |
| 167 | Uquid Coin                           | uqc                     |
| 168 | Korean won                           | krw                     |
| 169 | IQ                                   | iq                      |
| 170 | Ravencoin                            | rvn                     |
| 171 | LBRY Credits                         | lbc                     |
| 172 | ReddCoin                             | rdd                     |
| 173 | Numeraire                            | nmr                     |
| 174 | Russian Ruble                        | rub                     |
| 175 | Ukrainian Hryvnia                    | uah                     |
| 176 | Turkish Lira                         | try                     |
| 177 | Aurora Chain                         | aoa                     |
| 178 | Australian Dollar                    | aud                     |
| 179 | Brazilian Real                       | brl                     |
| 180 | Swiss Franc                          | chf                     |
| 181 | Ethernity                            | ern                     |
| 182 | Hong Kong Dollar                     | hkd                     |
| 183 | Singapore Dollar                     | sgd                     |
| 184 | OpenDAO                              | sos                     |
| 185 | Dragonchain                          | drgn                    |
| 186 | Kleros                               | pnk                     |
| 187 | USD Coin                             | usdc                    |
| 188 | KuCoin Token                         | kcs                     |
| 189 | Paxos Standard                       | pax                     |
| 190 | Gemini Dollar                        | gusd                    |
| 191 | Constellation                        | dag                     |
| 192 | Nimiq                                | nim                     |
| 193 | GoChain                              | go                      |
| 194 | Electroneum                          | etn                     |
| 195 | Bitcoin SV                           | bsv                     |
| 196 | MXC                                  | mxc                     |
| 197 | TomoChain                            | tomo                    |
| 198 | Livepeer                             | lpt                     |
| 199 | RSK Infrastructure Framework         | rif                     |
| 200 | v.systems                            | vsys                    |
| 201 | Grin                                 | grin                    |
| 202 | Seele                                | seele                   |
| 203 | Lambda                               | lamb                    |
| 204 | Dora Factory                         | dora                    |
| 205 | Beam                                 | beam                    |
| 206 | Unibright                            | ubt                     |
| 207 | FTX Token                            | ftt                     |
| 208 | Kryll                                | krl                     |
| 209 | Fetch.ai                             | fet                     |
| 210 | Ontology Gas                         | ong\_ontologygas        |
| 211 | Ankr                                 | ankr                    |
| 212 | Haven Protocol                       | xhv                     |
| 213 | Quant                                | qnt                     |
| 214 | SOLVE                                | solve                   |
| 215 | Aergo                                | aergo                   |
| 216 | Circuits of Value                    | coval                   |
| 217 | Cronos                               | cro                     |
| 218 | Cosmos                               | atom                    |
| 219 | Orbs                                 | orbs                    |
| 220 | Theta Fuel                           | tfuel                   |
| 221 | BORA                                 | bora                    |
| 222 | Function X                           | fx                      |
| 223 | IRISnet                              | iris                    |
| 224 | Celer Network                        | celr                    |
| 225 | ABBC Coin                            | abbc                    |
| 226 | Verasity                             | vra                     |
| 227 | Wrapped Bitcoin                      | wbtc                    |
| 228 | Polygon                              | matic                   |
| 229 | Litentry                             | lit                     |
| 230 | Fantom                               | ftm                     |
| 231 | Algorand                             | algo                    |
| 232 | Dusk Network                         | dusk                    |
| 233 | XYO                                  | xyo                     |
| 234 | Ocean Protocol                       | ocean                   |
| 235 | Celsius                              | cel                     |
| 236 | Synthetix                            | snx                     |
| 237 | ThunderCore                          | tt                      |
| 238 | MovieBloc                            | mbl                     |
| 239 | Reserve Rights                       | rsr                     |
| 240 | STP                                  | stpt                    |
| 241 | Harmony                              | one\_harmony            |
| 242 | ARPA                                 | arpa                    |
| 243 | Phoenix                              | phb                     |
| 244 | WINkLink                             | win\_wink               |
| 245 | Binance USD                          | busd                    |
| 246 | Dai                                  | dai                     |
| 247 | Tether Gold                          | xaut                    |
| 248 | PAX Gold                             | paxg                    |
| 249 | OKB                                  | okb                     |
| 250 | Hedera                               | hbar                    |
| 251 | Nervos Network                       | ckb                     |
| 252 | Solar                                | sxp                     |
| 253 | Terra Classic                        | luna                    |
| 254 | Chiliz                               | chz                     |
| 255 | Orchid                               | oxt                     |
| 256 | LCX                                  | lcx                     |
| 257 | Nahmii                               | nii                     |
| 258 | USDK                                 | usdk                    |
| 259 | WazirX                               | wrx                     |
| 260 | Band Protocol                        | band                    |
| 261 | Kusama                               | ksm                     |
| 262 | Hive                                 | hive                    |
| 263 | Energi                               | nrg                     |
| 264 | GateToken                            | gt                      |
| 265 | Kava                                 | kava                    |
| 266 | MX TOKEN                             | mx                      |
| 267 | Arweave                              | ar                      |
| 268 | Compound                             | comp                    |
| 269 | NuCypher                             | nu                      |
| 270 | Keep Network                         | keep                    |
| 271 | Origin Protocol                      | ogn                     |
| 272 | Render Token                         | rndr                    |
| 273 | Cocos-BCX                            | cocos                   |
| 274 | DREP                                 | drep                    |
| 275 | LTO Network                          | lto                     |
| 276 | COTI                                 | coti                    |
| 277 | Solana                               | sol                     |
| 278 | Cartesi                              | ctsi                    |
| 279 | Chromia                              | chr                     |
| 280 | StormX                               | stmx                    |
| 281 | BIDR                                 | bidr                    |
| 282 | Polkadot                             | dot                     |
| 283 | Celo                                 | celo                    |
| 284 | Filecoin                             | fil                     |
| 285 | sUSD                                 | susd                    |
| 286 | Travala.com                          | ava                     |
| 287 | Wirex Token                          | wxt                     |
| 288 | Syntropy                             | noia                    |
| 289 | Akropolis                            | akro                    |
| 290 | Ampleforth                           | ampl                    |
| 291 | SENSO                                | senso                   |
| 292 | DigitalBits                          | xdb                     |
| 293 | Sylo                                 | sylo                    |
| 294 | Neutrino USD                         | usdn                    |
| 295 | KardiaChain                          | kai                     |
| 296 | Energy Web Token                     | ewt                     |
| 297 | yearn.finance                        | yfi                     |
| 298 | UMA                                  | uma                     |
| 299 | renBTC                               | renbtc                  |
| 300 | Avalanche                            | avax                    |
| 301 | BOSagora                             | boa                     |
| 302 | JUST                                 | jst                     |
| 303 | Bifrost                              | bfc                     |
| 304 | DIA                                  | dia                     |
| 305 | ForTube                              | for                     |
| 306 | Green Satoshi Token                  | gst                     |
| 307 | Helium                               | hnt                     |
| 308 | IDEX                                 | idex                    |
| 309 | Kadena                               | kda                     |
| 310 | Klaytn                               | klay                    |
| 311 | mStable Governance Token: Meta (MTA) | mta                     |
| 312 | NEST Protocol                        | nest                    |
| 313 | MANTRA                               | om                      |
| 314 | Orion Protocol                       | orn                     |
| 315 | Prom                                 | prom                    |
| 316 | PARSIQ                               | prq                     |
| 317 | Rocket Pool                          | rpl                     |
| 318 | Reserve                              | rsv                     |
| 319 | THORChain                            | rune                    |
| 320 | ShareToken                           | shr                     |
| 321 | Serum                                | srm                     |
| 322 | SUKU                                 | suku                    |
| 323 | tBTC                                 | tbtc                    |
| 324 | Tellor                               | trb                     |
| 325 | BiLira                               | tryb                    |
| 326 | Curve DAO Token                      | crv                     |
| 327 | Velas                                | vlx                     |
| 328 | Wrapped NXM                          | wnxm                    |
| 329 | DFI.Money                            | yfii                    |
| 330 | Balancer                             | bal                     |
| 331 | SushiSwap                            | sushi                   |
| 332 | Swerve                               | swrv                    |
| 333 | Cream Finance                        | cream                   |
| 334 | Sun Token                            | sun                     |
| 335 | MultiversX                           | egld                    |
| 336 | Uniswap                              | uni                     |
| 337 | Alchemy Pay                          | ach                     |
| 338 | Aleph.im                             | aleph                   |
| 339 | Bella Protocol                       | bel                     |
| 340 | Frontier                             | front                   |
| 341 | Insight Protocol                     | inx                     |
| 342 | Klever                               | klv                     |
| 343 | TrustSwap                            | swap                    |
| 344 | Toncoin                              | ton                     |
| 345 | TerraUSD                             | ust                     |
| 346 | Handshake                            | hns                     |
| 347 | Ultra                                | uos                     |
| 348 | BakeryToken                          | bake                    |
| 349 | Aavegotchi                           | ghst                    |
| 350 | Rarible                              | rari                    |
| 351 | Velo                                 | velo                    |
| 352 | Aave                                 | aave                    |
| 353 | PancakeSwap                          | cake                    |
| 354 | DODO                                 | dodo                    |
| 355 | Harvest Finance                      | farm                    |
| 356 | Polkastarter                         | pols                    |
| 357 | Secret                               | scrt                    |
| 358 | Venus                                | xvs                     |
| 359 | Core                                 | core                    |
| 360 | Dego Finance                         | dego                    |
| 361 | Ergo                                 | erg                     |
| 362 | MATH                                 | math                    |
| 363 | NEAR Protocol                        | near                    |
| 364 | DeFiChain                            | dfi                     |
| 365 | Audius                               | audio                   |
| 366 | Axie Infinity                        | axs                     |
| 367 | Conflux                              | cfx                     |
| 368 | Shentu                               | ctk                     |
| 369 | Celo Dollar                          | cusd                    |
| 370 | Injective                            | inj                     |
| 371 | Keep3rV1                             | kp3r                    |
| 372 | Oasys                                | oas                     |
| 373 | Smooth Love Potion                   | slp                     |
| 374 | StaFi                                | fis                     |
| 375 | Flamingo                             | flm                     |
| 376 | Oasis Network                        | rose                    |
| 377 | TrueFi                               | tru                     |
| 378 | Unifi Protocol DAO                   | unfi                    |
| 379 | Golem                                | glm                     |
| 380 | Hegic                                | hegic                   |
| 381 | API3                                 | api3                    |
| 382 | Badger DAO                           | badger                  |
| 383 | Firo                                 | firo                    |
| 384 | MobileCoin                           | mob                     |
| 385 | Synapse                              | syn                     |
| 386 | Virtua                               | tvk                     |
| 387 | The Graph                            | grt                     |
| 388 | 1inch                                | 1inch                   |
| 389 | Alpha Venture DAO                    | alpha                   |
| 390 | OctoFi                               | octo                    |
| 391 | saffron.finance                      | sfi                     |
| 392 | Perpetual Protocol                   | perp                    |
| 393 | AS Roma Fan Token                    | asr                     |
| 394 | BarnBridge                           | bond                    |
| 395 | CUDOS                                | cudos                   |
| 396 | DeXe                                 | dexe                    |
| 397 | Bonfida                              | fida                    |
| 398 | Frax                                 | frax                    |
| 399 | Frax Share                           | fxs                     |
| 400 | Juventus Fan Token                   | juv                     |
| 401 | Linear                               | lina                    |
| 402 | Mdex                                 | mdx                     |
| 403 | Mirror Protocol                      | mir                     |
| 404 | OG Fan Token                         | og                      |
| 405 | Marlin                               | pond                    |
| 406 | Paris Saint-Germain Fan Token        | psg                     |
| 407 | REVV                                 | revv                    |
| 408 | Rook                                 | rook                    |
| 409 | Trust Wallet Token                   | twt                     |
| 410 | ZKSpace                              | zks                     |
| 411 | Flow                                 | flow                    |
| 412 | Stratis                              | strax                   |
| 413 | Reef                                 | reef                    |
| 414 | Bitcoin Standard Hashrate Token      | btcst                   |
| 415 | The Sandbox                          | sand                    |
| 416 | SafePal                              | sfp                     |
| 417 | SKALE                                | skl                     |
| 418 | Phala Network                        | pha                     |
| 419 | WOO Network                          | woo                     |
| 420 | Raydium                              | ray                     |
| 421 | AC Milan Fan Token                   | acm                     |
| 422 | Akash Network                        | akt                     |
| 423 | Alchemix                             | alcx                    |
| 424 | DAO Maker                            | dao                     |
| 425 | DerivaDAO                            | ddx                     |
| 426 | Dypius                               | dyp                     |
| 427 | Inverse Finance                      | inv                     |
| 428 | MAPS                                 | maps                    |
| 429 | Mask Network                         | mask                    |
| 430 | NFTX                                 | nftx                    |
| 431 | Prosper                              | pros                    |
| 432 | BENQI                                | qi                      |
| 433 | Radicle                              | rad                     |
| 434 | Rally                                | rly                     |
| 435 | SuperVerse                           | super                   |
| 436 | Tornado Cash                         | torn                    |
| 437 | AIOZ Network                         | aioz                    |
| 438 | Alpaca Finance                       | alpaca                  |
| 439 | Anchor Protocol                      | anc                     |
| 440 | Boson Protocol                       | boson                   |
| 441 | Convergence                          | conv                    |
| 442 | Fei USD                              | fei                     |
| 443 | Fire Protocol                        | fire                    |
| 444 | Flux                                 | flux                    |
| 445 | Franklin                             | fly                     |
| 446 | Galxe                                | gal                     |
| 447 | Illuvium                             | ilv                     |
| 448 | JasmyCoin                            | jasmy                   |
| 449 | Polkacity                            | polc                    |
| 450 | Rai Reflex Index                     | rai                     |
| 451 | Strike                               | strk                    |
| 452 | Alien Worlds                         | tlm                     |
| 453 | Tribe                                | tribe                   |
| 454 | Symbol                               | xym                     |
| 455 | Internet Computer                    | icp                     |
| 456 | Shiba Inu                            | shib                    |
| 457 | FC Barcelona Fan Token               | bar                     |
| 458 | SpookySwap                           | boo                     |
| 459 | Somnium Space Cubes                  | cube                    |
| 460 | Dogelon Mars                         | elon                    |
| 461 | Ampleforth Governance Token          | forth                   |
| 462 | Gitcoin                              | gtc                     |
| 463 | Kishu Inu                            | kishu                   |
| 464 | Liquity                              | lqty                    |
| 465 | Media Network                        | media                   |
| 466 | APENFT                               | nft                     |
| 467 | QuickSwap                            | quick                   |
| 468 | Songbird                             | sgb                     |
| 469 | Step Finance                         | step                    |
| 470 | Persistence                          | xprt                    |
| 471 | Liquity USD                          | lusd                    |
| 472 | Lido DAO                             | ldo                     |
| 473 | Baby Doge Coin                       | babydoge                |
| 474 | BitDAO                               | bit                     |
| 475 | Coin98                               | c98                     |
| 476 | Celo Euro                            | ceur                    |
| 477 | Tranchess                            | chess                   |
| 478 | CLV                                  | clv                     |
| 479 | Covalent                             | cqt                     |
| 480 | Convex Finance                       | cvx                     |
| 481 | Dvision Network                      | dvi                     |
| 482 | Gala                                 | gala                    |
| 483 | Goldfinch                            | gfi                     |
| 484 | Metahero                             | hero                    |
| 485 | Karura                               | kar                     |
| 486 | MOBOX                                | mbox                    |
| 487 | Moonriver                            | movr                    |
| 488 | PlayDapp                             | pla                     |
| 489 | Qredo                                | qrdo                    |
| 490 | RadioCaca                            | raca                    |
| 491 | SuperRare                            | rare                    |
| 492 | Saitama                              | saitama                 |
| 493 | Shiden Network                       | sdn                     |
| 494 | SOMESING                             | ssx                     |
| 495 | StarLink                             | starl                   |
| 496 | Wrapped NCG                          | wncg                    |
| 497 | XCAD Network                         | xcad                    |
| 498 | eCash                                | xec                     |
| 499 | Yield Guild Games                    | ygg                     |
| 500 | Pax Dollar                           | usdp                    |
| 501 | My Neighbor Alice                    | alice                   |
| 502 | ASD                                  | asd                     |
| 503 | XDC Network                          | xdc                     |
| 504 | Mina                                 | mina                    |
| 505 | Adventure Gold                       | agld                    |
| 506 | Star Atlas DAO                       | polis                   |
| 507 | dYdX                                 | dydx                    |
| 508 | Spell Token                          | spell                   |
| 509 | Angle                                | angle                   |
| 510 | Ariva                                | arv                     |
| 511 | Assemble Protocol                    | asm                     |
| 512 | AstroSwap                            | astro                   |
| 513 | Star Atlas                           | atlas                   |
| 514 | Beta Finance                         | beta                    |
| 515 | BinaryX                              | bnx                     |
| 516 | Braintrust                           | btrst                   |
| 517 | Manchester City Fan Token            | city                    |
| 518 | Clearpool                            | cpool                   |
| 519 | FLOKI                                | floki                   |
| 520 | Gods Unchained                       | gods                    |
| 521 | Highstreet                           | high                    |
| 522 | JOE                                  | joe                     |
| 523 | S.S. Lazio Fan Token                 | lazio                   |
| 524 | Moss Carbon Credit                   | mco2                    |
| 525 | Marinade Staked SOL                  | msol                    |
| 526 | Olympus                              | ohm                     |
| 527 | Orca                                 | orca                    |
| 528 | PackagePortal                        | port                    |
| 529 | Ribbon Finance                       | rbn                     |
| 530 | Samoyedcoin                          | samo                    |
| 531 | Saber                                | sbr                     |
| 532 | ssv.network                          | ssv                     |
| 533 | Strips Finance                       | strp                    |
| 534 | Tokemak                              | toke                    |
| 535 | VEMP                                 | vemp                    |
| 536 | Wrapped Centrifuge                   | wcfg                    |
| 537 | Mines of Dalarnia                    | dar                     |
| 538 | Ethereum Name Service                | ens                     |
| 539 | GM Wagmi                             | gm                      |
| 540 | GYEN                                 | gyen                    |
| 541 | ImmutableX                           | imx                     |
| 542 | KOK                                  | kok                     |
| 543 | Magic Internet Money                 | mim                     |
| 544 | FC Porto Fan Token                   | porto                   |
| 545 | ParaSwap                             | psp                     |
| 546 | Aurora                               | aurora                  |
| 547 | Binance Beacon ETH                   | beth                    |
| 548 | Boba Network                         | boba                    |
| 549 | Everscale                            | ever                    |
| 550 | Merit Circle                         | mc                      |
| 551 | Maple                                | mpl                     |
| 552 | ONSTON                               | onston                  |
| 553 | ConstitutionDAO                      | people                  |
| 554 | Santos FC Fan Token                  | santos                  |
| 555 | BitTorrent (new)                     | bttc                    |
| 556 | Vulcan Forged PYR                    | pyr                     |
| 557 | Tether EURt                          | eurt                    |
| 558 | Casper                               | cspr                    |
| 559 | Automata Network                     | ata                     |
| 560 | ApeCoin                              | ape                     |
| 561 | LooksRare                            | looks                   |
| 562 | Moonbeam                             | glmr                    |
| 563 | Tulip Protocol                       | tulip                   |
| 564 | Osmosis                              | osmo                    |
| 565 | STEPN                                | gmt                     |
| 566 | Biconomy                             | bico                    |
| 567 | Alpine F1 Team Fan Token             | alpine                  |
| 568 | Astar                                | astr                    |
| 569 | Biswap                               | bsw                     |
| 570 | PowerPool                            | cvp                     |
| 571 | Gari Network                         | gari                    |
| 572 | Index Cooperative                    | index                   |
| 573 | Multichain                           | multi                   |
| 574 | Optimism                             | op                      |
| 575 | REI Network                          | rei                     |
| 576 | SHPING                               | shping                  |
| 577 | Stargate Finance                     | stg                     |
| 578 | Voxies                               | voxel                   |
| 579 | Zebec Protocol                       | zbc                     |
| 580 | Acala Token                          | aca                     |
| 581 | Bounce Governance Token              | auction                 |
| 582 | Eden                                 | eden                    |
| 583 | Ellipsis                             | epx                     |
| 584 | Shapeshift FOX Token                 | fox                     |
| 585 | League of Kingdoms Arena             | loka                    |
| 586 | MetisDAO                             | metis                   |
| 587 | Ooki Protocol                        | ooki                    |
| 588 | Pundi X                              | pundix                  |
| 589 | Threshold                            | t                       |
| 590 | Voyager Token                        | vgx                     |
| 591 | USDD                                 | usdd                    |
| 592 | Chia                                 | xch                     |
| 593 | Euro Coin                            | euroc                   |
| 594 | Beefy Finance                        | bifi\_beef              |
| 595 | Staked Ether Lido                    | steth                   |
| 596 | poundtoken                           | gbpt                    |
| 597 | Terra 2.0                            | luna2                   |
| 598 | Nano                                 | xno                     |
| 599 | Onyxcoin                             | xcn                     |
| 600 | NYM                                  | nym                     |
| 601 | Efinity Token                        | efi                     |
| 602 | WEMIX                                | wemix                   |
| 603 | Step App                             | fitfi                   |
| 604 | Sweat Economy                        | sweat                   |
| 605 | FirmaChain                           | fct2                    |
| 606 | Tokenlon Network Token               | lon                     |
| 607 | pSTAKE Finance                       | pstake                  |
| 608 | Vesper                               | vsp                     |
| 609 | GuildFi                              | gf                      |
| 610 | LeverFi                              | lever                   |
| 611 | Euler                                | eul                     |
| 612 | EthereumPoW                          | ethw                    |
| 613 | Crabada                              | cra                     |
| 614 | Reflexer Ungovernance Token          | flx                     |
| 615 | JUNO                                 | juno                    |
| 616 | Altered State Token                  | asto                    |
| 617 | BreederDAO                           | breed                   |
| 618 | Saddle                               | sdl                     |
| 619 | Arsenal Fan Token                    | afc                     |
| 620 | Aptos                                | apt                     |
| 621 | Axelar                               | axl                     |
| 622 | Bitcicoin                            | bitci                   |
| 623 | Cult DAO                             | cult                    |
| 624 | Forta                                | fort                    |
| 625 | GMX                                  | gmx                     |
| 626 | Hashflow                             | hft                     |
| 627 | Polymesh                             | polyx                   |
| 628 | Agoric                               | bld                     |
| 629 | Avocado DAO Token                    | avg                     |
| 630 | ECOx                                 | ecox                    |
| 631 | Evmos                                | evmos                   |
| 632 | PathDAO                              | path                    |
| 633 | Stader                               | sd                      |
| 634 | Tribal Token                         | tribl                   |
| 635 | Bonk                                 | bonk                    |
| 636 | Hooked Protocol                      | hook                    |
| 637 | Dogechain                            | dc                      |
| 638 | Flare                                | flr                     |
| 639 | Hifi Finance                         | hifi                    |
| 640 | DeFi Kingdoms                        | jewel                   |
| 641 | Dopex                                | dpx                     |
| 642 | MAGIC                                | magic                   |

## Appendix B

The following table lists the weights applied to each one-minute time interval described in the Hourly Reference Rates Methodology section.

| Time Interval | Weight   |
| ------------- | -------- |
| 0             | 0.000000 |
| 1             | 0.000526 |
| 2             | 0.001052 |
| 3             | 0.001578 |
| 4             | 0.002104 |
| 5             | 0.002630 |
| 6             | 0.003156 |
| 7             | 0.003682 |
| 8             | 0.004208 |
| 9             | 0.004734 |
| 10            | 0.005260 |
| 11            | 0.005786 |
| 12            | 0.006312 |
| 13            | 0.006838 |
| 14            | 0.007364 |
| 15            | 0.007890 |
| 16            | 0.008416 |
| 17            | 0.008942 |
| 18            | 0.009468 |
| 19            | 0.009994 |
| 20            | 0.010520 |
| 21            | 0.011046 |
| 22            | 0.011572 |
| 23            | 0.012098 |
| 24            | 0.012624 |
| 25            | 0.013150 |
| 26            | 0.013676 |
| 27            | 0.014202 |
| 28            | 0.014728 |
| 29            | 0.015254 |
| 30            | 0.015780 |
| 31            | 0.016306 |
| 32            | 0.016832 |
| 33            | 0.017358 |
| 34            | 0.017884 |
| 35            | 0.018410 |
| 36            | 0.018936 |
| 37            | 0.019462 |
| 38            | 0.019988 |
| 39            | 0.020514 |
| 40            | 0.021040 |
| 41            | 0.021566 |
| 42            | 0.022092 |
| 43            | 0.022618 |
| 44            | 0.023144 |
| 45            | 0.023670 |
| 46            | 0.024196 |
| 47            | 0.024722 |
| 48            | 0.025248 |
| 49            | 0.025774 |
| 50            | 0.026300 |
| 51            | 0.026826 |
| 52            | 0.027352 |
| 53            | 0.027878 |
| 54            | 0.028404 |
| 55            | 0.028930 |
| 56            | 0.029456 |
| 57            | 0.029982 |
| 58            | 0.030508 |
| 59            | 0.050000 |
| 60            | 0.050000 |

## Change Log

1. **Version 1.0 on March 16, 2023**: Initial publication of Coin Metrics Pricing Methodology. Previous versions of this document were contained in our Market Selection Framework, Hourly Reference Rates Methodology, Real-Time Reference Rates Methodology, and Principal Mark Price Methodology. Those four documents are now consolidated into the Coin Metrics Pricing Methodology. The coverage universe is expanded to include the following assets: `bonk`, `cusd`, `cra`, `jewel`, `apt`, `asto`, `aurora`, `avg`, `axl`, `bld`, `breed`, `ceur`, `cpool`, `ecox`, `evmos`, `flx`, `fly`, `fort`, `gf`, `index`, `indi`, `inx`, `multi`, `path`, `rpl`, `rsv`, `sd`, `sdl`, `tbtc`, `tribl`, `gmx`, `bifi_beef`, `dpx`, `boo`, `beth`, `magic`, `juno`, `port`, `phb`, `kishu`, `lever`, `flr`, `hft`, `porto`, `polyx`, `lazio`, `atm`, `acm`, `xcad`, `ssv`, `pros`, `rei`, `qlc`, `dego`, `vite`, `firo`, `iq`, `bar`, `og`, `hifi`, `asr`, `dyp`, `time`, `sylo`, `polc`, `bitci`, `fct2`, `onston`, `vsp`, `afc`, `bsw`, `epx`, `xno`, `dexe`, `core`, `vemp`, `cult`, `saitama`, `ever`, `babydoge`, `dc`, `kar`, `fsn`, `hero`, `oas`, `hook`, `cocos`. The following assets are terminated from the coverage universe: `mft`, `hpt`, `hxro`, `usdn`, `aion`.
2. **Coin Metrics Real-Time Reference Rates Methodology Version 0.15 on February 9, 2023**: Added a 200 milliseconds publication frequency.
3. **Coin Metrics Hourly Reference Rates Methodology Version 2.13 and Coin Metrics Real-Time Reference Rates Methodology Version 0.14 on September 21, 2022**: The coverage universe is expanded to include the following assets: `loka`, `mc`, `polis`, `sgb`, `steth`, `frax`, `rai`, `lusd` , `dfi`, `gbpt`, `ooki`, `fis`, `nest`, `drep`, `math`, `aleph`, `media`, `luna2`, `t`, `ethw`, `bttc`, `vra`, `swftc`, `raca`, `pyr`, `mbox`, `sweat`, `fitfi`, `qrdo`, `wemix`, `zbc`, `psg`, `voxel`, `chess`, `prq`, `gari`, `nym`, `arv`, `cudos`, `efi`, `for`, `juv`, `cvp`, `mbl`, `auto`, `eden`, `xcn`, `kai`, `velo`, `akt`, `berry`, `klv`, `kok`, `senso`, `floki`, `sdn`, `alpine`, `step`, `eurt`, `bfc`, `toke`, `shping`, `oxy`, `ssx`, `lit`, `conv`. The publication of reference rates is terminated for the following assets: `ramp`, `grs`, `ppt`, `nav`, `itc`, `qc`, `meta`, `cope`, `zb`. Minor changes to internal audit section.
4. **Coin Metrics Hourly Reference Rates Methodology Version 2.12 and Coin Metrics Real-Time Reference Rates Methodology Version 0.13 on July 1, 2022**: The coverage universe is expanded to include the following assets: `fei`, `op`, `usdd`, `xch`, `gmt`, `bico`, `ctk`, `flm`, `sfp`, `starl`, `glmr`, `tulip`, `astro`, `sfi`, `gst`, `mob`, `bit`, `vgx`, `auction`, `pundix`, `stg`, `ata`, `bel`, `dar`, `gal`, `astr`, `cqt`, `cspr`, `metis`, `boba`, `twt`, `aca`, `dao`, `xprt`, `cube`. The publication of reference rates is terminated for the following assets: `gxs`, `dgtx`, `wluna`, `dgd`, `foam`, `csp`, `cnn`, `bft`.
5. **Market Selection Framework Version 1.0.2 on February 15, 2022**: The selection algorithm was modified so that any market with volume, measured in U.S. dollars over the past 90 days, of less than 5 percent of the volume of the selected market with the largest volume is excluded.
6. **Coin Metrics Hourly Reference Rates Methodology Version 2.11 and Coin Metrics Real-Time Reference Rates Methodology Version 0.12 on February 15, 2022**: The coverage universe is expanded to include the following assets: `xec`, `kda`, `mina`, `xdc`, `elon`, `flux`, `movr`, `ceek`, `win_wink`, `dvi`, `dusk`, `asd`, `gala`, `spell`, `ens`, `tru`, `alcx`, `clv`, `imx`, `agld`, `jasmy`, `farm`, `alice`, `chr`, `dydx`, `tlm`, `mdt`, `gtc`, `sun`, `c98`, `people`, `lina`, `rndr`, `ach`, `super`, `mask`, `quick`, `arpa`, `qi`, `idex`, `rad`, `bond`, `mir`, `joe`, `gods`, `front`, `pla`, `orn`, `ramp`, `rgt`, `fida`, `forth`, `tribe`, `wluna`, `coval`, `rbn`, `lcx`, `asm`, `ddx`, `suku`, `krl`, `rari`, `mco2`, `gyen`, `btrst`, `api3`, `rly`, `wcfg`, `musd`, `ilv`, `atlas`, `usdp`, `joe`, `ldo`, `cvx`, `fxs`, `kp3r`, `alpaca`, `bnx`, `boson`, `dora`, `ghst`, `nft`, `ohm`, `om`, `pond`, `rare`, `revv`, `stpt`, `torn`, `tvk`, `wncg`, `xym`, `ygg`. The publication of reference rates is terminated for the following assets: `hedg`, `eurs`, `bzrx`, `poa`, `wpr`, `dmg`, `cdt`, `phx`, `appc`, `btt`, `idrt`, `rdn`, `via`, `evx`. The section “Data Inputs”, subsections “Other Cryptocurrencies Excluding Stablecoins” and “Stablecoins”, was modified to consider markets quoted in USD Coin or Tether to serve as constituent markets. The constituent markets for all assets in the coverage universe are updated. The constituent markets for all assets in the coverage universe are updated.
7. **Coin Metrics Hourly Reference Rates Methodology Version 2.10 and Coin Metrics Real-Time Reference Rates Methodology Version 0.11 on September 28, 2021**: The coverage universe is expanded to include the following assets: `amp`, `axs`, `shib`, `audio`, `bake`, `med`, `dag`, `slp`, `xdb`. The publication of reference rates is terminated for the following assets: `agi` ,`btmx`, `dgx`, `ethos`, `mco`, `sngls`, `cpay`, `eng`, `lun`, `pnt`. The constituent markets for all assets in the coverage universe are updated.
8. **Coin Metrics Hourly Reference Rates Methodology Version 2.9 and Coin Metrics Real-Time Reference Rates Methodology Version 0.10 on May 27, 2021**: The coverage universe is expanded to include the following assets: `icp`, `cope`, `maps`, `btcst`, `ctsi`, `erg`, `woo`, `prom`, `strax`, `usdn`, `cfx`, `mdx`, `nkn`, `sand`, `fx`, `pha`. The publication of reference rates is terminated for the following assets: `tnt`, `npxs`, `zar`. The constituent markets for all assets in the coverage universe are updated.
9. **Coin Metrics Hourly Reference Rates Methodology Version 2.8 and Coin Metrics Real-Time Reference Rates Methodology Version 0.9 on April 25, 2021**: The methodology was modified to add fiat currencies to the coverage universe. The coverage universe is expanded to include the following assets: `eur`, `krw`, `gbp`, `jpy`, `aud`, `try`, `brl`, `rub`, `sgd`, `bidr`, `ngn`, `cad`, `chf`, `zar`, `idrt`, `hkd`, `uah`, `qc`, `klay`, `cake`, `btmx`, `flow`, `zks`, `stmx`, `skl`, `reef`, `dodo`, `coti`, `bora`, `cream`, `ray`, `tryb`, `rook`. The publication of reference rates is terminated for the following assets: `xzc`, `bcpt`, `yamv2`, `xns`, `tmtg`, `kp3r`.
10. **Coin Metrics Hourly Reference Rates Methodology Version 2.7 and Coin Metrics Real-Time Reference Rates Methodology Version 0.8 on February 23, 2021**: The coverage universe is expanded to include the following assets: `1inch`, `alpha`, `octo`, `perp`, `scrt`, `grt`, `keep`, `xvs`, `nu`, `tel`, `badger`.
11. **Coin Metrics Hourly Reference Rates Methodology Version 2.6 and Coin Metrics Real-Time Reference Rates Methodology Version 0.7 on January 26, 2021**: The coverage universe is expanded to include the following assets: `susd`, `pols`, `ust`, `lto`, `swap`, `nim,` `lbc`, `mta`, `kp3r`, `glm`, `near`, `noia`, `rose`, `inj`. The publication of reference rates is terminated for the following assets: `gnt`, `fxc`, `bht`, `cmct`, `strat`, `loki`. The constituent markets for all assets in the coverage universe are updated.
12. **Coin Metrics Hourly Reference Rates Methodology Version 2.5 and Coin Metrics Real-Time Reference Rates Methodology Version 0.6 on November 5, 2020**: The coverage universe is expanded to include the following assets: `akro`, `ampl`, `ar`, `bal`, `bzrx`, `celo`, `comp`, `crv`, `csp`, `dmg`, `dot`, `foam`, `kin`, `oxt`, `rune`, `sol`, `srm`, `vtho`, `wbtc`, `wnxm`, `xhv`, `xyo`, `yamv2`, `yfi`, `yfii`, `uma`, `ewt`, `rev`, `rsr`, `avax`, `tmtg`, `jst`, `hnt`, `trac`, `vlx`, `mxc`, `fet`, `aoa`, `iris`, `pnk`, `mln`, `shr`, `uqc`, `one_harmony`, `trb`, `ogn`, `ava`, `loki`, `hxro`, `wxt`, `cpay`, `fil`, `uni`, `swrv`, `sushi`, `aave`, `egld`, `hns`, `dia`, `boa`, `uos`, `ctc`, `renbtc`. The publication of reference rates is terminated for the following assets: `arn`, `pma`, `erd`, `man`, `iq`, `lend`. The Market Selection Framework was amended such that extremely low volume markets are less likely to be selected as a constituent market if higher volume markets of similar quality are available. The constituent markets for all assets in the coverage universe are updated.
13. **Market Selection Framework Version 1.0.1 on November 5, 2020**: The selection algorithm was modified so that any market with volume, measured in U.S. dollars over the past 90 days, of less than 1 percent of the volume of the selected market with the largest volume is excluded.
14. **Coin Metrics Hourly Reference Rates Methodology Version 2.4 on July 29, 2020 and Coin Metrics Real-Time Reference Rates Methodology Version 0.5 on July 29, 2020**: The coverage universe is expanded to include the following assets: `wrx`, `band`, `ksm`, `usdk`, `snx`, `stx`, `fxc`, `kcs`, `hive`, `nrg`, `cel`, `ubt`, `chsb`, `crpt`, `bht`, `cvt`, `data`, `eurs`, `xns`, `gt`, `dgtx`, `kava`, `tt`, `sxp`, `mx`, `ocean`, `erd`, `lpt`. The publication of reference rates is terminated for the following assets: `storm`, `gto`. A revision policy was amended. The constituent markets for all assets in the coverage universe are updated.
15. **Coin Metrics Hourly Reference Rates Methodology Version 2.3 on February 27, 2020 and Coin Metrics Real-Time Reference Rates Methodology Version 0.4 on February 27, 2020**: The coverage universe is expanded to include the following assets: `xaut`, `paxg`, `husd`, `dgx`, `busd`, `ftt`, `hedg`, `okb`, `zb`, `hbar`, `ckb`, `mof`, `vsys`, `cennz`, `luna`, `chz`, `seele`, `dx`, `matic`, `abbc`, `rif`, `tomo`, `hpt`, and `ant`.
16. **Coin Metrics Hourly Reference Rates Methodology Version 2.2 on February 6, 2020 and Coin Metrics Real-Time Reference Rates Methodology Version 0.3 on February 6, 2020**: The constituent markets for all assets in the coverage universe are updated. The coverage universe is adjusted to remove the following assets: `box`, `cosm`, `fsn`, `medx`, `pst`, and `ttc_protocol`. The coverage universe was expanded to include Dai and the previous asset with this name was renamed to Sai to appropriately reflect MakerDAO’s transition from Single-Collateral Dai (Sai) to Multi-Collateral Dai (Dai).
17. **Coin Metrics Hourly Reference Rates Methodology Version 2.1 on December 9, 2019 and Coin Metrics Real-Time Reference Rates Methodology Version 0.2 on December 9, 2019**: The coverage universe is expanded to include the following assets: `algo` and `beam`. Updated calculation methodology to include price inverse variance weighting to reduce the impact of outliers.
18. **Coin Metrics Real-Time Reference Rates Methodology Version 0.1 on August 30, 2019**: Initial publication of Real-Time Reference Rates Methodology.
19. **Coin Metrics Hourly Reference Rates Methodology Version 2.0 on July 8, 2019**: Increased publication times from once daily at midnight UTC to once hourly. Changed human oversight from once daily at midnight UTC to once daily at 16:00 New York time.
20. **Coin Metrics Hourly Reference Rates Methodology Version 1.2 on June 13, 2019**: The coverage universe is expanded to include the following assets: `gno`, `hot_holo`, `maid`, `nuls`, `qkc`, `rdd`, `rvn`, `zen`, and `mona`.
21. **Coin Metrics Hourly Reference Rates Methodology Version 1.1 on May 30, 2019**: Updated data contingency rules. If no observable transactions from constituent markets occur during a one-minute time interval, the next one-minute time interval’s volume-weighted median price is used instead of the previous. This contingency rule is applied recursively.
22. **Coin Metrics Hourly Reference Rates Methodology Version 1.0 on May 13, 2019**: Initial publication of Reference Rates Methodology.
23. **Market Selection Framework Version 1.0.0 on May 13, 2019**: Initial publication of Market Selection Framework.
