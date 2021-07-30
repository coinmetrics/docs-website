---
description: /timeseries/asset-metrics
---

# Mean Block Size \(in bytes\)

## Definition

The mean size \(in bytes\) of all blocks created that interval.

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Mean Block Size \(in bytes\) | BlkSizeMeanByte | Network Usage | Blocks | Mean | Bytes | 1 day |

## Details

* Only mainchain \(non-orphaned/uncles\) blocks are counted.
* For chains that use median time, the day is defined using it, otherwise, it’s defined using the block’s timestamps.

## Asset-Specific Details

* This metric is not available for all assets, as some node’s RPC API do not expose the size of the blocks.

## Release History

* Released in the 1.0 release of NDP

## Interpretation

Mean block size is somewhat arbitrary; block count multiplied by mean block size gives you the total data throughput on a blockchain per day. Blockchains with shorter interblock times will often have smaller blocks but may throughput more data than their higher-latency peers.

## Availability for Assets

{% embed url="https://docs.coinmetrics.io/info/metrics/BlkSizeMeanByte" %}



| Asset | Community tier | Professional tier |
| :--- | :---: | :---: |
| [ADA](https://docs.coinmetrics.io/info/assets/ada) | ✓ | ✓ |
| [BCH](https://docs.coinmetrics.io/info/assets/bch) | ✓ | ✓ |
| [BSV](https://docs.coinmetrics.io/info/assets/bsv) | ✓ | ✓ |
| [BTC](https://docs.coinmetrics.io/info/assets/btc) | ✓ | ✓ |
| [BTG](https://docs.coinmetrics.io/info/assets/btg) | ✓ | ✓ |
| [DASH](https://docs.coinmetrics.io/info/assets/dash) | ✓ | ✓ |
| [DCR](https://docs.coinmetrics.io/info/assets/dcr) | ✓ | ✓ |
| [DGB](https://docs.coinmetrics.io/info/assets/dgb) | ✓ | ✓ |
| [DOGE](https://docs.coinmetrics.io/info/assets/doge) | ✓ | ✓ |
| [ETC](https://docs.coinmetrics.io/info/assets/etc) | ✓ | ✓ |
| [ETH](https://docs.coinmetrics.io/info/assets/eth) | ✓ | ✓ |
| [LSK](https://docs.coinmetrics.io/info/assets/lsk) | ✓ | ✓ |
| [LTC](https://docs.coinmetrics.io/info/assets/ltc) | ✓ | ✓ |
| [NEO](https://docs.coinmetrics.io/info/assets/neo) | ✓ | ✓ |
| [PIVX](https://docs.coinmetrics.io/info/assets/pivx) | ✓ | ✓ |
| [VTC](https://docs.coinmetrics.io/info/assets/vtc) | ✓ | ✓ |
| [WAVES](https://docs.coinmetrics.io/info/assets/waves) | ✓ | ✓ |
| [XMR](https://docs.coinmetrics.io/info/assets/xmr) | ✓ | ✓ |
| [XVG](https://docs.coinmetrics.io/info/assets/xvg) | ✓ | ✓ |
| [ZEC](https://docs.coinmetrics.io/info/assets/zec) | ✓ | ✓ |

