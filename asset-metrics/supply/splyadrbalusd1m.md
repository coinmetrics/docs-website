# Val in Addrs w/ Bal ≥ $1M \(native units\)

## Definition

The sum of all native units being held in addresses whose balance was $1M or greater at the end of that day. Only native units are considered \(e.g., an address with less than X ETH but with more than X in ERC-20 tokens would not be considered\).

## Dictionary

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Val in Addrs w/ Bal ≥ $1M USD | SplyAdrBalUSD1M | Supply | Addresses with Balance | Sum | Native units | 1 day |

## Details

* This metric breaks down the supply of an asset by the USD balance of addresses owning it.
* For a day D, balances are taken at the end of that day, the price used it the close price for that day too.
* Only native units are taken into account, not L2 tokens.
* The comparison is done using greater than or equal comparison \(an address owning exactly $1M counts towards SplyAdrBalUSD1M\).

## Asset-Specific Details

* For Ripple, escrows are taken into account.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/SplyAdrBalUSD1M" %}



