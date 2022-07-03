# Active Market Cap (1yr) (USD)

## Definition

The sum USD value of all active native units in the last year. Native units that transacted more than once are only counted once.

| Name                          | MetricID     | Category | Subcategory           | Type    | Unit | Interval |
| ----------------------------- | ------------ | -------- | --------------------- | ------- | ---- | -------- |
| Active Market Cap (1yr) (USD) | CapAct1yrUSD | Market   | Market Capitalization | Product | USD  | 1 year   |

## Details

* The state of the ledger is the one at the last available block for that day.
* Only the native units balance is considered, on-top tokens (e.g., ERC-20) are not included.
* Addresses owning 0 native units are not considered.
* For UTX-based protocols, last activity is the date of creation of the output. Mining reward outputs are not considered active.
* For account-based protocols, last activity is defined as either the time of the last debit of native units from this account, or the time at which it was created (if that creation wasn’t due to a genesis event or mining).

## Asset-Specific Details

* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Version 1.0 of CM Network Data Pro Daily Macro (End of Day)

## Interpretation

In contrast with Capitalization, realized, USD,this metric counts as valid on the fraction of supply which has moved in the prior 12 months. The intuition is to devise a measure of the economic significance of liquid and market-available supply, as evidenced by units that have made recent on-chain transactions. This metric can be volatile as large tranches of supply fall out of the eligibility window or as large sections move for the first time in over a year.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapAct1yrUSD" %}
