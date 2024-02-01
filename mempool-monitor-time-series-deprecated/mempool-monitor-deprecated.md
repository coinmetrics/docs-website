---
description: /timeseries/mempool-feerates
---

# Mempool Monitor - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

## Overview

The Mempool Monitor provides a full breakdown of what other network participants are willing to pay to have their transactions settled, thereby enabling precise fee estimation and settlement prediction.

### Asset Availability

Bitcoin (BTC)

## API Fields

Blockchain networks vary widely in how they price transaction fees. In Bitcoin, users denote transaction fees in feerate, a monetary unit that is measured using the smallest denomination of BTC, the satoshi. In order to calculate a transaction’s total fee expenditure, wallets multiply the feerate by the size of the transaction, either in bytes or virtual bytes (a Bitcoin-specific size notation). As such, larger transactions cost more since every byte needs to be paid for.

In order to better understand the concept of feerates, consider a simple transaction with 1 input and 2 outputs, which has a size of 226 bytes. If a minimum feerate of 8 satoshis per virtual byte is required for this transaction to be included in the next block, the total fee expenditure would be 1,808 (226 x 8) satoshis, or roughly $0.42 USD at the time of writing.

FARUM’s Mempool Monitor provides a full breakdown of what other network participants are willing to pay to have their transactions settled, thereby enabling precise fee estimation and settlement prediction. The API showcases all feerate levels that have corresponding transactions in the mempool. For each feerate level, the total number of mempool transactions, as well as their size, are monitored.

```
{
  "data" : [ {
    "asset" : "The asset ticker",
    "time" : "The time the response was issued", 
    "feerates" : [ {
      "feerate" : "1",
      "count" : "The total number of transactions paying 1 satoshi per virtual byte", 
      "consensus_size" : "The size of all of transactions paying this feerate", 
      "fees" : "The sum of fees of all of transactions paying this feerate",
      "physical_size" : "The physical size of all transactions paying this feerate. This number will determine how much storage is taken up by transactions in a node's mempool."
    }, {
      "feerate" : "2",
      "count" : "The total number of transactions paying 2 satoshis per virtual byte", 
      "consensus_size" : "The size of all of transactions paying this feerate", 
      "fees" : "The sum of fees of all of transactions paying this feerate",
      "physical_size" : "The physical size of all transactions paying this feerate. This number will determine how much storage is taken up by transactions in a node's mempool."
    }, {
      "feerate" : "n",
      "count" : "The total number of transactions paying n satoshis per virtual byte", 
      "consensus_size" : "The size of all of transactions paying this feerate", 
      "fees" : "The sum of fees of all of transactions paying this feerate",
      "physical_size" : "The physical size of all transactions paying this feerate. This number will determine how much storage is taken up by transactions in a node's mempool."
    } ] 
  }
```

For more details on this API, please refer to our [Mempool Monitor API Docs](https://docs.coinmetrics.io/api/v4#operation/getMempoolFeerates).
