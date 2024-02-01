# Fast Increase in Transaction Count Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the number of transactions in a block greatly exceeds the preceding 100 blocks.&#x20;

**Dictionary**

| Name                                     | AlertID                         | Category | Sub-category  | Type | Unit        | Interval |
| ---------------------------------------- | ------------------------------- | -------- | ------------- | ---- | ----------- | -------- |
| Fast Increase in Transaction Count Alert | block\_tx\_count\_rsd\_100b\_hi | Alert    | ETH PoS Alert | Sum  | Transaction | Ad hoc   |

**Interpretation**

At times projects release new tokens and NFTs at specific block heights. This can lead to congestion as demand for block space increases at that specific height. This can in turn prevent regular transactors from using the network.

**Potential Root Causes**

NFT or Token Launch at a specific point in time increases demand for block space. Market-driven events, such as market crashes, also tend to increase demand for block space.

**Asset Coverage**

Ethereum (ETH)

\
