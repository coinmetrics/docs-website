---
description: /blockchain-v2/{asset}/accounts
---

# Accounts

The **Account** endpoint returns a list of accounts, which have the following fields:

| Field                             | Description                                                                                                                                     |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| account                           | [Account](accounts.md) as described in the Atlas overview                                                                                       |
| type                              | Account type (UTXO, Virtual, Account)                                                                                                           |
| balance                           | Current account balance in native units                                                                                                         |
| n\_debits                         | Number of debits                                                                                                                                |
| n\_credits                        | Number of credits                                                                                                                               |
| creation\_height                  | Block height at creation of account                                                                                                             |
| creation\_block\_hash             | Block hash at creation of account                                                                                                               |
| creation\_time                    | Block time at creation of account                                                                                                               |
| creation\_chain\_sequence\_number | The positioning of the account creation transaction relative to all other transactions that have taken place on this chain                      |
| last\_chain\_sequence\_number     | The positioning of the last transaction that took place for this account relative to all other transactions that have taken place on this chain |
| last\_debit\_height               | Block height of the last debit                                                                                                                  |
| last\_credit\_height              | Block height of the last credit                                                                                                                 |

