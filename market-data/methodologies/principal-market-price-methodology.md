# Principal Market Price Methodology

The full text of this methodology can be downloaded as a pdf document using the link below.&#x20;

{% file src="../../.gitbook/assets/PMR_Methodology_2022_09_12.pdf" %}

## Introduction

This document describes our first implementation of Coin Metric’s Principal Market price calculation Methodology. It was developed taking into account the requirements of IFRS 13 and ASC 820 accounting guidelines defining what a Principal Market is and how it should be selected. These guidelines also allow for additional controls to verify the market is active and trades are orderly. As we acquire new data in the future (for example, when a forced liquidation occurs) it is possible some of the steps below will be elaborated in the future to ensure we are calculating a fair market value.&#x20;

As Coin Metrics already provides a proprietary [Reference Rate methodology](https://docs.coinmetrics.io/market-data/methodologies/real-time-reference-rates-methodology) to price crypto-assets which we believe to be robust and stable, it is worth briefly describing the philosophy behind producing a Principal Market Price to supplement the Reference Rates. The first and most significant criteria is that certain regulatory agencies require a methodology consistent with the aforementioned accounting principles. These principles clearly describe the preferred ’fair market value’ calculation as one which identifies a Principal Market by trade volume and tracks executed trades in that market.&#x20;

Beyond external requirements the benefits for a Principal Market methodology are that it is that it is clearly defined and auditable. The price is always taken from a single market, which tends to remain constant, and can easily be traced and double checked for a given time stamp. We minimize computations being done on the price, which reduces the likelihood of unforeseen behavior. Additionally, the trades are always taken from the exchange where the most of the activity is happening, which is setting customers are most likely to be interested in.&#x20;

Like all things in life, this comes with some trade offs. Our Reference Rates look for a central tendency among several markets. In some cases this can avoid volatility if the Principal Market deviates from the global average, but it also means that the final price may be taken from comparatively insignificant market that is sandwiched between markets of larger volume. With these trade-offs in mind, our methodology seeks err on the side of trusting the largest market by volume of trades, and only exclude a market in extreme situations.&#x20;

We also to avoid numerical comparisons of the price between markets in the methodology, in order to minimize the possibility that a price anomaly could affect the calculation of other markets. Our Reference Rate by contrast chooses to combine multiple markets to identify a more stable price representative of the global environment.

## Description

The Principal Market Prices are published once per second, every day of the year, and represent the price of one unit of the asset quoted in U.S. dollars or other currency.

## Data and Calculation Methodology

1. Consider list of approved constituent markets already in use for Coin Metrics Reference Rates&#x20;
   * Market Selection uses data and human review to ensure inclusion of high-quality exchanges and data feeds
   * Summary can be found [here](https://docs.coinmetrics.io/market-data/methodologies/hourly-reference-rates-methodology#market-selection-framework) and specific details [here](https://docs.coinmetrics.io/methodologies/reference-rates/market-selection-framework)
2. Identify any inactive markets, drop all trades associated with the inactive market. A market is considered inactive if it meets the following conditions:
   * (a) The last trade was more than 1-minute ago **AND**&#x20;
   * (b) The last trade was either:&#x20;
     * i. Longer than 10-minutes ago (no markets without trades for 10 minutes will be considered) **OR**&#x20;
     * ii. Longer than 100 ∗ \[mean trade interval]&#x20;
       * A. The mean trade interval is defined as: The the average of all intervals between sequential trades in the past 1-hour. For example, if trades happen at times \[00:02, 00:12, 0:37, 1:15] the MTI will be mean\[10s, 25s, 38s] = 23.3sec&#x20;
       * B. Investigation shows the maximum trade interval in a given hour is often around 20-30x the mean trade interval. It is very rare to see a gap of more than 50x the mean interval in trading, especially in the highest volume market.
   * (c) If there are no active markets (no market has a trade in the past 10 minutes), then the PMP will forward-fill the last non-null value available.
     * i. We have not yet identified a situation where all markets go down simultaneously.
3. Check if any trades in the markets are not considered orderly (IFRS 13.B37-B38). Drop any non-orderly trades from the calculation.
   * (a) This is done by looking 2 windows ago (60-120 min before calculation time) to calculate a reference standard deviation of prices in each market separately.
     * i. If there are not sufficient trades to calculate a standard deviation in the 60- 120 minute window, then all trades are considered orderly (i.e. no trades are dropped if there is sparse data).
   * (b) Then we divide the most recent window (0-60 min from calc. time) into 60 1- minute slices and calculate how far each trade is from the mean price of trades in that market in the same 1-minute slice.
   * (c) Finally, we exclude trades that occur more than three reference standard deviations from the mean price of trades within that minute.&#x20;
   * (d) We also require at least five trades occur in that minute in order to exclude any. The two parameters (3 reference deviations and 5 trades) may be adjusted in the future.
4. Identify the active market with the largest volume of orderly trades in the past 1-hour time window. This will serve as the Principal Market. (IFRS 13.16, ASC 820-35-5)&#x20;
5. Use the most recent orderly trade on the PM and publish as the PMP.

## Compliance

Coin Metrics maintains records and has processes in place to comply with requests for information from regulatory authorities. Coin Metrics commits to full cooperation with any regulatory authority in carrying out their regulatory or supervisory duties.

## Change Log

1. **Version 0.1 on October 25, 2022**: Initial publication of Principal Market Price Methodology.
