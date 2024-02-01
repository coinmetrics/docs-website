# Fast Decrease in Priority Fees (Tips) Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the Priority Fees (or tips) of a block are lower than its 100-block predecessors. For context, the concept of a Priority Fee, or tip, was introduced as part of EIP-1559 and it represents the portion of the total transaction fees that rewards miners. This serves as an added incentive so that miners prioritize transactions that have opted-in and paid a tip. The other portion is called the Base Fee, and it is burnt (destroyed) after the transaction is included in a block

\
**Dictionary**

| Name                                        | AlertID                             | Category | Sub-category  | Type | Unit | Interval |
| ------------------------------------------- | ----------------------------------- | -------- | ------------- | ---- | ---- | -------- |
| Fast Decrease in Priority Fees (Tips) Alert | block\_priority\_fee\_rsd\_100b\_lo | Alert    | ETH PoS Alert | Sum  | Gas  | Ad hoc   |

**Interpretation**

A consistent decrease in Priority Fees might occur organically as demand for block space decreases. It can also be a sign of more concerning circumstances if persistent. For example, a decrease in Priority Fees at a time when there is visible demand for block space might be a sign of so-called out of band payments, which are payments made by transactors directly to miners.

**Potential Root Causes**

Organic decrease in demand for block space. Out of band payments made directly to miners.

**Asset Coverage**

Ethereum (ETH)

\
