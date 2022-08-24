---
description: CM Pro FAQs
---

# Troubleshooting

#### Why am I unable to choose different resolutions?&#x20;

You are able to select a variety of resolutions for the [ExchCandles](./#exchange-candles-exchcandles) data category.   For the other data categories, the resolution is determined by the best fit for the data type (for more info see each [data category](./#data-categories)):

* ExchTrades (real-time data displayed at a 1 min resolution given a TradingView limitation on the "seconds" resolutions)
* CM-RefRates (real-time data displayed at a 1 min resolution given a TradingView limitation on the "seconds" resolutions, 1 hr at a 1 hr resolution, NY/UTC at a 1 day resolution; each is selected by selecting the named dataseries - e.g. BTC-HR-REF)
* CMBI-Indicies (15 second data displayed at a 1 min resolution given a TradingView limitation on the "seconds" resolutions, 1 hr at a 1hr resolution, D/NY/SG at a 1 day resolution; each is selected by selecting the named dataseries - e.g., CMBI-10-1H)
* CM-Metrics (daily UTC data displayed at a 1 day resolution)
* CM-RTMetrics (block-by-block data displayed at a 10 min resolution)
* Benchmarks (daily data is displayed at a 1 day resolution)

**Why can't I view historical data?**

By default, the content displayed is always from the most recent date/time. Daily data defaults to displaying the past year. For other higher density content, the amount of history displayed is dependent on information density as only the most recent 10,000 data points will get displayed.  To shift the horizon, you can hold and drag your chart.

The chart time increments at the bottom are currently only applicable to “Daily” “D” series.

#### Why don't my candles show the High/Low?

The only data category with true candles is the [ExchCandles](../../market-data/market-candles.md) category.  Selecting Candles for the other data types will result in "manufactured candles".  For instance, daily NYC close reference rates are created from the timeseries whereby the open price is the previous day's close price and the close price is the current day's close price.  The High/Low are simply either the open or close (not the intraday high and low prices).   &#x20;



