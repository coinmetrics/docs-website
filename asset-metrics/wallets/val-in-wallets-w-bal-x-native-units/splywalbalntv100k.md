# Val in Wallets w/ Bal ≥ 100k Native Units

## Definition <a href="#definition" id="definition"></a>

The sum of the supply being held by all wallets whose balance was at least 100k native units. For example, if an asset's current supply is 21M tokens in total, this metric would provide the sum of the balances held by _all_ wallets with a balance greater or equal to 100k units. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## Dictionary <a href="#dictionary" id="dictionary"></a>



<table data-header-hidden><thead><tr><th width="222">Name</th><th width="185">MetricID</th><th width="196">Category</th><th>Subcategory</th><th>Type</th><th>Unit</th><th>Interval</th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Subcategory</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Supply, in wallets with balance, greater than 100k native units</td><td>SplyWalBalNtv100k</td><td>Wallets</td><td>Balance</td><td>Sum</td><td>Native units</td><td>1 day</td></tr></tbody></table>

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

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyWalBalNtv100k" %}
