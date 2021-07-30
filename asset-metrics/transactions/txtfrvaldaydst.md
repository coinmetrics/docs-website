# Xfer'd Days Destroyed

## Definitions

The sum of all native units transferred that interval multiplied by the sum of days since those native units were last transferred.

| Name |  MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Xfer'd Days Destroyed | TxTfrValDayDst | Transactions | Transfer value | Product | Dimensionless | 1 day, 1 block |

## Details

* Days destroyed is a measure of time \* money.
* When an unspent output is spent, the time it stayed unspent \(in days\) is multiplied by its value, this metric measures the sum of these coin days spent in a given day.
* Only full days are taken into account \(2.5 days count as 2 days\)

## Asset-Specific Details

* Only available for UTXO chains.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private activity.

## Release History

* Released in the 1.0 release of NDP

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/TxTfrValDayDst" %}



| Asset | Available in [Community](https://docs.coinmetrics.io/api/tiers/community) tier | Available in [Pro](https://docs.coinmetrics.io/api/tiers/pro) tier |
| :--- | :--- | :--- |
| [BCH](https://docs.coinmetrics.io/info/assets/bch) |  |  |
| [BSV](https://docs.coinmetrics.io/info/assets/bsv) |  |  |
| [BTC](https://docs.coinmetrics.io/info/assets/btc) |  |  |
| [BTG](https://docs.coinmetrics.io/info/assets/btg) |  |  |
| [DASH](https://docs.coinmetrics.io/info/assets/dash) |  |  |
| [DCR](https://docs.coinmetrics.io/info/assets/dcr) |  |  |
| [DGB](https://docs.coinmetrics.io/info/assets/dgb) |  |  |
| [DOGE](https://docs.coinmetrics.io/info/assets/doge) |  |  |
| [LTC](https://docs.coinmetrics.io/info/assets/ltc) |  |  |
| [VTC](https://docs.coinmetrics.io/info/assets/vtc) |  |  |
| [XVG](https://docs.coinmetrics.io/info/assets/xvg) |  |  |
| [ZEC](https://docs.coinmetrics.io/info/assets/zec) |  |  |

