# 6 Consecutive Empty Blocks Alert

**Alert Definition**

Alerts if the previous six blocks mined had no user-generated transactions within.

**Dictionary**

| Name                              | AlertID                     | Category | Sub-category      | Type | Unit              | Interval |
| --------------------------------- | --------------------------- | -------- | ----------------- | ---- | ----------------- | -------- |
| 6 Consecutive Empty Blocks Alert  | block\_count\_empty\_6b\_hi | Alert    | Blockchain Alerts | Sum  | Empty Block Count | Ad-hoc   |

**Interpretation**

Proof-of-Work mining is a Poisson process whereby it is impossible to authoritatively predict who the miner or the composition of the next block. Nevertheless, it is very unusual for six sequential blocks to contain no user generated transactions. As such, this is a critical event that must be tracked.

**Potential Root Causes**

In less popular networks, there might be a severe lack of demand for block space. In other words, no users are utilizing the network.

Alternatively, the network might be experiencing a severe DoS attack whereby miners are actively censoring user transactions.

Miners might be deliberately producing empty blocks in order to manipulate the fee market and increase the fees users are paying.

There might be a severe bug in the software used by mining pools to assemble block templates. This might also occur due to a Selfish Mining attack, or a 51% attack.

**Asset Coverage**

Bitcoin (BTC)

\
