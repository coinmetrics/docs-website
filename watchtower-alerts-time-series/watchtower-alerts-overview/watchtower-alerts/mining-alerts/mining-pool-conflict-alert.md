# Mining Pool Conflict Alert

**Alert Definition**

Alerts if miners disagree on which version of the blockchain to build upon over the course of two blocks.

**Dictionary**

| Name                       | AlertID                        | Category | Sub-category  | Type | Unit   | Interval |
| -------------------------- | ------------------------------ | -------- | ------------- | ---- | ------ | -------- |
| Mining Pool Conflict Alert | mining\_pool\_conflict\_2b\_hi | Alert    | Mining Alerts | Sum  | Blocks | Ad hoc   |

**Interpretation**

The blockchain fundamentally serves as a coordination mechanism for its users. When miners put together a new block of transactions, they often choose the most recently-mined block to build upon. Once a miner is successful, all other miners are expected to stop their work and create yet another block template that builds upon that miner's block. While that is the expectation, there are conditions that may lead mining pools to disagree on which block to build upon. Such disagreements can lead to network disruptions such as blockchain reorganization events, or reorgs.

**Potential Root Causes**

A mining pool might not be seeing the same block(s) as others due to connectivity problems at the P2P layer.

The network might have experienced a stale block and/or reorgs.

**Asset Coverage**

Bitcoin (BTC)

\


\
