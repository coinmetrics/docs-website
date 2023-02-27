# 1 Consecutive Empty Block Alert

Alert ID

1b\_consecutive\_empty\_blocks\_hi

**Alert Definition**

Alerts if 1 consecutive block was produced with no user-generated transactions within. This alert could indicate issues with relayers or MEV economics as well as an issue with the validator for that slot.

**Dictionary**

| Name                              | AlertID                            | Category | Sub-category      | Type | Unit              | Interval |
| --------------------------------- | ---------------------------------- | -------- | ----------------- | ---- | ----------------- | -------- |
| 1 Consecutive Empty Blocks Alert  | 1b\_consecutive\_empty\_blocks\_hi | Alert    | Blockchain Alerts | Sum  | Empty Block Count | Ad-hoc   |

**Interpretation**

In Proof-of-Stake, validators are known ahead of time and can collude to produce empty blocks. Their motivation would be to exacerbate pricing discrepancies in DeFi so that higher arbitrage opportunities emerge. This activity is part of a broader theme called Maximum Extractable Value (MEV).

In Proof-of-Work, mining is a Poisson process whereby it is impossible to authoritatively predict who the miner or the composition of the next block. If two consecutive blocks are empty, it might be a sign of selfish mining and might lead to network disruptions, such as the increase of feerates.

**Potential Root Causes**

In Proof-of-Stake, this can be caused by a type of MEV attack, or by a severe bug preventing validators from sourcing transactions.

In less popular networks, there might be a severe lack of demand for block space. In other words, no users are utilizing the network.

**Asset Coverage**

Ethereum (ETH)

\
\
