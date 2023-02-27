# Non SegWit Blocks

**Definition**

The number of blocks without [SegWit](https://en.bitcoin.it/wiki/Segregated\_Witness) transactions in the past 6 blocks.

**Dictionary**

| Name              | MetricID                          | Category | Sub-category     | Type | Unit             | Interval |
| ----------------- | --------------------------------- | -------- | ---------------- | ---- | ---------------- | -------- |
| Non segwit blocks | block\_count\_without\_segwit\_6b | KRI      | Block Attributes | Sum  | Number of blocks | 1 block  |

**Methodology**

The 6 blocks from the tip of the blockchain (including the most recent block) are assessed, and the number of blocks without SegWit transactions is counted.

**Available Assets**

Bitcoin (BTC)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_count_without_segwit_6b&pretty=true" %}
