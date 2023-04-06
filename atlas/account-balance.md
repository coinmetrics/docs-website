---
description: /blockchain-v2/{asset}/accounts/{account}/balance-updates
---

# Account Balance

The account balance endpoint allows users to query balance-updates and counter-parties by account with a single request. The endpoint will include full account transaction history and counter-party data.

| Field                             | Description                                                                                                                                                                                                    |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| account                           | Counterparty account for the transaction that occurred ([Account](accounts.md) as described in the Atlas overview)                                                                                             |
| account\_creation\_height         | Block height at creation of account                                                                                                                                                                            |
| change                            | Balance change after this update                                                                                                                                                                               |
| previous\_balance                 | Balance of the account prior to the application of this update                                                                                                                                                 |
| new\_balance                      | Balance of the account after this update                                                                                                                                                                       |
| transaction\_sequence\_number     | Order of this update inside the transaction that contains it                                                                                                                                                   |
| n\_debits                         | Number of debits                                                                                                                                                                                               |
| n\_credits                        | Number of credits                                                                                                                                                                                              |
| previous\_debit\_height           | Block height of the last debit                                                                                                                                                                                 |
| previous\_credit\_height          | Block height of the last credit                                                                                                                                                                                |
| previous\_chain\_sequence\_number | Orders balance updates inside a single transaction to distinguish between serial and parallel balance updates.                                                                                                 |
| sub\_account                      | Sub-account value depends on the asset. Bitcoin value is set to be the reference of the unspent output (concatenation of txHash + offset) Other assets will show values like FREE, FROZEN, STAKED, LOCKED, etc |
| stale                             | Indicator if the block is stale                                                                                                                                                                                |
| block\_hash                       | Hash of that block (unique per block)                                                                                                                                                                          |
| height                            | Height of that block (number of confirmed blocks since Genesis block)                                                                                                                                          |
| consensus\_time                   | [Consensus timestamp](atlas-overview.md#consensus-timestamp); always increases monotonically                                                                                                                   |
| txid                              | Hash of transaction (transaction ID)                                                                                                                                                                           |
| credit                            | Indicator whether the balance update is a credit or debit of the account                                                                                                                                       |
| total\_received                   | Total amount received                                                                                                                                                                                          |
| total\_sent                       | Total amount sent                                                                                                                                                                                              |
