# Gemini Deposit Cnt

## Definition

The sum count of transfers to any address belonging to exchange Gemini in that interval. If the sender address also belongs to Gemini, the transfer is not counted.

| Name               | MetricID        | Category | Subcategory | Type | Unit         | Interval       |
| ------------------ | --------------- | -------- | ----------- | ---- | ------------ | -------------- |
| Gemini Deposit Cnt | FlowTfrInGEMCnt | Exchange | Deposits    | Sum  | Native units | 1 block, 1 day |

## Details

* Coinbase (i.e., miner reward) transactions are not counted.

## Asset-Specific Details

* For UTXO-based protocols, this metric does not count change outputs:
  * If the input addresses belong to Gemini, then the outputs belonging to Gemini are not counted as transfers to Gemini.
* For account-based protocols, if both sender and recipient belong to Gemini, then the transfer is not counted.

## Release History

* Version 4.2 of CM Network Data Pro Daily Macro (End of Day)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/FlowTfrInGEMCnt" %}
