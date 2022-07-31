---
description: /blockchain/{asset}/transactions
---

# Transactions

Transactions, just like double entry accounting transactions, are groups of balance updates that are ordered within a block.  The **Transactions** endpoint returns a list of accounts, which have the following fields:

| Field                      | Description                                                                                                                                                                                                                                                                 |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| block\_hash                | Hash of the block containing the transaction                                                                                                                                                                                                                                |
| height                     | Height of the block containing the transaction                                                                                                                                                                                                                              |
| transaction\_hash          | Hash of transaction                                                                                                                                                                                                                                                         |
| consensus\_time            | [Consensus timestamp](../../on-chain-data/atlas-overview.md#consensus-timestamp); always increases monotonically                                                                                                                                                            |
| min\_chain sequence number | Starting [sequence number](../../on-chain-data/atlas-overview.md#chain-sequencing) (global ordering of the first update in this transaction relative to all other updates recorded on the ledger up until that point) for the balance updates occurring in this transaction |
| max\_chain sequence number | Last [sequence number ](../../on-chain-data/atlas-overview.md#chain-sequencing)(global ordering of the last update in this transaction relative to all other updates recorded on the ledger up until that point) for the balance updates occurring in this transaction      |
| n\_balance updates         | Number of balance updates                                                                                                                                                                                                                                                   |
| amount                     | Amount of the balance updates                                                                                                                                                                                                                                               |
