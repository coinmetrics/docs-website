---
description: /timeseries/mining-pool-tips-summary
---

# Mining Pool Monitor API Fields

Coin Metrics collects data from major mining pools through the Stratum protocol, a popular software used by individual miners to connect to mining pools. This enables Coin Metrics to access all data that the miners within a mining pool would see, such as the block template that all mining pool constituents are working on. Access to block templates is critical as it can predict reorgs, settlement disruptions, consensus failures, and attacks like 51% attacks.

This predictive property of the Mining Pool Monitor is enabled by the real-time identification of mining conflicts. Such conflicts occur when mining pools do not agree on the same sequencing of blocks in the blockchain. Often, this is caused by a few mining pools that have not yet updated their block templates. For example, if there are only 3 mining pools working on block number 200, but the majority of pools are still working on block 199, this would be considered a mining pool conflict. The Mining Pool Monitor features a

tips\_count field that captures this type of conflict. In this example, the tips\_count would return a value of 2.

```
{
  "data" : [ {
    "asset" : "The asset ticker",
    "time" : "The time the response was issued",
    "tips_count" : "The total number of mining pool conflicts",
    "block_hashes_at_tip" : "The number of mining conflicts at the most recent block height ",
    "tips" : [ {
      "last_time" : "The time that this conflicting branch (A) was last updated",
      "height" : "The height that this conflicting branch (A) represents",
      "hash" : "The block hash that this conflicting branch (A) represents",
      "pool_count" : "The total number of mining pools working on branch (A)"
    }, {
      "last_time" : "The time that this conflicting branch (B) was last updated",
      "height" : "The height that this conflicting branch (B) represents",
      "hash" : "The block hash that this conflicting branch (B) represents",
      "pool_count" : "The total number of mining pools working on branch (B)"
  } ],
}
```

The Mining Pool Monitor can also be used to understand when transactions may face settlement issues as a result of stale blocks, a natural byproduct of Nakamoto Consensus that occurs in Bitcoin on a monthly basis. When two different miners successfully mine a block at the same height, these blocks are called stale block candidates. A race condition ensues, where mining pools must pick a branch to mine upon. Once a block is found in one of the conflicting branches, the race ends. The winning branch continues forward, whereas the block on the other branch becomes stale. Those that had transactions siloed in the block that became stale might have to take additional action for their transactions to settle in a timely fashion. All this activity is captured by the Mining Pool Monitor and the block\_hashes\_at\_tip signals when a race condition is taking place.

Beyond the monitoring of mundane network events, the Mining Pool Monitor can also be used to detect and respond to network attacks at the mining pool level. If, for example, a mining pool conflict lasts for multiple blocks, or if there is a considerable gap in block heights, a network attack might be taking place. There have been multiple precedents where 51% of attacks were identified at the mining pool level using block templates data.

For more details on this API, please refer to our [Mining Pool Monitor API Docs](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMiningPoolTipsSummary).

\
