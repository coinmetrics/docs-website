---
description: '/blockchain/{asset}/blocks/{block_hash}/transactions/{transaction_hash}'
---

# Full Transaction Info for Block

Adding a `block_hash`and a `transaction_hash`the prefix returns a block info and transaction info for a single transaction, including all  balance updates for that transaction. 

| Field | Description |
| :--- | :--- |
| block\_hash | Hash of that block \(unique per block\) |
| parent\_block\_hash | Hash of the parent block \(set to a string of 65 zeros for Genesis blocks\) |
| height | Height of that block \(number of confirmed blocks since Genesis block\) |
| transaction\_hash | Hash of transaction |
| consensus\_time | [Consensus timestamp](../../atlas-overview.md#consensus-timestamp); always increases monotonically |
| miner\_time | [Miner/producer timestamp](../../atlas-overview.md#miner-timestamps) |
| n\_transactions | Number of transactions |
| n\_balance updates | Number of balance updates |
| difficulty | Difficulty of the block |
| physical\_size | The physical size of a block in bytes |
| consensus\_size | The stripped size of the block with Segregated Witness \(signature\) data |
| consensus\_size\_limit | The size limit of a block in weight units |
| min\_chain\_sequence\_number | Starting [sequence number](https://app.gitbook.com/@knowledge-coinmetrics/s/test-documents/~/drafts/-MVObHsqKxAoYlUFDMjZ/atlas-overview#chain-sequencing) \(global ordering of the first update in this transaction relative to all other updates recorded on the ledger up until that point\) for the balance updates occurring in this transaction |
| max\_chain\_sequence\_number | Last [sequence number](https://app.gitbook.com/@knowledge-coinmetrics/s/test-documents/~/drafts/-MVObHsqKxAoYlUFDMjZ/atlas-overview#chain-sequencing) \(global ordering of the last update in this transaction relative to all other updates recorded on the ledger up until that point\) for the balance updates occurring in this transaction |
| n\_balance\_updates | Number of balance updates |
| amount | Amount of balance updates |
| [balance\_updates](../../balance-updates.md) | Array of balance updates for that block |

