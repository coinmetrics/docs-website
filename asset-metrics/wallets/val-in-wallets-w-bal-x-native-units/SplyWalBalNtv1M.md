# Val in Wallets w/ Bal ≥ 1M Native Units

## Definition <a href="#definition" id="definition"></a>

The sum of the supply being held by all wallets whose balance was at least 1M native units. For example, if an asset's current supply is 21M tokens in total, this metric would provide the sum of the balances held by _all_ wallets with a balance greater or equal to 1M units. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## Dictionary <a href="#dictionary" id="dictionary"></a>



| Name                                                          | MetricID        | Category | Subcategory | Type | Unit         | Interval |
| ------------------------------------------------------------- | --------------- | -------- | ----------- | ---- | ------------ | -------- |
| Supply, in wallets with balance, greater than 1M native units | SplyWalBalNtv1M | Wallets  | Balance     | Sum  | Native units | 1 day    |

## Details <a href="#details" id="details"></a>

* Native units represent a cryptoasset's monetary unit. For example, the native unit of Bitcoin is BTC, or bitcoins_._&#x20;
* In order to group addresses together, we employ a clustering methodology based on well-established industry standards.

## Asset-Specific Details <a href="#asset-specific-details" id="asset-specific-details"></a>

* Only native units are taken into account. We do not account for token balances that may be held by the same entity. For example, this metric for ETH would not account for any ERC20 token balance that may be held by the very same address.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History <a href="#release-history" id="release-history"></a>

* Released in version 5.1 of Network Data Pro

## **Availability for Assets** <a href="#availability-for-assets" id="availability-for-assets"></a>

{% embed url="https://docs.coinmetrics.io/info/metrics/SplyWalBalNtv1M" %}
