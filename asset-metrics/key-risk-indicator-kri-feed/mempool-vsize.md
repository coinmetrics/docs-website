# Mempool vsize

**Definition**

The total virtual size (vsize) of all transactions in the mempool, in virtual bytes. [Virtual Size (vsize)](https://en.bitcoin.it/wiki/Weight\_units) is a unit used to measure the size of bitcoin transactions after the activation of SegWit.

**Dictionary**

| Name          | MetricID       | Category | Sub-category | Type | Unit          | Interval |
| ------------- | -------------- | -------- | ------------ | ---- | ------------- | -------- |
| Mempool vsize | mempool\_vsize | KRI      | Mempool      | Sum  | Virtual bytes | 1m       |

**Methodology**

The mempool is evaluated and all transactions within are indexed. The virtual size of all transactions is summed.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_vsize&pretty=true" %}
