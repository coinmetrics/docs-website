# Mempool Transaction Output Value

**Definition**

The sum of all mempool transaction outputs in native units.

**Dictionary**

| Name                             | MetricID               | Category | Sub-category | Type | Unit         | Interval |
| -------------------------------- | ---------------------- | -------- | ------------ | ---- | ------------ | -------- |
| Mempool Transaction Output Value | mempool\_output\_value | KRI      | Mempool      | Sum  | Native Units | 1m       |

**Methodology**

The mempool is evaluated and all transaction outputs (UTXOs) are indexed. The value of all UTXOs of mempool transactions is then summed.

**Available Assets**&#x20;

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1m&limit_per_asset=1&metrics=mempool_output_value&pretty=true" %}
