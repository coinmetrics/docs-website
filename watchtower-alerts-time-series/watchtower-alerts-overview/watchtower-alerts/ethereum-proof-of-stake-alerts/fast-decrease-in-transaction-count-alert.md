# Fast Decrease in Transaction Count Alert

**Alert Definition**

Alerts if the number of transactions in a block is considerably below the preceding 100 blocks.&#x20;

\
**Dictionary**

| Name                                     | AlertID                         | Category | Sub-category  | Type | Unit        | Interval |
| ---------------------------------------- | ------------------------------- | -------- | ------------- | ---- | ----------- | -------- |
| Fast Decrease in Transaction Count Alert | block\_tx\_count\_rsd\_100b\_lo | Alert    | ETH PoS Alert | Sum  | Transaction | Ad hoc   |

**Interpretation**

A decrease in transaction count may be caused organically by seasonal decreases in demand, or may be a result of more concerning circumstances. If, for example, validators are censoring a specific type of transaction, blocks would not be fully empty, but transaction count would decrease.

**Potential Root Causes**

Natural drop in demand for block space, which tends to be seasonal. Potential censorship at the block producer level.

**Asset Coverage**

Ethereum (ETH)

\
