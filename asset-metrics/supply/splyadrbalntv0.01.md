# Val in Addrs w/ Bal ≥ .01 (native units)

## Definition

The sum of all native units being held in addresses whose balance was 0.01 native units or greater at the end of that day. Only native units are considered (e.g., an address with less than X ETH but with more than X in ERC-20 tokens would not be considered).

| Name                                     | MetricID          | Category | Subcategory            | Type | Unit         | Interval |
| ---------------------------------------- | ----------------- | -------- | ---------------------- | ---- | ------------ | -------- |
| Val in Addrs w/ Bal ≥ .01 (native units) | SplyAdrBalNtv0.01 | Supply   | Addresses with Balance | Sum  | Native units | 1 day    |

## Details

* This metric breaks down the supply of an asset by the balance of addresses owning it.
* Only native units are taken into account, not L2 tokens.
* The comparison is done using greater than or equal comparison (an address owning exactly 0.01 native unit counts towards SplyAdrBalNtv0.01).

## Asset-Specific Details

* For Ripple, escrows are taken into account.
* This metric is not available for assets that have full privacy, like Monero and Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.
* For DOT, the address [balance minimum](https://support.polkadot.network/support/solutions/articles/65000168651-what-is-the-existential-deposit-) is 1 DOT. As such, SplyAdrBalNtv0.01 will be the same as SplyAdrBalNtv1.&#x20;

## Release History

Released in the 4.0 release of NDP

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/SplyAdrBalNtv0.01" %}
