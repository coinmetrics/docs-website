---
description: /blockchain-v2/{asset}/balance-updates
---

# Balance Updates

Balance updates represent the change in the balance of an account.  If the change is greater-or-equal to 0, it is considered a credit.  Otherwise, it is considered a debit.   In certain circumstances, there can be 0-valued balance updates (used to represent 0 fee transactions, for example, which were frequent in Bitcoin's early history). &#x20;

The **Balance Updates** endpoint returns a list of accounts, which have the following fields:

| Field                                                                     | Description                                                                                                                                                       |
| ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| block\_hash                                                               | Hash of block containing the transaction affecting the balance                                                                                                    |
| height                                                                    | Height of the block containing the transaction affecting the balance                                                                                              |
| consensus\_time                                                           | [Consensus timestamp](atlas-overview.md#consensus-timestamp); always increases monotonically                                                                      |
| chain\_sequence\_number                                                   | Global [sequence number ](atlas-overview.md#chain-sequencing)or ordering of this update relative to all other updates recorded on the ledger up until this point  |
| account                                                                   | [Account](atlas-overview.md#accounts) receiving a balance change                                                                                                  |
| account\_creation\_height                                                 | Block height at account creation                                                                                                                                  |
| change                                                                    | Balance change after this update                                                                                                                                  |
| previous\_balance                                                         | Balance of the account prior to the application of this update                                                                                                    |
| new\_balance                                                              | Balance of the account after this update                                                                                                                          |
| [transaction\_sequence\_number](atlas-overview.md#transaction-sequencing) | Order of this update inside the transaction that contains it                                                                                                      |
| previous\_n\_debits                                                       | Number of times this account has been debited prior to this update                                                                                                |
| previous\_n\_credits                                                      | Number of times this account has been credited prior to this update                                                                                               |
| transaction\_hash                                                         | Hash of the transaction containing the balance update                                                                                                             |
| previous\_debit\_height                                                   | Block height of the last debit from this account (null if no prior debit)                                                                                         |
| previous\_credit\_height                                                  | Block height of the last credit from this account (null if no prior credit)                                                                                       |
| previous\_chain\_sequence\_number                                         | The positioning of the last transaction that took place for this account relative to all other transactions that have taken place on this chain                   |
