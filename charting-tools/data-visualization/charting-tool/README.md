---
description: https://charts.coinmetrics.io/network-data/
---

# Charting Tool

## Selecting a Data Series

The Charting Tool allows you to easily visualize our [Asset Metrics](../../../asset-metrics/asset-metrics-overview.md).  Simply select the asset/metric pair from the top left selection dialogs. &#x20;

![](<../../../.gitbook/assets/Screen Shot 2020-12-30 at 1.13.48 PM.png>)

Upon clicking the "Assets" button, the Assets dialog will open to display the available assets.  Assets can be searched by category or by typing the symbol or name into the "Find assets..." search window.&#x20;

Once you've made your asset selection, you can click on the "Metrics" button, which will open the Metrics dialog to display the metrics available for the selected assets.  The metric will be displayed in black will be "selectable" if it is available for any selected asset. &#x20;

Metrics that are not available for the assets selected will show the "unavailable symbol".

![](<../../../.gitbook/assets/Screen Shot 2021-03-09 at 8.52.33 PM.png>)

Metrics that are not available with API key entered will show a "lock symbol.

![](<../../../.gitbook/assets/Screen Shot 2021-03-09 at 8.54.58 PM.png>)

The metric definition can be expanded via the "question symbol" to the right of the metric name as shown below.  To collapse it, click the "up arrow".

![](<../../../.gitbook/assets/Screen Shot 2021-03-09 at 8.57.53 PM.png>)

## Handling of Data Gaps

On occasion, you may want to compare a continuous data series with one with gaps (such as when you compare cryptoasset returns with a traditional index like S\&P500 that has no values on the weekends or holidays).  The tool gives you two options for handling this:

* Linearly interpolate the data to derive a value for the data gap prior to calculating the returns
* Exclude the observations on the dates where one data series has a gap, but the other doesn't prior to calculating the returns (note:  this results in fewer observations for the non-gapped series)

The tool will default to "excluding" data where gaps are identified.  You can adjust this setting from the settings menu on the right toolbar.

![Click on the "gear" to find the settings for Data Gaps](<../../../.gitbook/assets/Screen Shot 2020-12-19 at 4.48.10 PM.png>)

## **Charting Tool Tutorial Series**

### **Part 1 - Tool Basics**

In the first segment of our tutorial series, we explore the basic features and functions you'll need to get started with our Network Data visualization tool.

[**Charting Tool Tutorial Series - Part 1**](https://5264302.fs1.hubspotusercontent-na1.net/hubfs/5264302/Charting%20Tool%20Demo%20\(Part%201\)%20-%20Tool%20Basics.mp4)

### **Part 2 - Assets & Metrics**

The second segment of the series explores the wide array of assets and metrics available in the Coin Metrics coverage universe, and demonstrates the variety of charting tool settings that can be used to visualize this data.

[**Charting Tool Tutorial Series - Part 2**](https://5264302.fs1.hubspotusercontent-na1.net/hubfs/5264302/Charting%20Tool%20Demo%20\(Part%202\)%20-%20Assets%20&%20Metrics.mp4)

