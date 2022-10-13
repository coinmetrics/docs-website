# Addr Cnt of Bal > 0

## Definition

The sum count of unique addresses holding any amount of native units as of the end of that day. Only native units are considered (e.g., a 0 ETH balance address with ERC-20 tokens would not be considered).

| Name                | MetricID  | Category  | Subcategory | Type | Unit      | Interval |
| ------------------- | --------- | --------- | ----------- | ---- | --------- | -------- |
| Address Cnt Bal > 0 | AdrBalCnt | Addresses | Balance     | Sum  | Addresses | 1 day    |

## Details

* This metric is the count of how many addresses own any positive amount of the native units.
* The state of the ledger is the one at the last available block for that day.
* Only the native units balance is considered, L2 tokens (ERC-20, etc..) are not taken into account.
* Addresses owning 0 native units are not considered.

## Address-Specific Details

* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account.

## Release History

* Released in the 4.0 release of NDP

## Interpretation

* This metric gives you an indication of how many addresses hold a nonzero balance of the asset; it however imposes no other eligibility test. This means that dust addresses qualify for inclusion. It only counts native units, so an Ethereum address with only ERC20s and no Ether would not count. This metric is predictably cheap to forge, as creating thousands or millions of dust outputs is cheap on many chains. To impose an eligibility hurdle on addresses, consider one of the thresholds in Addresses, with balance, greater than X native units, count.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/AdrBalCnt" %}
