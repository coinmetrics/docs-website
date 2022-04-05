# Supply Revived in Last 3 Years

## Defintion

The sum of all native units balances last active 3 years ago that became active in this interval.

| Name                           | MetricID   | Category | Subcategory   | Type | Unit         | Interval |
| ------------------------------ | ---------- | -------- | ------------- | ---- | ------------ | -------- |
| Supply Revived in Last 3 Years | SplyRvv3yr | Supply   | Active supply | Sum  | Native units | 3 years  |

## Details

* For UTXO chains, revived supply is considered as the outputs created before the considered time interval and spent at the time of the metric's computation. For example, if an address has one output created inside the time interval, and one output created outside of the time interval, only the latter will be considered revived.
* For account based chains, revived supply is the sum of the balances of accounts that were either created before the considered time interval and that had no activity afterwards, or that had no outgoing native units movement during that period. Any type of movement is sufficient to mark an account as active (fees, transfers, etc.).

## Chart

![https://charts.coinmetrics.io/network-data/#578](../../.gitbook/assets/3\_Year\_Revived\_Supply.png)

## Asset-Specific Details

* This metric is not available for assets that have full privacy, like Monero and Grin.
* For assets that have opt-in privacy features, like ZCash, we only take the non-private balances into account.

## Interpretation

Revived supply gives a more granular look into supply activity. Revived supply is calculated by summing up the amount of supply that has become active after being inactive for at least X days(or years). For example, “3-year revived supply” is the amount of supply reactivated (on a daily basis) after remaining dormant for at least 3 years. In the chart above, you can see that in the past​ 3-year revived supply ​has started to spike towards the tail end of bull runs. This is likely because longer-term holders begin to move BTC to sell as prices grow more tempting

## See Also

* [Supply Revived in Last 5 Years](splyrvv5yr.md)
* [Supply Revived in Last 4 Years](splyrvv4yr.md)
* [Supply Revived in Last 2 Years](splyrvv2yr.md)
* [Supply Revived in Last Year](splyrvv1yr.md)
* [Supply Revived in Last 180 Days](splyrvv180d.md)
* [Supply Revived in Last 90 Days](splyrvv90d.md)
* [Supply Revived in Last 30 Days](splyrvv30d.md)
* [Supply Revived in Last 7 Days](splyrvv7d.md)

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/SplyRvv3yr" %}

