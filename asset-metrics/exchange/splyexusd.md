# Exchange Supply (USD)

## Definition

The sum USD value of all native units held in hot or cold exchange wallets that day.

| Name                  | MetricID  | Category | Subcategory      | Type | Unit | Interval |
| --------------------- | --------- | -------- | ---------------- | ---- | ---- | -------- |
| Exchange Supply (USD) | SplyExUSD | Supply   | Held on exchange | Sum  | USD  | 1 day    |

## Details

* Computed as SplyExNtv \* PriceUSD
* All wallets (hot and cold) are considered to count towards the supply held by exchanges.
* This metric should be seen as an underestimation of the actual figure, as our heuristics and sources might not discover all addresses owned by exchanges.
* This metric includes the balances of all addresses we have flagged as being controlled by an exchange, even if our coverage of the exchange is not complete.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyExUSD" %}
