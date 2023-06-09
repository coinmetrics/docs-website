# Val in Wallets w/ Bal ≥ .001% of Current Supply

## Definition

The sum of the supply being held by all wallets whose balance was at least one in one-hundred-thousandth (0.001%) of an asset's current supply at the end of the measurement interval. For example, if an asset's current supply is 100 tokens in total, this metric would provide the sum of the balances held by _all_ wallets holding at least 0.001 units of the token. Wallets represent groups of addresses that we estimate are owned by the same entity. They provide a better proxy for user behavior since users often own more than one blockchain address.

## Dictionary

<table data-header-hidden><thead><tr><th width="222">Name</th><th width="279">MetricID</th><th>Category</th><th>Subcategory</th><th>Type</th><th>Unit</th><th>Interval</th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Subcategory</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Supply, in wallets with balance, greater than 1in100K</td><td>SplyWalBal1in100k</td><td>Wallets</td><td>Balance</td><td>Sum</td><td>Native units</td><td>1 day</td></tr></tbody></table>

## Details

* Current Supply represents all supply that has been issued and can be currently seen on a cryptoasset's ledger. Coin Metrics calls this metric SplyCur.
* In order to group addresses together, we employ a clustering methodology based on well-established industry standards.&#x20;

## Asset-Specific Details

* Only native units are taken into account. We do not account for token balances that may be held by the same entity. For example, this metric for ETH would not account for any ERC20 token balance that may be held by the very same address.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Released in version 5.1 of Network Data Pro

## **Availability for Assets**

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyWalBal1in100k" %}
