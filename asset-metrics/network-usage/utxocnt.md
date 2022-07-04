# UTXO Cnt

## Definitions

The sum count of unspent transaction outputs that interval.

| Name     | MetricID | Category            | Subcategory                 | Type | Unit | Interval |
| -------- | -------- | ------------------- | --------------------------- | ---- | ---- | -------- |
| UTXO Cnt | UTXOCnt  | Blockchain / ledger | Unspent transaction outputs | Sum  | UTXO | 1 day    |

## Details

* Unspent Transaction Outputs (UTXOs) are cryptoasset balances that have been received by the output addresses listed in a transaction. As transactions are comprised of senders (input addresses) and receivers (output addresses), only the owner of output addresses can spend them after the transaction confirms. Said differently, UTXOs are balances received that have not yet been spent by their owners. Collectively, the UTXO set constitutes the current ownership state of a cryptonetwork. Bitcoin is the first and most predominant network that uses this structure, but there are several other UTXO-based chains.

## **Asset-Specific Details**

* For BTC and derivatives asset, it doesn’t include OP\_RETURN outputs as they are provably unspendable.

## Release History

* Released in the 4.0 release of NDP

## Interpretation

This metric gives a proxy for an asset’s ownership fragmentation. If there’s not a lot of unspent outputs, then there cannot be a lot of onchain owners. More broadly, the UTXO set count is an upper bound estimate on the number of people owning funds on-chain.

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/UTXOCnt" %}
