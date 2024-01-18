# CMBI Market Selection Framework

### Introduction

Coin Metrics evaluates markets traded on digital asset exchanges as potential input data sources for the Coin Metrics Prices using a Market Selection Framework. The framework consists of a fully-systematized process for evaluating markets along a wide set of criteria to determine if the data source reflects trading activity in a transparent and representative manner. In this framework, a market refers to a specific traded asset pair on a specific exchange. Only spot markets are considered. It produces a unique set of candidate selected markets for each index in the coverage universe.

The Index team evaluates new markets for inclusion as a selected market and assesses already selected markets using the Market Selection Framework on a quarterly basis and during interim periods if market conditions warrant. Such market conditions include, but are not limited to, material changes in an exchange's solvency risk, material changes in the degree of free capital flows in and out of an exchange, the presence of long-lasting price differences from other exchanges, and during times of market stress.

Markets that are approved are added to a list of constituent markets (the "Constituent Markets"). A separate list of Constituent Markets is maintained for each of the indexesin the coverage universe.

A candidate market can be nominated for inclusion and an existing constituent market can be nominated for exclusion by any member of the public. Public nominations for inclusion or exclusion of a market can be submitted in writing to `cmbi-support@coinmetrics.io`.

The data inputs for the calculation of the Coin Metrics Prices are observable transactions in a constituent market where the underlying asset is traded.

### Feature Descriptions

The Market Selection Framework consists of 45 features, 30 of which are in active use. Features represent individual measurable properties that provide an indication of the suitability for a market to serve as an input data source, which are combined to form a market rating.

Some of the features described in this section are indicator variables that encode qualitative information about a market or exchange. These indicator variables can require a degree of subjectivity in determining whether a market or exchange meets a certain criteria. In such cases, the indicator variable is set to true only if an unambiguous source is found that provides sufficient information to make an evaluation. In the absence of such a source, the indicator variable is set to false.

#### Technology

An assessment of whether the technology infrastructure of the market's exchange provides sufficient availability and reliability for input data collection. Evaluates whether the exchange offers a REST API or WebSocket feed for data collection. Evaluates the performance of the API in terms of reliability.

1. **`has_rest_api`**: An indicator variable for the existence of a REST API.
2. **`has_websocket_feed`**: An indicator variable for the existence of a WebSocket feed.
3. **`has_historical_trade_data`**: An indicator variable for whether the exchange offers historical trade data via its API.
4. **`has_real_time_trade_data`**: An indicator variable for whether the exchange offers real-time trade data via its API.
5. **`has_real_time_order_book_data`**: An indicator variable for whether the exchange offers real-time order book data via its API.
6. **`api_downtime_incidents`**: A feature that represents the stability of an API.

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

An assessment of the market's exchange with respect to its business model, including its fee structure and asset listing standards.

1. **`has_fiat_markets`**: An indicator variable that indicates whether the exchange has markets where the quote currency is a fiat currency.
2. **`has_fees`**: An indicator variable that indicates whether the exchange charges trading fees as a percentage of the trade size. Exchanges that charge zero fees or charge fees indirectly through a transaction mining model are determined to not charge fees.
3. **`has_listing_standards`**: An indicator variable that indicates whether the exchange has publicly disclosed a framework for deciding which assets to list.
4. **`has_usa_hq`**: An indicator variable for whether the company's headquarters are domiciled in the United States.

#### Data Availability

An assessment of the available data the market's exchange offers for the given digital asset, including the amount of historical data available for a market and the quoted currency of the market.

1. **`market_days_history`**: The number of days of historical data for the market.
2. **`market_quote_modifier`**: An optional modifier to give greater weight to a certain quote currency. Currently all quote currencies have equal weight.

#### Price

An assessment of the quality of the market's price data, including testing for the occurrence of price outliers and impactful price deviations from other markets, and implementing tests that determine whether the exchange's markets function as active markets in the underlying digital asset and are anchored by observable transactions entered into at arm's length between buyers and sellers.

In this section, prices are compared to the global median price. The global median price is defined as the median price of all markets in which the digital asset is the base currency from the following list of exchanges: `["Coinbase", "Poloniex", "Bittrex", "Gemini", "Kraken", "Binance", "Bitstamp", "itBit"]`. This list of exchanges was selected by first calculating the market ratings for each market but without the price-related features below. The median market rating was then calculated for each exchange and the top 8 exchanges were selected.

1. **`market_open_mape_all`**: The mean absolute percentage error of the market's daily open price compared to the global median's daily open price over the last 90 days.
2. **`market_close_mape_all`**: The mean absolute percentage error of the market's daily close price compared to the global median's daily close price over the last 90 days.
3. **`market_low_mape_all`**: The mean absolute percentage error of the market's daily low price compared to the global median's daily low price over the last 90 days.
4. **`market_high_mape_all`**: The mean absolute percentage error of the market's daily high price compared to the global median's daily high price over the last 90 days.
5. **`market_open_mape_trimmed`**: The mean absolute percentage error of the market's daily open price trimmed to exclude the bottom and top 5th percentiles compared to the global median's daily open price over the last 90 days.
6. **`market_close_mape_trimmed`**: The mean absolute percentage error of the market's daily close price trimmed to exclude the bottom and top 5th percentiles compared to the global median's daily close price over the last 90 days.
7. **`market_low_mape_trimmed`**: The mean absolute percentage error of the market's daily low price trimmed to exclude the bottom and top 5th percentiles compared to the global median's daily low price over the last 90 days.
8. **`market_high_mape_trimmed`**: The mean absolute percentage error of the market's daily high price trimmed to exclude the bottom and top 5th percentiles compared to the global median's daily high price over the last 90 days.

#### Volume

An assessment of the quality of the market's volume data, including testing for manipulated volume figures, and implementing tests that determine whether the exchange's markets function as active markets in the underlying digital asset and are anchored by observable transactions entered into at arm's length between buyers and sellers. The size of the exchange's markets is also considered.

1. **`market_volume_usd`**: The total volume of the market over the past 90 days in U.S. dollars.
2. **`market_volume_dispersion`**: The coefficient of variation of the market's daily volume in U.S. dollars over the past 90 days.
3. **`market_volume_price_corr_raw`**: The correlation of the market's daily return to detrended daily volume where volume is quoted in raw units over the past 90 days.
4. **`market_volume_price_corr_usd`**: The correlation of the market's daily return to detrended daily volume where volume is quoted in U.S. dollars over the past 90 days.
5. **`similarweb_global_rank`**: The global rank of the exchange's website as reported by SimilarWeb.
6. **`similarweb_visit_monthly`**: The number of monthly visits as reported by SimilarWeb.
7. **`similarweb_vmvu`**: The total U.S. dollar volume of the exchange over the past month divided by the monthly visits as reported by SimilarWeb.

### Feature Normalization

All features are normalized to between 0 and 1, with a number closer to 1 meaning that the feature contributes positively to the likelihood that the market will be selected. The qualitative features are all indicator variables that take values 0 or 1. For quantitative features, a separate empirical cumulative distribution function is calculated for all the markets for each asset. The quantitative feature is normalized by converting the value to its equivalent value on the empirical cumulative distribution function.

### Rating Algorithm

In order for a market to be eligible to receive a rating, the following three indicator variables for the market must be true: `has_rest_api`, `has_real_time_trade_data`, `has_real_time_order_book_data`. These indicator variables are required to be true because the ability to collect real-time trade data and real-time order book data via an API is necessary in order for the market to serve as an input data source.

The rating algorithm uses a weighted sum using a custom weighting function of the normalized features:

| Feature                          | Weight |
| -------------------------------- | ------ |
| has\_websocket\_feed             | 1      |
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
| similarweb\_global\_rank         | 4      |
| similarweb\_visit\_monthly       | 3      |
| similarweb\_vmvu                 | 3      |

### Selection Algorithm

Markets with a rating higher than 22.5 are selected. For each asset in the coverage universe, markets that are in the top 4 by rank are also selected, regardless of the market's rating. Any market with volume, measured in U.S. dollars over the past 90 days, of less than 5 percent of the volume of the selected market with the largest volume is excluded.

### Change Log

* **January 18, 2024:** Updated Rating Algorithm to weight fix\_gateway and Alexa criteria to 0; noted that we are leveraging only 30 of the criteria.
* January 18, 2024:   Removed the following inactive variables: `has_fix_gateway`, `alexa_rank_normalized`, `alexa_page_views_per_million_normalized`, `alexa_reach_per_million_normalized`, `alexa_pvpmvu_normalized`, and `alexa_rpmvu_normalized`. Reallocated alexa variable weights to similarweb weights. Removed market orderbooks section.
