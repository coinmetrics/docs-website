# Exchange Deposits (USD)

The sum USD value sent to exchanges that interval, excluding exchange to exchange activity.

| Name                    | MetricID    | Category | Subcategory | Type | Unit | Interval       |
| ----------------------- | ----------- | -------- | ----------- | ---- | ---- | -------------- |
| Exchange Deposits (USD) | FlowInExUSD | Exchange | Deposits    | Sum  | USD  | 1 block, 1 day |

## Details

* This metric captures interactions between users of a cryptoasset and exchanges supporting that market. It excludes inter-exchange activity.

## Examples

* If a transaction sends 90 units from exchange B to exchange A, it doesn’t count towards this metric.
* If a transaction spends 10 units from exchange A and sends 5 units to exchange B and 5 units to unknown destination, it counts as a 5 units outflow for exchanges overall, 10 units outflow for exchange A, 5 units inflow for exchange B

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowInExUSD" %}
