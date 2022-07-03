# MVRV (Market Cap / Realized Market Cap)

## Definition

The ratio of the sum USD value of the current supply to the sum "realized" USD value of the current supply.

| Name                                    | MetricID   | Category | Subcategory           | Type  | Unit          | Interval |
| --------------------------------------- | ---------- | -------- | --------------------- | ----- | ------------- | -------- |
| MVRV (Market Cap / Realized Market Cap) | CapMVRVCur | Market   | Market Capitalization | Ratio | Dimensionless | 1 day    |

## Details

* Computed as CapMrktCurUSD / CapRealUSD

## Chart

![https://charts.coinmetrics.io/formulas/#580](<../../.gitbook/assets/MVRV (3).png>)

## Asset-Specific Details

* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account, see Realized Cap’s entry for more details

## Release History

* Conceptualized by [Adaptive Capital](https://medium.com/adaptivecapital/bitcoin-market-value-to-realized-value-mvrv-ratio-3ebc914dbaee)
* Released in the 1.0 release of NDP

## Interpretation

Market value to realized value (MVRV) has historically been one of the most reliable on-chain indicators of bitcoin market tops and bottoms. MVRV is calculated by dividing bitcoin’s market capitalization by its [realized capitalization](https://coinmetrics.io/realized-capitalization/). Realized capitalization can also be thought of as a gross approximation of bitcoin’s aggregate cost basis. &#x20;

The intuition behind the creation of this ratio was to divide a price function by a ‘fundamental’ - [Realized Capitalization](caprealusd.md). This gives you a ratio potentially indicating periods of overvaluation (when network value far exceeds its historical relationship to realized cap) and undervaluation.

Historically, a high ratio of market capitalization to realized capitalization has signaled that bitcoin price was near a local maximum, while a low ratio has indicated that price is near a local minimum. The few times that MVRV has dropped below one have historically been some of the best times to buy bitcoin. An increasing MVRV indicates that current sentiment is increasing fast relative to estimated aggregate cost basis, while decreasing MVRV signals the opposite.

## See Also

* [Free Float MVRV](capmvrvff.md)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapMVRVCur" %}
