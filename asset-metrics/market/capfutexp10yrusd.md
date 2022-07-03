# Future Market Cap (USD)

## Definition

The sum USD value of all native units counting the current supply and including those that will be issued over the next 10 years if the current known issuance schedule is followed.

| Name                    | MetricID         | Category | Subcategory           | Type    | Unit | Interval |
| ----------------------- | ---------------- | -------- | --------------------- | ------- | ---- | -------- |
| Future Market Cap (USD) | CapFutExp10yrUSD | Market   | Market Capitalization | Product | USD  | 10 years |

## Details

* Only continuous, predictable issuance is taken into account.
* Only information known at the time for which the metric is computed is used: unpredictable changes in monetary policy are taken into account only when they become effective. ETH’s reward changes from 5 ETH to 3 and from 3 ETH to 2 are not taken into account for values of the metric computed before they became effective. This metric doesn’t add forward knowledge.
* Price used is the daily close.
* The state of the ledger used is the one at the last available block for that day.
* It’s computed as SplyFutExp10yr \* PriceUSD

## Asset-Specific Details

* For ETH/ETC, uncle rate is fixed at 0.90625 uncle per block

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapFutExp10yrUSD" %}
