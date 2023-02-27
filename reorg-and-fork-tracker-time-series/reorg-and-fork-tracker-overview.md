---
description: /timeseries/asset-chains
---

# Reorg & Fork Tracker Overview

The Reorg & Fork Tracker is a tool that can be used to monitor the conditions at the blockchain tip, the most recent set of blocks. This endpoint provides all context to understand when a network wide split is occurring, or when a network wide reorg has occurred.

**Blockchain Splits**

Blockchain Splits, also known as chain splits, occur when two or more versions of the blockchain can be observed at the same height. Often, splits are a natural by-product of a network's consensus protocol. For example, if two Bitcoin miners happen to find a mine block at the same time, the blockchain is split into two versions. In such events, a race condition ensues whereby miners must converge on a single version. Ultimately, only one of the blocks will be considered valid and all competing versions become stale.

On rarer occasions, chain splits may be a result of more concerning circumstances, such as software bugs and/or network attacks. Ethereum, for example, experienced two chain splits within the two years which led to varying levels of service disruptions. Both splits were caused by unexpected bugs in the software client employed by Ethereum users to connect to the network. The chain split captured in, [CVE-2021-39137](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-39137), was particularly worrisome as some estimated that only one-third of the network was running the correct version blockchain client.

**Reorganization Events**

After a chain split, networks might experience Reorganization Events, often abbreviated to reorgs. These occur when the ordering of the most recent blocks of a blockchain changes. For example, consider a chain split where a blockchain is partitioned into two branches, branch A and B. Immediately after the chain split, the majority of miners are mining upon branch A and ignoring branch B. They mine two blocks upon branch A. Soon thereafter, however, a large miner is able to build one block upon branch B. Other miners start converging on branch B, which subsequently attains the majority of miners. As per consensus rules, all nodes will discard the blocks of branch A and incorporate the blocks of branch B.

Reorgs happen on Bitcoin roughly on a monthly basis. They are often harmless, as the composition of the blocks of the competing branches is often very similar, apart from the miner reward transaction. There are two dimensions that determine the severity of a reorg: the number of transactions impacted by it, its composition; and the number of blocks replaced, its depth. Deep reorgs with vastly different composition can be indicative of network attacks, such as 51% attacks, or the exploitation of a severe bug at the client level.

\
