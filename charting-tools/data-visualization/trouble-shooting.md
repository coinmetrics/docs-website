# Troubleshooting

#### Why am I unable to access certain metrics? 

While we offer hundreds of metrics to our Community users, the metrics with a "lock" are Pro metrics.  If you are a Pro user and you still see a "lock", this metric is likely not included with your subscription.  If you see a "warning" sign, that metric is not compatible with any of the assets you've selected \(e.g., UTXO metrics for a ETH\).

#### How do I unselect an asset that was pre-selected in the chart?

When you first load the charting tool, several commonly used assets are in the top toolbar. The "greyed" out assets are now shown in the chart, but they are technically still selected.  To unselect them,  click "Assets" -&gt; "Show Selected" and deselect the assets.  You can also use the "Deselect All" in the top corner of the window.

#### Why can't I select Price USD or several of the other prices for GOLD \(or LIBOR or VIX\)?

The traditional indexes \(Gold, Libor, etc.\) only offer a single closing time.  Therefore there is no Price USD \(which is a 00:00 UTC price\) for these indexes.  The closing times/prices for each of these indexes are as follows:

| Index | Available Price |
| :--- | :--- |
| S&P 500 | USD 4:00pm New York Price / Index Value |
| Gold | USD 10:30am London Price / Index Value |
| Dollar | USD 12:00pm New York Price / Index Value |
| VIX | USD 3:15pm Chicago Price / Index Value |
| LIBOR | USD 11:00am London Price / Index Value |

#### How can I zoom into a specific date range?

You can leverage our pre-selected zooms \(All, 1 month, 3 months, 1 year or YTD\) or you can drag the handles on the grey bar to zoom in on your desired range.  Unfortunately, these handles aren't particularly precise.  If you aren't getting to the range you desire, you the Formula builder slice the series using the Subseries formula.

Bitcoin Price in USD from January 1, 2015 through January 31, 2015:`slice(BTC.PriceUSD, date(2015, 1, 1), date(2018, 1, 31))`

We hope to have a calendar selector in a future version of the tool.

#### I am unable to use MetricIDs containing decimal points in the Formula Builder.  Help.

If a MetricID has a “.” \(e.g., SplyAdrBalNtv0.1\), use the AssetID.metric\("Metric.ID"\) notation.   

Example: `BTC.metric("SplyAdrValNtv.01")` 

Note:  quotation marks must be "straight quotes" and not "fancy quotes".

