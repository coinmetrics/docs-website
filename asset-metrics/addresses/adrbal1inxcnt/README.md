# Addr Cnt with ≥ X% Supply

## Definition

The sum count of unique addresses holding at least one in Xth of the current supply of native units as of the end of that day. Only native units are considered \(e.g., an address with less than one ten-billionth ETH but with ERC-20 tokens would not be considered\).

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Addr Cnt with ≥ 0.00000001% Supply | [AdrBal1in10BCnt](adrbal1in10bcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.0000001% Supply | [AdrBal1in1BCnt](adrbal1in1bcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.000001% Supply | [AdrBal1in100MCnt](adrbal1in100mcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.00001% Supply | [AdrBal1in10MCnt](https://docs.coinmetrics.io/info/metrics/AdrBal1in10MCnt) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.0001% Supply | [AdrBal1in1MCnt](https://docs.coinmetrics.io/info/metrics/AdrBal1in1MCnt) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.001% Supply | [AdrBal1in100KCnt](https://docs.coinmetrics.io/info/metrics/AdrBal1in1MCnt) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.01% Supply | [AdrBal1in10KCnt](https://docs.coinmetrics.io/info/metrics/AdrBal1in10KCnt) | Addresses | Balance | Sum | Addresses | 1 day |
| Addr Cnt with ≥ 0.1% Supply | [AdrBal1in1KCnt](https://docs.coinmetrics.io/info/metrics/AdrBal1in1KCnt) | Addresses | Balance | Sum | Addresses | 1 day |

## Details

* These metrics are a breakdown of the addresses with balance by relative ownership of the total current supply
* In this unadjusted version, the total current supply is used.
* The state of the ledger is the one at the last available block for that day.
* Only the native units balance is considered, L2 tokens \(ERC-20, etc..\) are not taken into account.
* The computation uses greater than or equal comparison: owning exactly 1 billionth of the current supply qualifies an address for AdrBal1in1BCnt

## Asset-Specific Details

* For XRP, escrowed amounts are not taken into account for balances but are counted towards total current supply.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account. The shielded balances are taken into account for the supply component of the metric.

## Examples

If the total current supply of the token is 10,000,000,000 units \(10 billion units\):

* Addresses with less than 1 native unit \(or 0.00000001% of supply\) don't appear in any of these metrics
* Addresses with a balance of 1 native unit \(or 0.00000001% of supply\) are counted only in AdrBal1in10BCnt
* Addresses with a balance of 10 native units \(or 0.0000001% of supply\) are counted in AdrBal1in10BCnt and AdrBal1in1BCnt
* Addresses with 10,000,000 native units \(0.1% of supply\) are counted in all of these metrics 

## Release History

* All but AdrBal1in10KCnt and AdrBal1in1KCnt were released in the 4.0 release of NDP
* AdrBal1in10KCnt and AdrBal1in1KCnt were released in the 4.2 release of NDP

## Interpretation

In contrast with Addresses, with balance, greater than X native units, count, this metric seeks to facilitate direct comparisons between blockchains, even if they have widely varying supply counts. This metric allows you to determine how many addresses own a given fraction of supply, rather than a given number of units of supply. Keep in mind that in blockchains where transacting is cheap or free, this metric can be gamed.

