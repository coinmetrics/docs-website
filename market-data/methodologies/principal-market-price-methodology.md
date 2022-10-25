# Principal Market Price Methodology

The full text of this methodology can be downloaded as a pdf document using the link below.&#x20;

{% file src="../../.gitbook/assets/PMR_Methodology_2022_09_12.pdf" %}

## Introduction

This document describes our first implementation of Coin Metric’s Principal Market price calculation Methodology. It was developed taking into account the requirements of IFRS 13 and ASC 820 accounting guidelines defining what a Principal Market is and how it should be selected. These guidelines also allow for additional controls to verify the market is active and trades are orderly. As we acquire new data in the future (for example, when a forced liquidation occurs) it is possible some of the steps below will be elaborated in the future to ensure we are calculating a fair market value.&#x20;

As Coin Metrics already provides a proprietary Reference Rate methodology to price crypto-assets which we believe to be robust and stable, it is worth briefly describing the philosophy behind producing a Principal Market Price to supplement the Reference Rates. The first and most significant criteria is that certain regulatory agencies require a methodology consistent with the aforementioned accounting principles. These principles clearly describe the preferred ’fair market value’ calculation as one which identifies a Principal Market by trade volume and tracks executed trades in that market.&#x20;

Beyond external requirements the benefits for a Principal Market methodology are that it is that it is clearly defined and auditable. The price is always taken from a single market, which tends to remain constant, and can easily be traced and double checked for a given time stamp. We minimize computations being done on the price, which reduces the likelihood of unforeseen behavior. Additionally, the trades are always taken from the exchange where the most of the activity is happening, which is setting customers are most likely to be interested in.&#x20;

Like all things in life, this comes with some trade offs. Our Reference Rates look for a central tendency among several markets. In some cases this can avoid volatility if the Principal Market deviates from the global average, but it also means that the final price may be taken from comparatively insignificant market that is sandwiched between markets of larger volume. With these trade-offs in mind, our methodology seeks err on the side of trusting the largest market by volume of trades, and only exclude a market in extreme situations.&#x20;

We also to avoid numerical comparisons of the price between markets in the methodology, in order to minimize the possibility that a price anomaly could affect the calculation of other markets. Our Reference Rate by contrast chooses to combine multiple markets to identify a more stable price representative of the global environment.

## Description

The Principal Market Prices are published once per second, every day of the year, and represent the price of one unit of the asset quoted in U.S. dollars or other currency.

## Compliance

Coin Metrics maintains records and has processes in place to comply with requests for information from regulatory authorities. Coin Metrics commits to full cooperation with any regulatory authority in carrying out their regulatory or supervisory duties.

## Change Log

1. **Version 0.1 on October 25, 2022**: Initial publication of Principal Market Price Methodology.
