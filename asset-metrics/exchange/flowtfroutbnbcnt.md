# Binance Withdrawal Cnt

## Definition

The sum count of transfers from any address belonging to exchange Binance in that interval. If the recipient address also belongs to Binance, the transfer is not counted.

| Name                   | MetricID         | Category | Subcategory | Type | Unit         | Interval       |
| ---------------------- | ---------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Binance Withdrawal Cnt | FlowTfrOutBNBCnt | Exchange | Withdrawals | Sum  | Native units | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.

## Asset-Based Details

* For account-based protocols, if both sender and recipient belong to Binance, then the transfer is not counted.
* For UTXO-based protocols, this metric applies the following logic:
  * If the input addresses belong to Binance, then only the outputs where the address doesn’t belong to Binance are counted as transfers from Binance.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrOutBNBCnt" %}
