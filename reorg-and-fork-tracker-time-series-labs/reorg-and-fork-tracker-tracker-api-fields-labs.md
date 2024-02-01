---
description: /timeseries/asset-chains
---

# Reorg & Fork Tracker Tracker API Fields - Labs

<mark style="color:orange;">**THIS ENDPOINT IS DESIGNATED AS A LABS ENDPOINT.**</mark>

<mark style="color:orange;">Our Labs offerings are a place for our pioneering team to experiment. Here, you'll find associate passion projects, fun prototypes, test products/features and cutting edge efforts that are experimental in nature. Many of our most popular commercial products have their roots in these innovative, community-first efforts.</mark>\ <mark style="color:orange;">While CM Labs products and features are very cool, for one reason or another, we are not quite ready to incorporate them into our mainstream product offerings.</mark>

For more information on CM Labs offerings please check out our [CM Labs information](https://docs.coinmetrics.io/cm-labs).

The Reorg & Fork Tracker supports the following fields:

```
{
  "data": [
    {
      "asset": "the ticker that represents a network's base asset",
      "time": "current time in UTC",
      "chains_count": "the number of blockchain versions observed",
      "blocks_count_at_tip": "the number of distinct blocks at the tip of the chain",
      "reorg": "a boolean that returns true if a reorg has occurred,
      "reorg_depth": "the depth of the most recent reorg",
      "chains": "details on the competing blockchain versions" [
        [
          {
            "hash": "the hash of branch A",
            "height": "the current height of branch A",
            "time": "the time of the last update on this branch"
          }
        ],
        [
          {
            "hash": "the hash of branch A",
            "height": "the current height of branch A",
            "time": "the time of the last update on this branch"
          }
        ]
      ]
    }
  ],
  "next_page_token": "token of the next page",
  "next_page_url": "URL of the next page"
}

```
