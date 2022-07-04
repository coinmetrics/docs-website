# 90 Day Active Supply

## Definition

The sum of unique native units that transacted at least once in the trailing 90 days up to that interval. Native units that transacted more than once are only counted once.

| Name                 | MetricID   | Category | Subcategory | Type | Unit         | Interval |
| -------------------- | ---------- | -------- | ----------- | ---- | ------------ | -------- |
| 90 Day Active Supply | SplyAct90d | Supply   | Active      | Sum  | Native units | 90 days  |

## Details

* For UTXO-based protocols, active supply is considered as the outputs created during the time interval. Mining reward outputs are not considered active. If an address has an output created outside the time interval, and inside the time interval, only the latter output will be considered active.
* For account-based protocols, active supply is the sum of the balances of accounts that were either created outside of token generation events (genesis, mining, etc.) during the considered time interval, or that had at least one native units debit during it. Any type of movement suffice to mark an account as active (fees, transfers, etc.).

## Asset- Specific Details

* For Ripple, escrows are considered active supply, with a last active time at the time of their creation.
* This metric is not available for assets that have full privacy, like Monero and Grin.
* For assets that have opt-in privacy features, like ZCash, we only take the non-private balances into account.

## Release History

* Released in the version 4.9 of Network Data Pro

## Interpretation

This metric tracks the fraction of supply active in the trailing period specified. This allows you to determine how active given tranches of a cryptocurrency are. This is a distinct and harder to forge metric than transactional value (see for instance Transactions, transfers, value, adjusted, USD), which can be increased by a few whales making copious self-sends. In active supply, one’s ability to game the metric is proportional to one’s share of supply. The worst an adversary could do would be to make their fraction of supply appear perpetually active. Active supply cohorts are a popular tool used by traders to access the market-relevant supply of an asset and to ascertain whether a given asset is being used transactionally or as a store of value. Additionally, the longer-term active supply cohorts can be used to derive an estimate of lost coins.

## Availability for Assets&#x20;

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyAct90d" %}
