# Huobi Withdrawal Cnt

## Definition

The sum count of transfers from any address belonging to exchange Huobi in that interval. If the recipient address also belongs to Huobi, the transfer is not counted.

| Name                 | MetricID         | Category | Subcategory | Type | Unit         | Interval       |
| -------------------- | ---------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Huobi Withdrawal Cnt | FlowTfrOutHUOCnt | Exchange | Withdrawals | Sum  | Native units | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.

## Asset-Specific Details

* For account-based protocols, if both sender and recipient belong to Huobi, then the transfer is not counted.
* For UTXO-based protocols, this metric applies the following logic:
  * If the input addresses belong to Huobi, then only the outputs where the address doesn’t belong to Huobi are counted as transfers from Huobi.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrOutHUOCnt" %}
