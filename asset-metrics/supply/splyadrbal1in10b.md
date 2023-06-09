# Val in Addrs w/ Bal ≥ .00000001% of Current Supply

## Definition

The sum of all native units being held in addresses whose balance was at least one in ten-billionth of the current supply of native units as the end of that day. Only native units are considered (e.g., an address with less than X ETH but with more than X in ERC-20 tokens would not be considered).

## Dictionary

<table data-header-hidden><thead><tr><th>Name</th><th width="160">MetricID</th><th>Category</th><th>Subcategory</th><th>Type</th><th>Unit</th><th>Interval</th></tr></thead><tbody><tr><td>Name</td><td>MetricID</td><td>Category</td><td>Subcategory</td><td>Type</td><td>Unit</td><td>Interval</td></tr><tr><td>Val in Addrs w/ Bal ≥ .00000001% of Current Supply</td><td>SplyAdrBal1in10B</td><td>Supply</td><td>Addresses with Balance</td><td>Sum</td><td>Native units</td><td>1 day</td></tr></tbody></table>

## Details

* The supply used is SplyCur
* The comparison is done using greater than or equal comparison (an address owning exactly 1/10,000,000,000th of the supply counts towards SplyAdrBal1in10B)
* For a day D, balances are taken at the end of that day.
* Only native units are taken into account, not L2 tokens.

## Asset-Specific Details

* For XRP, escrows are taken into account.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Released in the version 4.0 of Network Data Pro

## **Availability for Assets**

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyAdrBal1in10B" %}
