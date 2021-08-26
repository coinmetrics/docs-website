# Addr Cnt of Bal ≥ $X

## Definition

The sum count of unique addresses holding at least X dollar's worth of native units as of the end of that day. Only native units are considered \(e.g., an address with less than X dollar's worth of ETH but with more than X dollar's worth of ERC-20 tokens would not be considered\).

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Address Cnt of Bal ≥ $1 | [AdrBalUSD1Cnt](adrbalusd1cnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $10 | [AdrBalUSD10Cnt](adrbalusd10cnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $100 | [AdrBalUSD100Cnt](adrbalusd100cnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $1K | [AdrBalUSD1KCnt](adrbalusd1kcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $10K | [AdrBalUSD10KCnt](adrbalusd10kcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $100K | [AdrBalUSD100KCnt](adrbalusd100kcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $1M | [AdrBalUSD1MCnt](adrbalusd1mcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |
| Address Cnt of Bal ≥ $10M | [AdrBalUSD10MCnt](adrbalusd10mcnt.md) | Addresses | Balance | Sum | Addresses | 1 day |

## Details

* These metrics are a breakdown of the addresses with balance count with USD balance thresholds.
* The state of the ledger is the one at the last available block for that day.
* The price used is the daily close price.
* Only the native units balance is considered, L2 tokens \(ERC-20, etc..\) are not taken into account.
* The computation uses greater than or equal comparison: owning exactly $1 qualifies an address for AdrBalUSD1Cnt.

## Asset-Specific Details

* For XRP, escrowed amounts are not taken into account.
* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activities into account.

## Release History

* Released in the 4.0 release of NDP

## Interpretation

This metric standardizes wealth cohorts across multiple blockchains for easy comparison, although differences in address creation must be taken into account. Some wallets in UTXO chains tend to fragment user balances into multiple addresses to preserve privacy. Note that this metric is sensitive to changes in unit price; common address sizes combined with price changes can lead to large numbers of addresses hitting a new threshold at the same time. This can lead to sharp discontinuities in the metric. For a purer measure of holder dispersion \(albeit not as directly comparable\), see addresses, with balance, greater than X native units, count.

## Availability for Assets

| Asset | Community tier | Professional tier |
| :--- | :---: | :---: |
| [AAVE](https://docs.coinmetrics.io/info/assets/aave) |  | ✓ |
| [ADA](https://docs.coinmetrics.io/info/assets/ada) |  | ✓ |
| [ANT](https://docs.coinmetrics.io/info/assets/ant) |  | ✓ |
| [BAL](https://docs.coinmetrics.io/info/assets/bal) |  | ✓ |
| [BAT](https://docs.coinmetrics.io/info/assets/bat) |  | ✓ |
| [BCH](https://docs.coinmetrics.io/info/assets/bch) |  | ✓ |
| [BNB](https://docs.coinmetrics.io/info/assets/bnb) |  | ✓ |
| [BSV](https://docs.coinmetrics.io/info/assets/bsv) |  | ✓ |
| [BTC](https://docs.coinmetrics.io/info/assets/btc) |  | ✓ |
| [BTG](https://docs.coinmetrics.io/info/assets/btg) |  | ✓ |
| [BUSD](https://docs.coinmetrics.io/info/assets/busd) |  | ✓ |
| [COMP](https://docs.coinmetrics.io/info/assets/comp) |  | ✓ |
| [CRO](https://docs.coinmetrics.io/info/assets/cro) |  | ✓ |
| [CRV](https://docs.coinmetrics.io/info/assets/crv) |  | ✓ |
| [CVC](https://docs.coinmetrics.io/info/assets/cvc) |  | ✓ |
| [DAI](https://docs.coinmetrics.io/info/assets/dai) |  | ✓ |
| [DASH](https://docs.coinmetrics.io/info/assets/dash) |  | ✓ |
| [DCR](https://docs.coinmetrics.io/info/assets/dcr) |  | ✓ |
| [DGB](https://docs.coinmetrics.io/info/assets/dgb) |  | ✓ |
| [DGX](https://docs.coinmetrics.io/info/assets/dgx) |  | ✓ |
| [DOGE](https://docs.coinmetrics.io/info/assets/doge) |  | ✓ |
| [DRGN](https://docs.coinmetrics.io/info/assets/drgn) |  | ✓ |
| [ELF](https://docs.coinmetrics.io/info/assets/elf) |  | ✓ |
| [ENG](https://docs.coinmetrics.io/info/assets/eng) |  | ✓ |
| [EOS\_ETH](https://docs.coinmetrics.io/info/assets/eos_eth) |  | ✓ |
| [ETC](https://docs.coinmetrics.io/info/assets/etc) |  | ✓ |
| [ETH](https://docs.coinmetrics.io/info/assets/eth) |  | ✓ |
| [ETHOS](https://docs.coinmetrics.io/info/assets/ethos) |  | ✓ |
| [FTT](https://docs.coinmetrics.io/info/assets/ftt) |  | ✓ |
| [FUN](https://docs.coinmetrics.io/info/assets/fun) |  | ✓ |
| [FXC](https://docs.coinmetrics.io/info/assets/fxc) |  | ✓ |
| [GAS](https://docs.coinmetrics.io/info/assets/gas) |  | ✓ |
| [GNO](https://docs.coinmetrics.io/info/assets/gno) |  | ✓ |
| [GNT](https://docs.coinmetrics.io/info/assets/gnt) |  | ✓ |
| [GUSD](https://docs.coinmetrics.io/info/assets/gusd) |  | ✓ |
| [HEDG](https://docs.coinmetrics.io/info/assets/hedg) |  | ✓ |
| [HT](https://docs.coinmetrics.io/info/assets/ht) |  | ✓ |
| [HUSD](https://docs.coinmetrics.io/info/assets/husd) |  | ✓ |
| [KNC](https://docs.coinmetrics.io/info/assets/knc) |  | ✓ |
| [LEND](https://docs.coinmetrics.io/info/assets/lend) |  | ✓ |
| [LEO\_ETH](https://docs.coinmetrics.io/info/assets/leo_eth) |  | ✓ |
| [LINK](https://docs.coinmetrics.io/info/assets/link) |  | ✓ |
| [LOOM](https://docs.coinmetrics.io/info/assets/loom) |  | ✓ |
| [LSK](https://docs.coinmetrics.io/info/assets/lsk) |  | ✓ |
| [LTC](https://docs.coinmetrics.io/info/assets/ltc) |  | ✓ |
| [MAID](https://docs.coinmetrics.io/info/assets/maid) |  | ✓ |
| [MANA](https://docs.coinmetrics.io/info/assets/mana) |  | ✓ |
| [MCO](https://docs.coinmetrics.io/info/assets/mco) |  | ✓ |
| [MKR](https://docs.coinmetrics.io/info/assets/mkr) |  | ✓ |
| [NEO](https://docs.coinmetrics.io/info/assets/neo) |  | ✓ |
| [NXM](https://docs.coinmetrics.io/info/assets/nxm) |  | ✓ |
| [OMG](https://docs.coinmetrics.io/info/assets/omg) |  | ✓ |
| [PAX](https://docs.coinmetrics.io/info/assets/pax) |  | ✓ |
| [PAXG](https://docs.coinmetrics.io/info/assets/paxg) |  | ✓ |
| [PAY](https://docs.coinmetrics.io/info/assets/pay) |  | ✓ |
| [POLY](https://docs.coinmetrics.io/info/assets/poly) |  | ✓ |
| [POWR](https://docs.coinmetrics.io/info/assets/powr) |  | ✓ |
| [PPT](https://docs.coinmetrics.io/info/assets/ppt) |  | ✓ |
| [QASH](https://docs.coinmetrics.io/info/assets/qash) |  | ✓ |
| [REN](https://docs.coinmetrics.io/info/assets/ren) |  | ✓ |
| [RENBTC](https://docs.coinmetrics.io/info/assets/renbtc) |  | ✓ |
| [REP](https://docs.coinmetrics.io/info/assets/rep) |  | ✓ |
| [SAI](https://docs.coinmetrics.io/info/assets/sai) |  | ✓ |
| [SNT](https://docs.coinmetrics.io/info/assets/snt) |  | ✓ |
| [SNX](https://docs.coinmetrics.io/info/assets/snx) |  | ✓ |
| [SRM](https://docs.coinmetrics.io/info/assets/srm) |  | ✓ |
| [SUSHI](https://docs.coinmetrics.io/info/assets/sushi) |  | ✓ |
| [SWRV](https://docs.coinmetrics.io/info/assets/swrv) |  | ✓ |
| [TRX\_ETH](https://docs.coinmetrics.io/info/assets/trx_eth) |  | ✓ |
| [TUSD](https://docs.coinmetrics.io/info/assets/tusd) |  | ✓ |
| [UMA](https://docs.coinmetrics.io/info/assets/uma) |  | ✓ |
| [UNI](https://docs.coinmetrics.io/info/assets/uni) |  | ✓ |
| [USDC](https://docs.coinmetrics.io/info/assets/usdc) |  | ✓ |
| [USDK](https://docs.coinmetrics.io/info/assets/usdk) |  | ✓ |
| [USDT](https://docs.coinmetrics.io/info/assets/usdt) |  | ✓ |
| [USDT\_ETH](https://docs.coinmetrics.io/info/assets/usdt_eth) |  | ✓ |
| [USDT\_TRX](https://docs.coinmetrics.io/info/assets/usdt_trx) |  | ✓ |
| [VTC](https://docs.coinmetrics.io/info/assets/vtc) |  | ✓ |
| [WBTC](https://docs.coinmetrics.io/info/assets/wbtc) |  | ✓ |
| [WETH](https://docs.coinmetrics.io/info/assets/weth) |  | ✓ |
| [WNXM](https://docs.coinmetrics.io/info/assets/wnxm) |  | ✓ |
| [WTC](https://docs.coinmetrics.io/info/assets/wtc) |  | ✓ |
| [XAUT](https://docs.coinmetrics.io/info/assets/xaut) |  | ✓ |
| [XLM](https://docs.coinmetrics.io/info/assets/xlm) |  | ✓ |
| [XRP](https://docs.coinmetrics.io/info/assets/xrp) |  | ✓ |
| [XTZ](https://docs.coinmetrics.io/info/assets/xtz) |  | ✓ |
| [XVG](https://docs.coinmetrics.io/info/assets/xvg) |  | ✓ |
| [YFI](https://docs.coinmetrics.io/info/assets/yfi) |  | ✓ |
| [ZEC](https://docs.coinmetrics.io/info/assets/zec) |  | ✓ |
| [ZRX](https://docs.coinmetrics.io/info/assets/zrx) |  | ✓ |

