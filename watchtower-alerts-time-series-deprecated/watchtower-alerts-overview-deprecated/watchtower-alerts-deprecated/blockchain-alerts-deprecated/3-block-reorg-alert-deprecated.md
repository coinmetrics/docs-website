# 3 Block Reorg Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if a blockchain reorganization event, or reorg, of 3 blocks has been identified. For context, reogs occur when the ordering of the most recent blocks of a blockchain changes. For example, consider a scenario where a blockchain is partitioned into two branches, branches A and B. Immediately after this split, the majority of miners (or validators in the case of Proof-of-Stake) are mining upon branch A and ignoring branch B. They mine two blocks upon branch A. Soon thereafter, however, a large miner is able to build one block upon branch B. Other miners start converging on branch B, which subsequently attains the majority of miners. As per consensus rules, all nodes will discard the block(s) of branch A and incorporate the blocks of branch B.

**Dictionary**

| Name                | AlertID             | Category | Sub-category      | Type | Unit            | Interval |
| ------------------- | ------------------- | -------- | ----------------- | ---- | --------------- | -------- |
| 3 Block Reorg Alert | 3b\_deep\_reorg\_hi | Alert    | Blockchain Alerts | N/A  | Block tip count | Ad hoc   |

**Interpretation**

Reorgs that are shallow can occur naturally as part of a blockchain’s consensus process. However, if frequent, they are a cause of concern given their potential to impact the set of transactions users consider to be final. Reorgs also increase congestion as the transactions of the removed branch are sent back to the mempool with other unprocessed transactions.

**Potential Root Causes**

Reorgs might occur naturally, especially in times of network connectivity issues.

In some circumstances, reorgs might represent an attack on a network’s consensus layer.

**Asset Coverage**

Bitcoin (BTC), Ethereum (ETH)

\
