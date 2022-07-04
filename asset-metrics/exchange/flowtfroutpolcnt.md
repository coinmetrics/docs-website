# Poloniex Withdrawal Cnt

## Definition

The sum count of transfers from any address belonging to exchange Poloniex in that interval. If the recipient address also belongs to Poloniex, the transfer is not counted.

| Name                    | MetricID         | Category | Subcategory | Type | Unit         | Interval       |
| ----------------------- | ---------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Poloniex Withdrawal Cnt | FlowTfrOutPOLCnt | Exchange | Withdrawals | Sum  | Native units | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.

## Asset-Specific Details

* For account-based protocols, if both sender and recipient belong to Poloniex, then the transfer is not counted.
* For UTXO-based protocols, this metric applies the following logic:
  * If the input addresses belong to Poloniex, then only the outputs where the address doesn’t belong to Poloniex are counted as transfers from Poloniex.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrOutPOLCnt" %}
