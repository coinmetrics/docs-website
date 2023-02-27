# Fast Increase in Priority Fees (Tips) Alert

**Alert Definition**

Alerts if the Priority Fees (or tips) of a block are higher than its 100-block predecessors. For context, the concept of a Priority Fee, or tip, was introduced as part of EIP-1559 and it represents the portion of the total transaction fees that rewards miners. This serves as an added incentive so that miners prioritize transactions that have opted-in and paid a tip. The other portion is called the Base Fee, and it is burnt (destroyed) after the transaction is included in a block.

**Dictionary**

| Name                                        | AlertID                             | Category | Sub-category  | Type | Unit | Interval |
| ------------------------------------------- | ----------------------------------- | -------- | ------------- | ---- | ---- | -------- |
| Fast Increase in Priority Fees (Tips) Alert | block\_priority\_fee\_rsd\_100b\_hi | Alert    | ETH PoS Alert | Sum  | Gas  | Ad hoc   |

**Interpretation**

A sharp increase in Priority Fees may occur organically as demand for block space increases, but they are more frequently associated with market events. At times, projects release new tokens and NFTs at specific block heights. This can lead to congestion as demand for block space increases at that specific height. Users bid exponentially higher priority fees to get access to specific tokens or NFTs. This practice is usually called Fee Sniping.

**Potential Root Causes**

Organic increase in demand for block space, leading to an increase in Priority Fees. Market-level event, such as the release of a new NFT, leading to Fee Sniping.

**Asset Coverage**

Ethereum (ETH)

\
