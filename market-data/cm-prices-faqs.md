# CM Prices FAQs

### **How do you calculate the CM Reference Rates?**

The CM Prices are collectively governed by rules-based methodologies described in [Coin Metrics Prices Methodology](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) which describes our Market Selection Framework, a systematic method of producing a unique set of constituent markets for each asset, our data sources, calculation algorithm, and contingency rules..

{% content-ref url="methodologies/coin-metrics-prices-methodology.md" %}
[coin-metrics-prices-methodology.md](methodologies/coin-metrics-prices-methodology.md)
{% endcontent-ref %}

### **Is there a difference between the metrics ReferenceRate and ReferenceRateUSD?**

`ReferenceRate` and `ReferenceRateUSD` are identical. When we added reference rates quoted in other currencies like `ReferenceRateEUR`, we also added `ReferenceRateUSD` and preserved `ReferenceRate` for backward compatibility.

### **Why do you use non-USDT-USD pairs to calculate the USDT-USD price?**

The market convention for stablecoins is to use stablecoins as the quote currency. As such, there are only a few usdt-usd markets and the markets that do exist are very thinly traded. We can use other markets that are more active such as btc-usdt markets to derive a price for btc-usd and btc-usdt, which can be used to derive a usd-usdt price. Both the btc-usd and btc-usdt markets have high levels of volume, so the quality of our prices are improved compared to relying on only the usd-usdt markets.

### **What is the expected latency for the 1s frequency of Reference Rates served through your websocket API?**

Our typical calculation latency is approximately 60 ms. A small amount of time is also required for normal network latency depending on the geographic location of your client relative to our servers.

### **When pulling ReferenceRateUSD and ReferenceRateEUR along with other metrics (like PriceUSD or FeeMeanNTV), the reference rates are updated with data up to the current date while other metrics are only updated to yesterday’s date. Why are these data fields assigned different dates?**

We use two different timestamp conventions for our metrics. Some metrics, like `PriceUSD`, use the "start-of-interval" timestamp, which represents the beginning of a time interval. The majority of our network data metrics represent a summary statistic over a daily time interval.&#x20;

For example, suppose our `FeeMeanNTV` metric, which represents mean fees over an interval of a day, has a timestamp of `2020-12-10 00:00:00`. The `FeeMeanNtv` value represents the mean of fees that occurred from `2020-12-10 00:00:00` to `2020-12-10 23:59:99.999999`.&#x20;

Other metrics, like `ReferenceRate` (and many other data types like trades, open interest and order book), use the "point-in-time" timestamp convention, where timestamp is set to the specific timestamp of the measurement or event. This is because we want to generate a price at a specific point in time.

When you compare something that uses the "point-in-time" convention with something that uses the "start-of-interval" convention, it can seem like the "start-of-interval" timeseries is lagged or is potentially missing data. I can assure that this is not the case, but we certainly understand your confusion here since the different values are delivered via the same `timeseries/asset-metrics` endpoint.

For more information, please see [What timestamp conventions does Coin Metrics use?](https://docs.coinmetrics.io/market-data/market-data-faqs#what-timestamp-conventions-does-coin-metrics-use)

### **What is the difference between your Reference Rates and a volume-weighted average price?**&#x20;

Our CM Reference Rates utilize volume-weighted median, time-weighted average, and inverse price variance-weighted median techniques.

ReferenceRate with frequency 1h or 1d use a 61 minute calculation window that is partitioned into 1 minute intervals. The volume-weighted median price for each 1 minute interval is calculated and then a time-weighted average price is calculated using a custom weight function that applies more weight to intervals close to the calculation time.

ReferenceRate with frequency 1m or 1s or 200ms extract the most recent trade from our set of constituent markets and calculate a weighted median where half the weight is calculated from volume measured over the previous 60 minutes and half the weight is calculated from inverse price variance of trades over the previous 60 minutes.

The CM Prices are collectively governed by rules-based methodologies described in [Coin Metrics Prices Methodology](https://docs.coinmetrics.io/market-data/methodologies/coin-metrics-prices-methodology) which describes our Market Selection Framework, a systematic method of producing a unique set of constituent markets for each asset, our data sources, calculation algorithm, and contingency rules.

{% content-ref url="methodologies/coin-metrics-prices-methodology.md" %}
[coin-metrics-prices-methodology.md](methodologies/coin-metrics-prices-methodology.md)
{% endcontent-ref %}

### What do the frequency parameters `1d` and `1d-ny-close` mean?

Our CM Prices are served through our [/timeseries/asset-metrics](https://docs.coinmetrics.io/api/v4/#tag/Timeseries/operation/getTimeseriesAssetMetrics) API endpoint, and this endpoint supports a frequency parameter that can take several values, including `1d` and `1d-ny-close`.

The `1d` frequency represents a daily frequency that ends at 00:00:00 in the UTC timezone and the `1d-ny-close` represents a daily frequency that ends at 16:00:00 in the America/New\_York timezone. These timestamps are not altered for weekends or holidays.

Please also see our FAQ on [What timestamp conventions does Coin Metrics use?](https://docs.coinmetrics.io/market-data/market-data-faqs#what-timestamp-conventions-does-coin-metrics-use) for more information.
