# Decrease in Active Addresses Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the Active Addresses of a given block are lower than its 100-block predecessors. Active Addresses represent the sum count of unique addresses that were active in the network (either as a destination or source of a ledger change) that block. All parties in a ledger change action (source and destination) are counted.

**Dictionary**

| Name                               | AlertID                                 | Category | Sub-category  | Type | Unit               | Interval |
| ---------------------------------- | --------------------------------------- | -------- | ------------- | ---- | ------------------ | -------- |
| Decrease in Active Addresses Alert | block\_active\_addresses\_rsd\_100b\_lo | Alert    | ETH PoS Alert | Sum  | Count of Addresses | Ad hoc   |

**Interpretation**

A consistent decrease in Active Addresses may be caused organically by seasonal decreases in demand, or may be a result of more concerning circumstances. If, for example, validators are censoring a group of addresses, blocks would not be fully empty, but Active Addresses would decrease.

**Potential Root Causes**

Natural drop in demand for block space, which tends to be seasonal. Potential censorship at the block producer level.

**Asset Coverage**

Ethereum (ETH)

\
