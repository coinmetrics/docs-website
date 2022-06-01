# Data Visualization

## Introduction

Our  Data Visualization offering includes three tools:

* [Charting tool](charting-tool/)
* [Formula builder](formula-builder.md)
* [Correlation tool](correlation-tool.md)

These tools allow for easy exploration of our network (on-chain data).  Users can select multiple assets and metrics to identify trends and insights or leverage our powerful formula builder to transform data series.   The correlation tool makes for simple correlation analysis.  All charts can be downloaded as PNGs and the charted data can be exported to CSV or XLS files.  And, you can save your charts for later or share them with others.

## Data Sources

All data is sourced from the CM v4 API. &#x20;

* **Network Data (EOD)**:  Available through our Network Data Pro product
* **Reference Rates**:  Specifically our daily 00:00 UTC, 12pm NYC, 4pm NYC, 10:30am London, 11:00am London,  3:15 Chicago&#x20;
* **Indexes (Daily Levels)**:  Available through our CMBI product

We also offer five external benchmarks sourced from the FRED API.  This data is not endorsed or certified by the Federal Reserve Bank of St. Louis.  These benchmarks include the&#x20;

* &#x20;S\&P 500 Index (http://fred.stlouisfed.org/series/SP500), which is an S\&P Dow Jones Indices LLC product; note the daily value for this index is as of 4pm NY time
* London Bullion Market Index (http://fred.stlouisfed.org/series/GOLDAMGBD228NLBM), which is an ICE Benchmark Administration Limited product; note the daily value for this index is as of 10:30am London time
* Trade Weighted US Dollar Index (http://fred.stlouisfed.org/seris/DTWEXBGS), which is a Board of Governors of the Federal Reserve System (US) product; note that the daily value for this index is 12:00pm NY time
* CBOE Volatility Index (http://fred.stlouisfed.org/series/VIXCLS), which is a Chicago Board Options Exchange product; note that the daily value for this index is 3:15pm Chicago time
* 1-Month London Interbank Offered Rate (LIBOR) (http://fred.stlousfed.org/series/USD1MTD156N), which is an ICE Benchmark Administration Limited product; note the daily value for this index is as of 11:00am London time

## Getting Started

This suite of charting tools can be accessed directly at [Charts](https://network-charts.coinmetrics.io/) with or without an API key.   Without an API key, you will have access to the community data from the above[ data sources. ](./#data-sources)

### Using an API Key

If you are a client of our professional data and you have an API Viz key, you can enter your key by selecting the "key" on the top of the right toolbar.  If you are a client, and you do not have a Viz key, contact us to obtain one.  Each user needs their own Viz key, as these keys have special permisssions.  Also, any charts saved to our cloud are saved to your user-specific key. &#x20;

![](<../../.gitbook/assets/Screen Shot 2020-12-20 at 4.48.50 PM.png>)

## Saving Charts

You can save your charts in all three of our tools.  Simply select the "save" image on the right toolbar.   There are two options for saving your charts:

* Save as... (only available to users with a Viz API key) - save your chart to your API key and reload it later from any device.  Charts saved to your API key can be "named" (given a title) and can be shared via a chart-specific URL.
* Save to local drive - save your chart to your local drive in a json format and reload it for later use.

![Click on the "disk" to find the Save Options](<../../.gitbook/assets/Screen Shot 2020-12-21 at 11.51.39 AM.png>)

## Loading Charts

To load a previously saved chart, select the "folder" image on the right toolbar.   If you saved your chart to your API key (to the Cloud), then "Load from cloud".  If you saved your chart to your local drive, then "Load from file".&#x20;

![](<../../.gitbook/assets/Screen Shot 2021-07-19 at 10.00.54 AM.png>)

If you "Load from file", then find your file/chart using the explorer window.

## Sharing Charts

If you'd like to share a chart via a URL, you need an API via key.  Once your API key is set, then, click the "share" button. &#x20;

![Click on the "share" button to copy a sharable URL to the desktop](<../../.gitbook/assets/Screen Shot 2020-12-30 at 12.33.01 PM.png>)

If you've already saved your chart, then ensure that "Sharing on" is green, and click the copy button to copy the URL to the clipboard.   If you haven't yet saved your chart, name the chart and then copy the URL to the clipboard.

![](<../../.gitbook/assets/Screen Shot 2020-12-30 at 12.36.51 PM.png>)

## Downloading Charts

Charts can be downloaded to data files (CSV or XLS) or image files (PNG with our without a legend).   Simply select the "download" button on the right toolbar.  If you'd like to see a title on your chart, save your chart and assign a name.  The assigned name will be your title. &#x20;

![Click on the "download" button to find the Download Options](<../../.gitbook/assets/Screen Shot 2020-12-30 at 12.21.12 PM.png>)

## Chart Options

There are several ways to adjust your plot in both the "Charting Tool" and the "Formula Builder".  These features are located on the bottom toolbar.  From left to right below:

* Lin/Log - adjust the vertical axes to a Linear or Logarithmic scale (the choice applies to both right and left axes)
* Line/Stacked Area/100% Stacked Area - chose a different chart type
* Average - select no average, a 7-day moving average, a 14-day moving average, a 30-day moving average, a 50-day moving average, a 90-day moving average and a 200-day moving average
* Right axis - chose which series you'd like to see on the right hand axis (RHS) (only on the primary charting tool, not in Formula Builder or Correlation Tool)
* All/1M/3M/1Y/YTD - chose your preferred X-axis range &#x20;

![](<../../.gitbook/assets/Screen Shot 2021-05-14 at 9.01.54 AM.png>)

