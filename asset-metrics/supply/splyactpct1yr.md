# 1 Year Active Supply %

## Defintion

The percentage of the current supply that has been active in the trailing 1 year up to that day.

| Name                   | MetricID      | Category | Subcategory | Type       | Unit          | Interval |
| ---------------------- | ------------- | -------- | ----------- | ---------- | ------------- | -------- |
| 1 Year Active Supply % | SplyActPct1yr | Supply   | Active      | Percentage | Dimensionless | 1 day    |

## Details

* Computed as SplyAct1yr / SplyCur
* For UTXO chains, active supply is considered as the outputs created during the considered time interval. Mining reward outputs are not considered active. (If an address has an output created outside the time interval, and inside the time interval, only the latter output will be considered active).
* For account based chains, active supply is the sum of the balances of accounts that were either created outside of token generation events (genesis, mining, etc.) during the considered time interval, or that had at least one outgoing native units movement during that time period.

## Chart

![Source: CM Network Data Charts](../../.gitbook/assets/1yr\_Active\_Supply\_\_.png)

## Asset-Specific Details

* For Ripple, escrows are considered active supply, with a last active time at the time of their creation.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Released in the 1.0 release of NDP

## Interpretation

1-year active supply %​ is the percent of total supply that has been transferred on-chain within the last year. As an asset price rises, an increasing amount of dormant supply can start to become active as long-term holders sell or move their native units. ​Some view a high percentage of 1-year active supply in the trailing year as a sign that a price rally is reaching exhaustion. Conversely, when price is low for extended periods of time, 1-year active supply % has dropped historically as investors hold through crypto winters.

## See Also

* [Active Supply (transacted at least once)](https://docs.coinmetrics.io/asset-metrics/supply/splyactever)
* [Supply Revived in Last 90 Days](https://docs.coinmetrics.io/asset-metrics/supply/splyrvv90d#defintion)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyActPct1yr" %}
