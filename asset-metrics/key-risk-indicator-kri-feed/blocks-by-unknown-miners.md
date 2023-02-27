# Blocks by Unknown Miners

**Definition**

The count of blocks that have been mined by unknown miners 6 blocks from the tip of the blockchain.

**Dictionary**

| Name                    | MetricID                              | Category | Sub-category | Type | Unit            | Interval |
| ----------------------- | ------------------------------------- | -------- | ------------ | ---- | --------------- | -------- |
| Blocks by unknown miner | block\_count\_by\_unknown\_miners\_6b | KRI      | Mining Pools | Sum  | Count of blocks | 1 block  |

**Methodology**

The 6 blocks from the tip of the blockchain (including the most recent block) are assessed. Coin Metric employs a proprietary entity clustering methodology in order to identify major mining pools & miners. The coinbase output field used by miners to self-identify is also used to help assess miner identities.

**Available Assets (v1)**

Bitcoin (BTC), _Ethereum (ETH)\*._

_\* Historical data covering the pre-merge timeframe only (up to 9/15/2022). With the merge ETH switched from Proof of Work and miners to Proof of Stake and validators meaning the network no longer has any miners as of the merge date._

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=btc&frequency=1b&limit_per_asset=1&metrics=block_count_by_unknown_miners_6b&pretty=true" %}
