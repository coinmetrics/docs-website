---
description: /timeseries/asset-chains
---

# Reorg & Fork Tracker Tracker API Fields

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
