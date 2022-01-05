---
description: /blockchain
---

# Atlas Overview

Atlas is a blockchain search tool designed to standardize and simplify raw blockchain data. It provides a uniform way to query data from various blockchain full nodes using the double-entry accounting format, thereby bridging the underlying intricacies of different blockchain data models. The basis of Atlas is our Universal Blockchain Data Model (UBDM).

## Asset Coverage

Atlas currently supports the following assets:

| Asset          | Symbol      |
| -------------- | ----------- |
| 0x             | `zrx`       |
| Aave           | `aave`      |
| Audius         | `audio`     |
| Bitcoin        | `btc`       |
| Bitcoin Cash   | `bch`       |
| Binance USD    | `busd`      |
| Cardano\*      | `ada`       |
| Chainlink      | `link`      |
| Compound       | `comp`      |
| Dash           | `dash`      |
| Ethereum       | `eth`       |
| Litecoin       | `ltc`       |
| Huobi USD      | `husd`      |
| Maker          | `mkr`       |
| Paxos Standard | `pax`       |
| Paxos Gold     | `paxg`      |
| Polkadot\*     | `dot`       |
| Polygon (ETH)  | `matic_eth` |
| SushiSwap      | `sushi`     |
| Synthetix      | `snx`       |
| Uniswap        | `uni`       |
| USDC           | `usdc`      |
| USDT (Omni)    | `usdt`      |
| USDT (ETH)     | `usdt_eth`  |
| USDT (TRX)     | `usdt_trx`  |
| WBTC           | `wbtc`      |
| XRP            | `xrp`       |
| Yearn.Finance  | `yfi`       |
| Zcash          | `zec`       |
|                |             |

\*These assets are experimental and offered through [CM Labs](../cm-labs.md)

## Accounts

Accounts in the UBDM can be **User Accounts**, which are addresses that belong to network participants, or **Virtual Accounts**, which denote things like new asset issuance (inflation) and fees. These Virtual Accounts serve to balance transactions and blocks.

### Virtual Accounts

#### Issuance Account

Protocols like Bitcoin subsidize network security for a period of time by issuing new assets to successful miners in so-called _coinbase transactions._ Since new units sent to miners create an imbalance in the ledger, the virtual Issuance Account is debited with every new coinbase transaction. There have been instances where, due to miner error, part of the funds that would have been otherwise fully claimed by a miner are inadvertently locked and irredeemable. In such circumstances, the Issuance Account is credited when units are permanently locked in, or burned.

#### Fees Account

For certain protocols, like Bitcoin, transactions are composed of inputs and outputs. Users pay fees to miners for including their transactions in a block, but that fee is not showcased in the transaction's output list. As a result, there is an imbalance between inputs and outputs (the difference of which being the miner fees), which is only settled when a block containing the transaction is mined. To account for this imbalance, a virtual Fee Account is credited when users pay fees and debited when miners claim these fees by mining a block.

### Non-Transactional Debits and Credits

Even though the overwhelming majority of debits and credits take place within a transaction, some protocols have balance updates that occur outside of transactions (for example, Ethereum blocks rewards are credited implicitly, outside of any transaction). There are also unusual circumstances where a block may carry additional credits and debits so that the ledger can be accurately balanced. For example, the irregular ledger update following Ethereum's notorious DAO hack required us to append additional credits and debits to that block in order for the irregular ledger change to be accounted for.

## Timestamps: Miner Timestamp vs. Consensus Timestamp

The UBDM accounts for two different types of timestamps: miner-reported and consensus.

### Miner Timestamps

The miner timestamp is exactly as it sounds - the timestamp put in the block header by the miner. Most UTXO-based chains do not guarantee that the miner timestamps are accurate or even have to follow the same order as the height. A timestamp for Bitcoin is considered valid if it is greater than the median timestamp of the previous 11 blocks, and less than the network-adjusted time + 2 hours (network-adjusted time is the median of the timestamps returned by all nodes connected to the miner). As a result, block 1 could have a timestamp younger than block 2, which complicates any analysis that requires the correct ordering of transactions.

### Consensus Timestamp

To provide accurate ordering, we employ the concept of a Consensus Timestamp, which has the property of providing the same or partial order over blocks as height (i.e., a block's Consensus Timestamp is always greater than or equal to its parent's). This provides a uniform time series that accurately reflects the ordering of transactions.

## Chain Sequencing

The global sequence number denotes the ordering of a transaction's updates relative to all other balance updates that have taken place up until that point. For example, the very first credit to the miner of the genesis block (the first block to be confirmed in the ledger) for the chain has a `chain_sequence_number` of 0. The operations in the transactions immediately after that, be it a credit or a debit, would have the `chain_sequence_number` of 1. In many ways, this is analogous to the block height (for the block ordering), but we take it a step further with the UBDM and apply the ordering to all operations that have ever taken place.

## Transaction Sequencing

The transaction sequence number serves to order and match sets of credits and debits inside a transaction. If in a single transaction, Alice sent Bob 1 token, then Bob sent Charlie 1 token we would have the following order of events.

{% hint style="info" %}
`transaction_sequence_number=0`

Alice debited by 1 token, Bob credited by 1 token

`transaction_sequence_number=1`

Bob debited by 1 token, Charlie credited by 1 token
{% endhint %}

Beyond ordering, transaction sequence numbers can be used to apply the concepts of sender and receiver because within the same transaction sequence number, _senders_ are the accounts that were debited whereas _receivers_ are the accounts that were credited.

Credits and debits inside a transaction are grouped by transaction sequence number in ascending order and applied to each transaction atomically to reflect the order in which credits and debits occurred in the asset.

### Application to UTXO Transactions

UTXO transactions (used in Bitcoin and derivative assets) are comprised of 2 parts:

* Inputs (debits) which list the previously unspent outputs spent by this transaction\

* Outputs (credits) which list the newly created unspent outputs by this transaction

Since UTXO transactions are applied atomically, all credits and debits have `tx_sequence_number` of 0.

Taking this transaction that pays a fee of 0.25 BTC as an example, we have:

| Inputs               | Outputs                 |
| -------------------- | ----------------------- |
| 50 BTC from 1NA7M... | 105 BTC to 1P3CK...     |
| 50 BTC from 1J27C... | 44.75 BTC to 1NA7Mop... |
| 50 BTC from 1DJ8d... |                         |

```javascript
{  
"transaction_hash": "418b84d7649055411d8be4e241376a93825c1d6248a304ae693060b3007a43f2",  
"balance_updates": [{ 
     "change": "-50.00000000", 
      "account": "1NA7Mopi9b4YhuWSBrB7D4W5XsTY53N1zY", 
      "new_balance": "0.00000000", 
      "previous_balance": "50.00000000", 
      "previous_n_debits": "0", 
      "previous_n_credits": "1", 
      "transaction_sequence_number": "0", 
      "chain_sequence_number": "156700", 
      "previous_credit_height": "35892", 
      "account_creation_height": "35892" 
      }, 
      { 
      "change": "-50.00000000", 
      "account": "1J27CLhDGmm3qBSiVcGxoE3evoSECUREYj", 
      "new_balance": "0.00000000", 
      "previous_balance": "50.00000000", 
      "previous_n_debits": "0", 
      "previous_n_credits": "1", 
      "transaction_sequence_number": "0", 
      "chain_sequence_number": "156701", 
      "previous_credit_height": "13316", 
      "account_creation_height": "13316" 
      }, 
      { 
      "change": "-50.00000000",
      "account": "1DJ8d8gVU5VFGpSjr2AzwS9Jtg5YnyfWQD", 
      "new_balance": "0.00000000", 
      "previous_balance": "50.00000000", 
      "previous_n_debits": "0", 
      "previous_n_credits": "1", 
      "transaction_sequence_number": "0", 
      "chain_sequence_number": "156702", 
      "previous_credit_height": "24451", 
      "account_creation_height": "24451" 
      }, 
      { 
      "change": "105.00000000", 
      "account": "1P3CKNyDEMRKHTDTLPqesYKSzPCo1QUCQK", 
      "new_balance": "555.00000000", 
      "previous_balance": "450.00000000", 
      "previous_n_debits": "1", 
      "previous_n_credits": "2", 
      "transaction_sequence_number": "0", 
      "previous_debit_height": "48243", 
      "chain_sequence_number": "156703", 
      "previous_credit_height": "47494", 
      "account_creation_height": "47041" 
      }, 
      { 
      "change": "44.74000000", 
      "account": "1NA7Mopi9b4YhuWSBrB7D4W5XsTY53N1zY", 
      "new_balance": "44.74000000", 
      "previous_balance": "0.00000000", 
      "previous_n_debits": "1", 
      "previous_n_credits": "1", 
      "transaction_sequence_number": "0", 
      "previous_debit_height": "48890", 
      "chain_sequence_number": "156704", 
      "previous_credit_height": "35892", 
      "account_creation_height": "35892" 
 }, 
 { 
 "change": "0.26000000", 
 "account": "FEES", 
 "new_balance": "0.00000000", 
 "previous_balance": "-0.26000000", 
 "previous_n_debits": "11", 
 "previous_n_credits": "49523", 
 "transaction_sequence_number": "0", 
 "previous_debit_height": "48890", 
 "chain_sequence_number": "156705", 
 "previous_credit_height": "48889", 
 "account_creation_height": "0" 
 } 
 ] 
}
```

## API Endpoints

The Atlas API endpoints are located under the common `/blockchain` prefix. There are four primary data sets returned by the Atlas endpoints:

* [Accounts](accounts.md) `/blockchain/{asset}/accounts`
* [Blocks](blocks/) `/blockchain/{asset}/blocks`
* [Transactions](transactions/) `/blockchain/{asset}/transactions`
* [Balance Updates](balance-updates.md) `/blockchain/{asset}/balance-updates`

These endpoints (with no additional query parameters) return the full list of accounts, blocks, transactions, or balance updates for the asset queried with fields listed in each relevant section that follows. The result can also be filtered for specific accounts or transactions, or for specific start/end times, heights, and chain sequence numbers.

So if you want a list of balance updates for a specific set of Bitcoin accounts, you'd use the `/blockchain/btc/balance-updates` endpoint with the `accounts=` parameter.

### Full Entity Endpoints

There are also two additional endpoints that can be used to get a:

* Single full Block with all Transactions `/blockchain/{asset}/blocks/block_hash`&#x20;
* Single full Transaction with all Balance Updates `/blockchain/{asset}/transactions/transaction_hash`

These endpoints do not support any query parameters and return full block info and full transaction info. The objects returned are the same as those without the full prefix with **additional JSON fields**.

### Sample Queries

* **Accounts info for all accounts created in the blockchain**: /{asset}/accounts
* **Account info for only specified accounts**:  /{asset}/accounts?accounts=account1,account2
* **Block info for all blocks created in the blockchain**: /{asset}/blocks
