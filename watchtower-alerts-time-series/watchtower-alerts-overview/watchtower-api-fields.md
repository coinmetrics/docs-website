---
description: https://api.coinmetrics.io/v4/timeseries/asset-alerts
---

# WatchTower API Fields

The following alerting fields are currently provided via the Network Alerts API endpoint:

```
{
  "data" : [ {
    "asset" : "the ticker of the asset monitored",
    "time" : "the time the alert was issued",
    "alert" : "the Alert ID",
    "block_height": "Optional: Returns the block height at which the alert tirggered, if the alert is calculated on a block by block basis. Otherwise this field is omitted from the response.",
    "status" : "whether the alerting condition is still in place (active), or no longer observed (inactive)",
    "value" : "the value of the alerting metric",
    "threshold" : "the alerting threshold for the metric"
  }
```
