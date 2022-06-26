# Poloniex Supply (USD)

## Definition

The sum USD value held by Poloniex at the end of that day.

| Name                  | MetricID   | Category | Subcategory     | Type | Unit | Interval |
| --------------------- | ---------- | -------- | --------------- | ---- | ---- | -------- |
| Poloniex Supply (USD) | SplyPOLUSD | Exchange | Exchange Supply | Sum  | USD  | 1 day    |

## Details

* Computed as SplyPOLNtv \* PriceUSD.
* All wallets (hot and cold) are considered to count towards the supply held by an exchange.
* This metric should be seen as an underestimation of the actual figure, as our heuristics and sources might not discover all addresses owned by an exchange.

## Asset-Specific Details

* This metric might not be available for all assets. Either that exchange doesn’t support this asset (BitMEX only trades in BTC for example), or we deemed that our coverage of the exchange was not complete enough to release the metric for it.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyPOLUSD" %}
