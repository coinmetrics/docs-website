# Reference Rate FAQs

### **How do you calculate your Reference Rates?**

The pricing inputs for our Indexes are informed by our Reference Rates methodologies.  We have methodologies for both hourly rates and real time rates.&#x20;

* [Real Time Reference Rates  ](https://coinmetrics.io/wp-content/uploads/2021/04/rtrr-methodology.pdf)
* [Hourly Reference Rates  ](https://coinmetrics.io/wp-content/uploads/2021/04/reference-rates-methodology.pdf)

Our hourly and daily CMBI levels use our Hourly Reference Rates and our 15 second levels use our rReal Time Reference Rates.  &#x20;

### **Is there a difference between “ReferenceRate” and “ReferenceRateUSD” for BTC?**

ReferenceRate and ReferenceRateUSD are identical - when we added ReferenceRateEUR we also added ReferenceRateUSD but left ReferenceRate for backward compatibility.

### **Why do you use non-USDT-USD pairs to calculate USDT-USD price?**

The market convention for stablecoins is to use stablecoins as the quote currency. As such, there are only a few usdt-usd markets and the markets that do exist are very thinly traded.  We can use btc-usdt markets to derive a price for btc-usd and btc-usdt, which can be used to derive a usd-usdt price. Both the btc-usd and btc-usdt markets have huge volume, so you can calculate a very accurate price this way compared to only relying on the usd-usdt markets.

### **What is the expected latency for the ‘1s’ frequency of WebSocket Reference Rates?**

The typical latency is 1.8-1.9 seconds for WebSocket reference rates. Our process is to wait 1 second to allow all relevant trades from all constituent exchanges (which vary depending on the asset), and then we do some pretty extensive computations to calculate the real time rate. After that we hand off the rate to our delivery system and it's then reflected on your end. &#x20;

### **When pulling ReferenceRateUSD and ReferenceRateEUR along with other metrics (like PriceUSD or FeeMeanNTV), the reference rates are updated with data up to the current date while other metrics are only updated to yesterday’s date. Why are these data fields assigned different dates?**

We use two different timestamp conventions for our metrics. Some metrics, like PriceUSD, use the "start-of-interval" timestamp, which represents the beginning of a time interval. Many network data metrics account for the value over a daily time interval. For example, suppose our FeeMeanNTV metric, which represents mean fees over an interval of a day, has a timestamp of 2020-12-10 00:00:00. The FeeMeanNtv value represents the mean of fees that occurred from 2020-12-10 00:00:00 to 2020-12-11 00:00:00.&#x20;

Other metrics, like ReferenceRate (and many other data types like trades, open interest and order book), use the "point-in-time" timestamp convention, where timestamp is set to the specific timestamp of the measurement or event. This is because we want to generate a price at a specific point in time.&#x20;

When you compare something that uses the "point-in-time" convention with something that uses the "start-of-interval" convention, it can seem like the "start-of-interval" timeseries is lagged or is potentially missing data. I can assure that this is not the case, but we certainly understand your confusion here since the different values are delivered via the same timeseries/asset-metrics endpoint. We are working on adding more documentation to our API Documentation to address this more proactively.&#x20;

### **What is the difference between your Reference Rates and Volume Weighted Average Pricing?**&#x20;

Our Reference Rates are different because we don't use volume weighted average price in the calculation**.**  Instead we use the volume weighted median price per time interval.

ReferenceRate with frequency 1h or 1d come from our Hourly Reference Rates. These rates use a 61 minute calculation window that is partitioned into 1 minute intervals. The volume-weighted median price for each 1 minute interval is calculated and then a time-weighted average price is calculated using a custom weight function that applies more weight to intervals close to the calculation time.

ReferenceRate with frequency 1s or 1m come from our Real-Time Reference Rates. These rates extract the most recent trade from our set of constituent markets and calculate a weighted median where half the weight is calculated from volume measured over the previous 60 minutes and half the weight is calculated from inverse price variance of trades over the previous 60 minutes.

Our Real Time and Hourly Reference Rate Methodologies have further details on our calculation algorithms: &#x20;

* [Real Time Reference Rates  ](https://coinmetrics.io/wp-content/uploads/2021/04/rtrr-methodology.pdf)
* [Hourly Reference Rates  ](https://coinmetrics.io/wp-content/uploads/2021/04/reference-rates-methodology.pdf)
