---
description: /blockchain/{asset}/transaction-tracker
---

# Transaction Tracker

The Transaction Tracker enables clients to track the settlement of their transactions in real-time and respond to events that may impact their operations, such as network congestion or attacks.&#x20;

The endpoint was designed to provide settlement intelligence on client transactions, even without the provision of client data. It achieves this by streaming settlement statuses of all transactions in the mempool. As such, users can privately locate their own transactions by consuming the entire feed and filtering their own transactions on their end.

Alternatively, the endpoint also supports `txids` as well as `addresses` as a query parameter, which exclusively returns the settlement statuses of the transactions that match the query parameters. For context, a `txid` is a unique identifier of blockchain transactions and represents the hash of all transaction fields. An `address` is the unique representation of an account on chain. By default the API returns all unconfirmed transactions associated with the address queried.

```
{
  "data" : [ {
    "txid" : "The hash of the transaction",
    "time" : "The time the response was issued",
    "first_seen_time" : "The time the transaction was first seen in the mempool",
    "status" : "The current settlement status of this transaction",
    "status_update_time" : "The time the status was last updated",
    "status_updates" : [ {
      "time" : "The time of the first status update",
      "status" : "The first status update"
    } ],
    "details" : {
      "version" : "The version of this transaction",
      "amount" : "The amount transacted",
      "replace_by_fee_supported" : "a Boolean noting whether RBF1 was used",
      "fee" : "The total fee paid by this transaction’s sender",
      "feerate" : "The feerate of this transaction",
      "mempool_feerate_mean_at_first_seen_time" : "The average feerate when first seen",
      "mempool_feerate_min_at_first_seen_time" : "The min feerate when it was first seen",
      "consensus_size" : "The consensus size of this transaction",
      "physical_size" : "The physical size of this transaction"
    },
    "block_hash": "Optional (returned for CONFIRMED status only): hash of the block in which the transaction was included",
    "height": "Optional (returned for CONFIRMED status only): height of the block in which the transaction was included",
    "n_confirmations": Optional (returned for CONFIRMED status only): number of confirmations of the block in which the transaction was included",
    "mempool_approx_queue_position" : "Optional (returned for UNCONFIRMED status only): Where this transaction sits in the queue of unprocessed transactions",
    "next_block_approx_settlement_probability_pct" : "Optional (returned for UNCONFIRMED status only): The probability that this transaction will be included in the next 2 blocks",
    "geo" : [ {
      "location" : "the location of the node that has witnessed this transaction",
      "seen_time" : "the time at which the node in this location witnessed the transaction"
    } ],
    "inputs":[{
      "address": "List of all addresses that served as an input to the transaction (i.e.: addresses that are sending funds)",
    } ],
    "outputs":[ {
      "address": "List of all addresses that served as an output to the transaction (i.e.: addresses that are receiving funds)",
    } ],
  } ]
```

The `mempool_approx_queue_position` metric showcases the ranking of a transaction relative to all other transactions in the mempool. The production of this metric involves ranking all the transactions in the mempool by fee expenditure and creating a queue. The first transaction in the queue pays the highest feerate in the network and can be expected to settle in the next block.&#x20;

The `next_block_approx_settlement_probability_pct` metric provides an estimate of the likelihood that this transaction will be included in the next 2 blocks of the blockchain. It is calculated following the assumption that miners are motivated to maximize their profits. In essence, FARUM's simulation engine builds a block with the highest-paying transactions in it and assesses the likelihood that it will contain a certain transaction. The 2-block interval accounts for the fact that miners may have already selected the transactions that will be included in the next block.

The `inputs` and `outputs` component of the response are **only available for BTC** currently.

Another critical field of the transaction tracker is the transaction’s `status`. This field enables clients to have granular data on the full lifecycle of their transactions. There are three different statuses that a transaction can support, which are listed below:

**UNCONFIRMED 🟡**

The transaction is still in the mempool and has not been included in a block.

**CONFIRMED** 🟢

The transaction is no longer in the mempool and has been included in a block. When a transaction confirms, the following additional fields are showcased by the Transaction Tracker:

```
  },
    "block_hash" : "The hash of the block containing the transaction",
    "height" : "The height of the block containing the transaction",
    "n_confirmations" : "The number of block confirmations this transaction has attained",
    "replacement_for_txid" : "The previous txid of this transaction. Only relevant when RBF is used "
  }
```

Since confirmation policies vary widely across market participants, the `n_confirmations` field can be used to apply custom confirmation thresholds to a transaction based on risk tolerance.

**ROLLED\_BACK** ⚠️

As covered in the intro, the settlement of transactions in public blockchains can be subjective. Previously confirmed transactions can be sent back to the mempool or rolled back if the blockchain goes through a reorganization event. Rollbacks might be a result of a stale block, which naturally occurs in Bitcoin on a monthly basis, or they may be indicative of network attacks. In such occurrences, clients can use the Key Risk Indicator feed described in subsequent sections to investigate the incident.

#### REMOVED

Transactions can be removed from the mempool through different means. The most common ones are EXPIRY or REPLACED. Based on the network, the mempool stores transactions for different amounts of time. Bitcoin stores transactions in the mempool for 14 days after which the transaction **expires** and it is automatically removed from the mempool. In Bitcoin, transactions can also be replaced via a method known as **replace by fee**. In that instance a new transaction is broadcast that replaces the existing one.

It is also important to note that a `null` return is, in and of itself, a transaction status. If a given `txid` is not in the mempool, it might be indicative of problems in the broadcasting of the transaction. For more details on this API, please refer to our [Transaction Tracker API Docs](https://docs.coinmetrics.io/api/v4#operation/getTransactionTracker).

### Asset Availability <a href="#asset-availability" id="asset-availability"></a>

* Bitcoin (BTC)
* Ethereum (ETH) - Confirmed transactions only

