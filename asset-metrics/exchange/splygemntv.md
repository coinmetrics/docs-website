# Gemini Supply (native units)

## Definition

The sum in native units held by Gemini at the end of that interval.

| Name                         | MetricID   | Category | Subcategory     | Type | Unit         | Interval |
| ---------------------------- | ---------- | -------- | --------------- | ---- | ------------ | -------- |
| Gemini Supply (native units) | SplyGEMNtv | Exchange | Exchange Supply | Sum  | Native units | 1 day    |

## Details

* All wallets (hot and cold) are considered to count towards the supply held by an exchange.
* This metric should be seen as an underestimation of the actual figure, as our heuristics and sources might not discover all addresses owned by an exchange.

## Asset-Specific Details

* This metric might not be available for all assets. Either that exchange doesn’t support this asset (BitMEX only trades in BTC for example), or we deemed that our coverage of the exchange was not complete enough to release the metric for it.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyGEMNtv" %}
