# Miner One Hop Rolling Inventory, 30 day (%)

## Definition

The outflow from all addresses within one hop of a mining entity divided by miner revenue, over a rolling window of 30 days.

## Dictionary

| Name                                        | MetricID      | Category | Subcategory | Type  | Unit       | Interval |
| ------------------------------------------- | ------------- | -------- | ----------- | ----- | ---------- | -------- |
| Miner One Hop Rolling Inventory, 30 day (%) | MRI1HopAll30d | Mining   | Flows       | Ratio | Percentage | 30 days  |

## Details

* This metric is computed as FlowMinerOut1HopAllNtv / RevNtv over a rolling window of 30 days

## Asset-Specific Details

* This metric will initially only be available for Bitcoin.

## Release History

* Release Version: NDP-EOD 4.8 (Nov, 2020)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/MRI1HopAll30d" %}
