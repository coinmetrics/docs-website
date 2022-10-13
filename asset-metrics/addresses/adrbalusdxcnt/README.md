# Addr Cnt of Bal ≥ $X

## Definition

The sum count of unique addresses holding at least X dollar's worth of native units as of the end of that day. Only native units are considered (e.g., an address with less than X dollar's worth of ETH but with more than X dollar's worth of ERC-20 tokens would not be considered).

| Name                       | MetricID                                | Category  | Subcategory | Type | Unit      | Interval |
| -------------------------- | --------------------------------------- | --------- | ----------- | ---- | --------- | -------- |
| Address Cnt of Bal ≥ $1    | [AdrBalUSD1Cnt](adrbalusd1cnt.md)       | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $10   | [AdrBalUSD10Cnt](adrbalusd10cnt.md)     | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $100  | [AdrBalUSD100Cnt](adrbalusd100cnt.md)   | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $1K   | [AdrBalUSD1KCnt](adrbalusd1kcnt.md)     | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $10K  | [AdrBalUSD10KCnt](adrbalusd10kcnt.md)   | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $100K | [AdrBalUSD100KCnt](adrbalusd100kcnt.md) | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $1M   | [AdrBalUSD1MCnt](adrbalusd1mcnt.md)     | Addresses | Balance     | Sum  | Addresses | 1 day    |
| Address Cnt of Bal ≥ $10M  | [AdrBalUSD10MCnt](adrbalusd10mcnt.md)   | Addresses | Balance     | Sum  | Addresses | 1 day    |

## Details

* These metrics are a breakdown of the addresses with balance count with USD balance thresholds.
* The state of the ledger is the one at the last available block for that day.
* The price used is the daily close price.
* Only the native units balance is considered, L2 tokens (ERC-20, etc..) are not taken into account.
* The computation uses greater than or equal comparison: owning exactly $1 qualifies an address for AdrBalUSD1Cnt.

## Asset-Specific Details

* For XRP, escrowed amounts are not taken into account.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## Release History

* Released in the 4.0 release of NDP

## Interpretation

* This metric standardizes wealth cohorts across multiple blockchains for easy comparison, although differences in address creation must be taken into account. Some wallets in UTXO chains tend to fragment user balances into multiple addresses to preserve privacy. Note that this metric is sensitive to changes in unit price; common address sizes combined with price changes can lead to large numbers of addresses hitting a new threshold at the same time. This can lead to sharp discontinuities in the metric. For a purer measure of holder dispersion (albeit not as directly comparable), see addresses, with balance, greater than X native units, count.

