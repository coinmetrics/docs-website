# Increase in Active Addresses Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the Active Addresses of a given block are higher than its 100-block predecessors. Active Addresses represent the sum count of unique addresses that were active in the network (either as a destination or source of a ledger change) that block. All parties in a ledger change action (source and destination) are counted.

**Dictionary**

| Name                               | AlertID                                 | Category | Sub-category  | Type | Unit               | Interval |
| ---------------------------------- | --------------------------------------- | -------- | ------------- | ---- | ------------------ | -------- |
| Increase in Active Addresses Alert | block\_active\_addresses\_rsd\_100b\_hi | Alert    | ETH PoS Alert | Sum  | Count of Addresses | Ad hoc   |

**Interpretation**

At times projects release new tokens and NFTs at specific block heights. This can lead to congestion as demand for block space increases at that specific height, which in turn increases Active Addresses. In more concerning circumstances, a consistent increase in Active Addresses might be a result of a Denial-of- Service (DoS) attack.

\
**Potential Root Causes**

NFT or Token Launch at a specific point in time increases demand for block space, which leads to increased address activity.

In some circumstances, it may indicative of a Denial-of-Service (DoS) attack.

**Asset Coverage**

Ethereum (ETH)

\
