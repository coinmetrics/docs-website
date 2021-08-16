# Payments \(Xfers\) Below $X, Sum \(USD\)

## Definition

The sum of all payments \(transfers\) that have occured in the measuring interval below a specific USD amount, displayed in units of USD. This family of metric supports $100, $500, $1,000, and $10,000 USD value thresholds.

| Name | MetricID | Category | Subcategory | Type | Unit | Interval |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| XfersBelow $100, Sum \(USD\) | TxTfrValBelUSD100USD | Transactions | Transactions | Sum | USD | 1d |
| XfersBelow $500, Sum \(USD\) | TxTfrValBelUSD500USD | Transactions | Transactions | Sum | USD | 1d |
| XfersBelow $1000, Sum \(USD\) | TxTfrValBelUSD1000USD | Transactions | Transactions | Sum | USD | 1d |
| XfersBelow $10000, Sum \(USD\) | TxTfrValBelUSD10000USD | Transactions | Transactions | Sum | USD | 1d |

## Details

* This metrics shows the sum of all of payments below each of the supported thresholds that have taken place within the measuring interval.
* Payments are defined as transfers \(xfers\) and represent the individual asset transfers _within_ a transaction.
* A transaction may be a collection of transfers which, specially in UTXO-based blockchains, may represent several P2P payments. 
* A cryptoasset exchange, for example, may engage in _transaction batching_ whereby user withdraws are aggregated in a single transaction comprised of multiple outputs. 
* Each of the outputs represents a transfer. And while each transfer \(output\) may be going to different users, they are all processed within the same transaction.
* For this reason, this metric is calculated at the transfer-level so all individual payments are accounted for.
* In this version of this metric, change outputs are not adjusted. This means not only peer-to-peer tranfers are accounted for, but also when a user sends fund to their own wallets.
* For example, if after paying each of the users withdrawing, the exchange still has a remaining balance, the change output is still accounted for in this metric if it falls below the metric's threshold.
* In other words, if the recipients listed in a transaction's output require payments that, when added together, have a value that is _lower_ than the input, a change output that goes back to the sender must be created. In such circumstances, this metric would also account for the change output if it fell under the measuring threshold.

## Example

* Consider that over the past day, only 4 payments have taken place in a network.
  * Payment 1: $300 USD worth of BTC, or 0.0064 BTC
  * Payment 2: $9,000 USD worth of BTC, or 0.19 BTC
  * Payment 3: $400 USD worth of BTC, or 0.0086 BTC
  * Payment 4: $30 USD worth of BTC, or 0.00064 BTC
* In light of the payments above, the results for this family of metrics would be 
  * Xfers Below $100, Sum \(USD\): 
    * $30 USD \(payment 4\)
  * Xfers Below $500, Sum \(USD\):
    * $730 USD \(sum of payment 1 + payment 3 + payment 4\)
  * Xfers Below $1,000, Sum \(USD\):
    * $730 USD \(sum of payment 1 + payment 3 + payment 4\)
  * Xfers Below $10,000, Sum \(USD\):
    * $9,730 USD \(sum of payment 1 + payment 2 + payment 3 + payment 4\)

## Interpretation

* This thresholds in this metric can be used to better understand the type of users interacting with a cryptoasset network.
* For example, if a network is predominantly being used for retail transactions, one would expect the sum of payments under $100 to have a greater aggregate value than payments above $10,000.
* Similarly, it can show the predominance of different types of investors, such the balance between retail and institutional investors within a network. 

## Release History

* Released in the 5.0 release of NDP \(August, 2021\)



