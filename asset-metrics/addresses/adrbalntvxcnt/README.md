# Addr Cnt of Bal ≥ X (native units)

## Definition

The sum count of unique addresses holding at least X native units as of the end of that day. Only native units are considered (e.g., an address with less than X ETH but with more than X in ERC-20 tokens would not be considered).

| Name                                   | MetricID                                  | Category  | Subcategory | Type | Unit      | Interval |
| -------------------------------------- | ----------------------------------------- | --------- | ----------- | ---- | --------- | -------- |
| Addr Cnt of Bal ≥ 0.001 (native units) | [AdrBalNtv0.001Cnt](adrbalntv0.001cnt.md) | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 0.01 (native units)  | [AdrBalNtv0.01Cnt](adrbalntv0.01cnt.md)   | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 0.1 (native units)   | [AdrBalNtv0.1Cnt](adrbalntv0.1cnt.md)     | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 1 (native units)     | [AdrBalNtv1Cnt](adrbalntv1cnt.md)         | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 10 (native units)    | [AdrBalNtv10Cnt](adrbalntv10cnt.md)       | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 100 (native units)   | [AdrBalNtv100Cnt](adrbalntv100cnt.md)     | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 1K (native units)    | [AdrBalNtv1KCnt](adrbalntv1kcnt.md)       | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 10K (native units)   | [AdrBalNtv10KCnt](adrbalntv10kcnt.md)     | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 100K (native units)  | [AdrBalNtv100KCnt](adrbalntv100kcnt.md)   | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Addr Cnt of Bal ≥ 1M (native units)    | [AdrBalNtv1MCnt](adrbalntv1mcnt.md)       | Addresses | Balance     | Sum  | Addresses | 1 day    |

## Details

* These metrics provide a count of addresses with balance by equal or higher than a native unit threshold.
* The state of the ledger is the one at the last available block for that day.
* Only the native units balance is considered, L2 tokens (ERC-20, etc..) are not taken into account.
* The computation uses greater than or equal comparison: owning exactly 1 native unit qualifies an address for AdrBalNtv1Cnt.

## Asset-Specific Details

* For XRP, escrowed amounts are not taken into account.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## Release History

* Released in the 4.0 release of NDP

## Interpretation

* This is a potent set of metrics which can elucidate the dispersion of ownership of the address space in a cryptocurrency. The trend can demonstrate whether or not a cryptocurrency is in a concentrative or distributive phase. It should be noted that supply is arbitrary, and for large-cap assets varies between tens of millions to hundreds of billions; so unit dispersion is often not directly comparable between chains. Put otherwise: it is cheaper to accumulate addresses with 100 XRP than 100 BTC since those are so different in fiat terms. This metric can also be gamed to a degree by adding dust to many thousands of addresses.
