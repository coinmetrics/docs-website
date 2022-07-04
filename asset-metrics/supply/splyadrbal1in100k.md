# Val in Addrs w/ Bal ≥ .001% of Current Supply

## Definition

The sum of all native units being held in addresses whose balance was at least one in one-hundred-thousandth of the current supply of native units as the end of that day. Only native units are considered \(e.g., an address with less than X ETH but with more than X in ERC-20 tokens would not be considered\).

## Dictionary

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Val in Addrs w/ Bal ≥ .001% of Current Supply | SplyAdrBal1in100K | Supply | Addresses with Balance | Sum | Native units | 1 day |

## Details

* The supply used is SplyCur
* The comparison is done using greater than or equal comparison \(an address owning exactly 1/100,000th of the supply counts towards SplyAdrBal1in100K\)
* For a day D, balances are taken at the end of that day.
* Only native units are taken into account, not L2 tokens.

## Asset-Specific Details

* For XRP, escrows are taken into account.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Released in the version 4.0 of Network Data Pro

## **Availability for Assets**

{% embed url="https://docs.coinmetrics.io/info/metrics/SplyAdrBal1in100K" %}

