# Val in Wallets w/ Bal ≥ .00000001% of Current Supply

## Definition <a href="#definition" id="definition"></a>

The sum of the supply being held by all wallets whose balance was at least one in ten-billionth (0.0000001%) of an asset's current supply at the end of the measurement interval. For example, if an asset's current supply is 100 tokens in total, this metric would provide the sum of the balances held by _all_ wallets holding at least 0.00000001 units of the token. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## Dictionary <a href="#dictionary" id="dictionary"></a>



| Name                                                 | MetricID         | Category | Subcategory | Type | Unit         | Interval |
| ---------------------------------------------------- | ---------------- | -------- | ----------- | ---- | ------------ | -------- |
| Supply, in wallets with balance, greater than 1in10B | SplyWalBal1in10B | Wallets  | Balance     | Sum  | Native units | 1 day    |

## Details <a href="#details" id="details"></a>

* Current Supply represents all supply that has been issued and can be currently seen on a cryptoasset's ledger. Coin Metrics calls this metric SplyCur.
* In order to group addresses together, we employ a clustering methodology based on well-established industry standards.

## Asset-Specific Details <a href="#asset-specific-details" id="asset-specific-details"></a>

* Only native units are taken into account. We do not account for token balances that may be held by the same entity. For example, this metric for ETH would not account for any ERC20 token balance that may be held by the very same address.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History <a href="#release-history" id="release-history"></a>

* Released in version 5.1 of Network Data Pro

## **Availability for Assets** <a href="#availability-for-assets" id="availability-for-assets"></a>

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyWalBal1in10B" %}
