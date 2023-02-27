# Average Hashrate

**Definition**

The mean hash rate needed to mine a block based on data from the previous 24 hrs. Hash rate is the speed at which computations are being completed across all miners in the network, in hashes per second.

**Dictionary**

| Name             | MetricID                  | Category | Sub-category | Type | Unit              | Interval |
| ---------------- | ------------------------- | -------- | ------------ | ---- | ----------------- | -------- |
| Average Hashrate | block\_hashrate\_mean\_1d | KRI      | Mining Pools | Mean | Hashes per second | 1 block  |

**Methodology**

Hash rate is derived from difficulty (DiffMean), the rate at which block came in (BlkIntMean) and depending on the protocols, some other pieces of data. This metric gives an estimate of how much hash power is mining a given chain. This represents a sliding 1d average.

**Available Assets**&#x20;

Bitcoin (BTC), _Ethereum (ETH)\*_

_\* Historical data covering the pre-merge timeframe only (up to 9/15/2022). With the merge ETH switched from Proof of Work and miners to Proof of Stake and validators meaning the network no longer has a hashrate as of the merge date._

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc,ltc&frequency=1b&limit_per_asset=1&metrics=block_hashrate_mean_1d&pretty=true" %}
