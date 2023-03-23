---
description: cmtv.coinmetrics.io
---

# Pro Charts

## Introduction

Our Coin Metrics Pro Visualization Tool incorporates the charting capabilities and indicators familiar to professional users.  It also enables our power users (market and network data users) to view our multiple datasets in a single screen.  And, users of our real-time feed can enjoy live market monitoring.

## Data Sources

All data is sourced from the CM v4 API. &#x20;

* **Network Data**:  Available through our Network Data Pro product
* **Market Data**: Available through our Market Data Feed product
* **Indexes**:  Available through our CMBI product
* **Blockchain Address Balances**: Available through our Atlas product

We also offer four external benchmarks sourced from the FRED API.  This data is not endorsed or certified by the Federal Reserve Bank of St. Louis.  These benchmarks include the&#x20;

* &#x20;S\&P 500 Index (http://fred.stlouisfed.org/series/SP500), which is an S\&P Dow Jones Indices LLC product; note the daily value for this index is as of 4pm NY time
* London Bullion Market Index (http://fred.stlouisfed.org/series/GOLDAMGBD228NLBM), which is an ICE Benchmark Administration Limited product; note the daily value for this index is as of 10:30am London time
* Trade Weighted US Dollar Index (http://fred.stlouisfed.org/seris/DTWEXBGS), which is a Board of Governors of the Federal Reserve System (US) product; note that the daily value for this index is 12:00pm NY time
* CBOE Volatility Index (http://fred.stlouisfed.org/series/VIXCLS), which is a Chicago Board Options Exchange product; note that the daily value for this index is 3:15pm Chicago time

## Available Data History

The latest 10,000 data points for any dataset are available in our CM Pro tool. For all daily metrics this will result in full data history (no assets have more than 10,000 daily data points). For other more frequently updated content (real-time trades, hourly or real-time reference rates, etc.) you will get history back through the latest 10,000 data points.  NOTE: For some data series, the available history is limited by our [data commencement date](../../exchanges/all-exchanges.md).  &#x20;

## Getting Started

The CM Pro tool can be accessed directly at [CMTV](https://cmtv.coinmetrics.io/) with or without an API key.   Without an API key, you will have access to the community data from the above [data sources](./#data-sources). \
\
If you do not have an API key, simply leave the "API KEY" pop-up blank and click "GO".

### Using an API Key

If you are a client of our professional data and you have an API Viz key, you can enter your key in the "API KEY" pop-up when you load the tool.  If you are a client, and you do not have a Viz key, contact us to obtain one.  Each user needs their own Viz key, as these keys have special permisssions.  Also, any charts saved to our cloud are saved to your user-specific key. &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-21 at 12.08.29 PM.png>)

## Charting a Data Series

1. Enter a symbol into the symbol entry window in the top left hand corner of your charting tool.&#x20;
2. As you begin typing, you will see a menu with our different data categories.  Select the appropriate data category in the menu.  &#x20;
3. The available data series within that category will then be auto-filtered as you are typing your symbol to help you find your desired selection.
4. Select the data series you would like to chart.&#x20;



![Symbol Entry Window and Data Categories Menu](<../../.gitbook/assets/Screen Shot 2021-05-20 at 10.02.17 AM.png>)

## Data Categories

### [Exchange Candles ](../../market-data/market-candles.md)(ExchCandles)

Candles are available for all our (spot and futures) market pairs.   Typing _BTC-USD-SPOT_ in the symbol entry window, and selecting the ExchCandles category will filter the BTC-USD spot markets for each supported exchange.  &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 3.21.04 PM.png>)

Our CM Pro visualization tool supports 5 min, 10 min, 15 min, 30  min, 1 hour, 4 hour and daily candles.  The default view is 1D (daily).  CM's daily close is 00:00 UTC.  To view a different candle, click the "D" (or current resolution) next to the symbol entry window, and select a different resolution.

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 3.27.28 PM.png>)

&#x20;

### [Exchange Trades ](../../market-data/market-trades.md)(ExchTrades)

Trades are available for all our  asset base/quote pairs.   Typing _BTC-USD-_ in the symbol entry window, and selecting the ExchTrades category will filter the BTC-USD markets.  &#x20;

Here you can find all the asset base/quote pairs currently offered, including exchange futures.

The trades update every 1.5 seconds and include all activity that took place in the past 1.5 seconds.  You can chart [comparisons](./#comparing-data) from multiple exchanges at the same time - the exact number of comparisons will depend on the power of you computer.  All trades data will appear in the tool's 1 minute resolution (updating every 1.5 seconds) due to a limitation of the Trading View library's "seconds" resolutions.

### [**Reference Rates**](../../asset-metrics/market/referencerateusd.md) **(CM-RefRates)**

Our Coin Metrics reference rates are available for 300+ assets. Typing the asset (e.g., _BTC_) in the symbol entry window will enable you to select the desired increment.  Increments supported include 1 min, 1 hour, daily 00:00 UTC close, and daily 4:00PM NYC close. We also have real-time (RT) rates that are computed every 1.5 seconds and update live on the chart.  All reference rate data will show up in the chosen resolution, except the real-time data, which will appear in the tool's 1 minute resolution (updating every 1.5 seconds) due to a limitation of the Trading View library's "seconds" resolutions.

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 3.49.48 PM.png>)

Note:  Our UTC Reference Rate represents the 00:00 UTC price, which is the price as of midnight UTC (midnight UTC is the beginning of the day per ISO 8601 standard).  For the sake of extreme clarity, this price is the same price found in the CM-Metrics category labeled BTC-PriceUSD for the prior day.&#x20;

### CMBI & Bletchley Index Levels (CMBI-Indices)

Here you can find our [Coin Metrics Bletchley Indexes ](../../index-data/index-levels.md)(CMBI), as well as our experimental family of [Bletchley Indexes.](https://bletchleyindexes.com/)   If you select the CMBI-Indices category, you can scroll through to view the available index levels.

If you chose the 1 minute resolution on any of the CMBI indexes you will see our live candles updating every 15 seconds.  This is due to a limitation of the Trading View library and their "seconds" resolutions.

### Asset-Metrics EOD (CM-Metrics)

Our full suite of metrics available by asset (e.g. for BTC we have over 250 metrics) are viewable in the tool with the provided CM Network Data Pro API Viz key (without the key, only Community metrics are available).  All asset metrics in this category are daily metrics (00:00 UTC/midnight UTC of the following day).&#x20;

### Asset-Metrics Real-time (CM-RTMetrics)

Our available block-by-block metrics for BTC and ETH are available in this data category.  These metrics are updated each time a new block is available. &#x20;

### Benchmarks

These are the 3rd party data sets described in [Data Sources](./#data-sources).  These benchmarks can be interesting plotted alongside cryptoassets.

### Blockchain Address Balances (Atlas)

Address balance information from over time sourced from our Atlas search tool.  These values are updated each time the address has a balance change.  To plot the balances, you need to specify the asset (e.g., "btc") and the specific address of interest.  You open the Atlas search window by clicking on "Atlas" in the top menu.

![](<../../.gitbook/assets/Screen Shot 2021-05-26 at 7.38.33 PM.png>)

You then type your address in the form of \[asset]:\[address] (e.g.,  btc:bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh). in the search window.

![](<../../.gitbook/assets/Screen Shot 2021-05-26 at 7.36.43 PM.png>)

## Changing the Chart Type&#x20;

Next to the symbol entry window, you can adjust the chart type by selecting the current chart type from the menu.  Upon selecting the chart type image, you will see other chart types.  In the example below, the data was presented as a line chart and selecting the small image that looks like a line chart, you will see other chart options. &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 9.50.08 PM.png>)

The only data category with true candles is the [ExchCandles](../../market-data/market-candles.md) category.  Selecting Candles for the other data types will result in "manufactured candles".  For instance, daily NYC close reference rates are created from the timeseries whereby the open price is the previous day's close price and the close price is the current day's close price.  The High/Low are simply either the open or close (not the intraday high and low prices).   &#x20;

## Comparing Data

To compare multiple timeseries, click "Compare" in the menu after plotting your primary timeseries.  &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 9.30.19 PM.png>)

In the compare dialog, ensure that "Add Symbol" is selected.  Add your second timeseries using the data category menus and symbol entry in the same way that you plotted your primary timeseries.  Repeat this process for each additional timeseries you'd like to compare.

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 9.35.28 PM.png>)

Each timeseries will auto-scale on its own axis.  To view these timeseries on a single axis, right click on the left hand (primary) axis and select "Merge All Scales Into One".  Select "On The Left" or "On The Right", depending on your preference.

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 9.44.54 PM.png>)

## Using Indicators

The TradingView library has many built-in indicators.  These indicators can be easily accessed  by clicking "Indicators" in the menu. &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 10.08.39 PM.png>)

Upon clicking "Indicators", you will see all available indictors and a search window.  Simply select the desired indicator or begin typing to auto-filter for the indicator desired. &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 10.16.15 PM.png>)

For example, if you select the "Spread" indicator, the fields required to display the spread (difference) will appear and the "Spread" between the primary series and the series entered (via symbol) will display in the window below your primary plot.

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 10.19.42 PM.png>)

For more information on these indicators, visit [TradingView's documentation](https://www.tradingview.com/ideas/indicator/). &#x20;

## Switch Between Light and Dark Mode

Easily switch between light and dark mode by clicking the Light/Dark button in the menu.

## Save/Load

The Save and Load functions are only available to users with an API Viz Key.  Both functions are accessible via the top menu.  The “Save” feature saves your graph and any studies you have created which you can subsequently restore with the “Load” feature. When you click the "Save" button, you will be asked to name your chart/study.  Your charts/studies are saved to a central Coin Metrics server-side storage facility via API Key so only you can see your charts.  To "Load" your saved chart, click "Load" from the menu and simply select the desired chart by name from the pop-up dialog.

## Snapshot

Use the "Snapshot" feature (camera icon in the top right hand corner of your chart).  A dialog will appear with your "Image URL" and an option to save your chart (image) &#x20;

![](<../../.gitbook/assets/Screen Shot 2021-05-13 at 4.40.32 PM.png>)

## Export

The “Export” feature lets you export your chart contents (series, indicators and comparison series) to a CSV file which can be opened with Excel or Numbers. &#x20;

### Time-Conversion

The export uses a "microseconds (MS) time since Epoch" for its X axis time value.  Upon export, if you want to convert the time to the normal date/time format the following Excel conversion is offered:&#x20;

_To convert to UTC enter this formula_

> \=\<timecell>/86400+25569 (divide by seconds in a day + Jan 1 1970 offset for epoch time).&#x20;

_For more westerly time zones_

> subtract offset seconds from \<timecell> (e.g., for EST subtract 18000 obtained by computing 5 hours of seconds for the EST offset (60\*60\*5)

_For more easterly time zones_&#x20;

> add offset seconds to \<timecell>&#x20;

## Live Prices

The Live Prices in the menu launches a dialog that shows the top assets' real-time prices.

![](<../../.gitbook/assets/Screen Shot 2020-12-28 at 9.22.46 PM.png>)

Every 3 seconds, we use the CM Reference Rate and the Rate from 24 hours ago to compute the % change for each asset. This is a scrolling and draggable window.
