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
    "status" : "whether the alerting condition is still in place (active), or no longer observed (inactive)",
    "value" : "the value of the alerting metric",
    "threshold" : "the alerting threshold for the metric"
  }
```
