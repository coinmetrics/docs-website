# CM Labs

[CM Labs](https://coinmetrics.io/cm-labs/) is a place for our pioneering team to experiment.  Here, you'll find associate passion projects, fun prototypes, test products/features and cutting edge efforts that are experimental in nature.  Many of our most popular commercial products have their roots in these innovative, community-first efforts. &#x20;

While CM Labs products and features are very cool, for one reason or another, we are not quite ready to incorporate them into our mainstream product offerings. &#x20;

## Identification of CM Labs Efforts

In addition to the projects and prototypes you'll find on our CM Labs [site](https://coinmetrics.io/cm-labs/), you will also notice certain metrics and assets (e.g., ICP) flagged in our tools as CM Labs. &#x20;

![](<.gitbook/assets/Screen Shot 2021-08-24 at 7.54.11 PM.png>)

This flag also exists in our catalogs.  Experimental assets/metrics with have `"experimental": true` in the array of objects returned for that asset/metric.

```
 }, {
    "asset" : "icp",
    "full_name" : "Internet Computer",
    "experimental" : true,
    "metrics" : [ {
      "metric" : "AdrAct30dCnt",
      "frequencies" : [ {
        "frequency" : "1d",
        "min_time" : "2021-05-06T00:00:00.000000000Z",
        "max_time" : "2021-08-23T00:00:00.000000000Z"
      } ]
```

{% hint style="warning" %}
While we obviously feel there is value in making these experimental assets/metrics available, please exercise caution given their experimental nature. &#x20;
{% endhint %}

## Examples of Labs Efforts

Below are some examples of Labs efforts:

* Experimental on-chain asset coverage in NDP and Atlas (e.g., ICP, DOT, ALGO, XTZ)
* DeFi Market Data (i.e., Uniswap and Sushiswap swaps, liquidity pool metadata, candles, and volume metrics)
* Farum Risk Management offerings (e.g., WatchTower Alerts (`/asset-alerts`), Mining Pool Monitor (`/mining-pool-tips-summary`), Reorg & Fork Tracker (`/asset-chains`)
* Flat Files Delivery System
