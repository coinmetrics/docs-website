# Exchange Deposits, Incl EtoE (native units)

## Definition

The sum number of native units sent to exchanges that interval, including exchange to exchange activity.

| Name                                        | MetricID        | Category | Subcategory | Type | Unit         | Interval       |
| ------------------------------------------- | --------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Exchange Deposits, Incl EtoE (native units) | FlowInExInclNtv | Exchange | Deposits    | Sum  | Native units | 1 block, 1 day |

## Details

* This metric captures interactions between users of a cryptoasset and exchanges supporting that market. It excludes inter-exchange activity.

## Examples

* If a transaction sends 90 units from exchange B to exchange A, it counts towards this metric.
* If a transaction moves 90 units inside exchange A (cold to hot or equivalent), it doesn’t count towards this metric.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowInExInclNtv" %}
