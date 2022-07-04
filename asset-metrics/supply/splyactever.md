# Active Supply (transacted at least once)

## Definition

The sum of unique native units held by accounts that transacted at least once up to that interval. Native units that transacted more than once are only counted once.

| Name                                     | MetricID    | Category | Subcategory   | Type | Unit         | Interval |
| ---------------------------------------- | ----------- | -------- | ------------- | ---- | ------------ | -------- |
| Active Supply (transacted at least once) | SplyActEver | Supply   | Active supply | Sum  | Native units | All time |

## Details

* For UTXO-based protocols, this includes all outputs in the UTXO set not created in mining reward transactions.
* For account-based protocols, this includes the sum of the balances of accounts that were either created outside of token generation events (genesis, mining, etc.), or that had at least one outgoing native unit movement during a token generation event. Any type of movement suffice to mark an account as active (fees, transfers, etc.).

## Asset-Specific Details

* For XRP, escrow transactions are considered as activity, with a last active time at the time of their creation.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Version 4.3 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyActEver" %}
