# Exchange Withdrawals, Incl EtoE (native units)

## Definition

The sum in native units withdrawn from exchanges that day, including exchange to exchange activity

| Name                                           | MetricID         | Category | Subcategory | Type | Unit         | Interval       |
| ---------------------------------------------- | ---------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Exchange Withdrawals, Incl EtoE (native units) | FlowOutExInclNtv | Exchange | Withdrawals | Sum  | Native units | 1 block, 1 day |

## Details

* This metric captures interactions between users of a cryptoasset and exchanges supporting that market. It excludes inter-exchange activity.
* If a transaction sends 90 units from exchange B to exchange A, it counts towards this metric.
* If a transaction moves 90 units inside exchange A (cold to hot or equivalent), it doesn’t count towards this metric.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowOutExInclNtv" %}
