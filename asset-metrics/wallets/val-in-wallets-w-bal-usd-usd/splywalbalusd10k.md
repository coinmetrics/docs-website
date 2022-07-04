# Val in Wallets w/ Bal ≥ $10,000 USD

## Definition <a href="#definition" id="definition"></a>

The sum of the supply being held by all wallets whose balance is equivalent to at least $10,000 dollars when priced using the Coin Metrics Reference Rate. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## Dictionary <a href="#dictionary" id="dictionary"></a>

| Name                                               | MetricID         | Category | Subcategory | Type | Unit | Interval |
| -------------------------------------------------- | ---------------- | -------- | ----------- | ---- | ---- | -------- |
| Supply, in wallets with balance, greater than $10K | SplyWalBalUSD10k | Wallets  | Balance     | Sum  | USD  | 1 day    |

## Details <a href="#details" id="details"></a>

* In order to compute this metric, we multiply the balance of all wallets that we have identified in the blockchain by the price of the token. All wallets with a value greater or equal to the USD value of the threshold above are summed and depicted in units of USD.
* Wallets represent groups of addresses that we estimate are owned by the same entity. In order to group addresses together, we employ a clustering methodology based on well-established industry standards.

## Asset-Specific Details <a href="#asset-specific-details" id="asset-specific-details"></a>

* Only native units are taken into account. We do not account for token balances that may be held by the same entity. For example, this metric for ETH would not account for any ERC20 USD balance that may be owned by the very same address.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History <a href="#release-history" id="release-history"></a>

* Released in version 5.1 of Network Data Pro

## **Availability for Assets** <a href="#availability-for-assets" id="availability-for-assets"></a>

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyWalBalUSD10k" %}
