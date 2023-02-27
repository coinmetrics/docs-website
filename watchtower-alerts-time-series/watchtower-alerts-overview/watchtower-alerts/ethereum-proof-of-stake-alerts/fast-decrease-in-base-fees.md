# Fast Decrease in Base Fees

**Alert Definition**

Alerts if a block’s Base Fee is lower relative to its 100-block predecessors. For context, the concept of a Base Fee was introduced as part of EIP-1559 and it represents the portion of the total transaction fees that are destroyed and taken out of circulation (i.e. burnt). Ethereum post-1559 requires users to pay for a Base Fee as a prerequisite to include transactions in a block. The Base Fee can go up or down on the basis of the size (in gas units) of the previous block.

**Dictionary**

| Name                       | AlertID                         | Category | Sub-category  | Type | Unit | Interval |
| -------------------------- | ------------------------------- | -------- | ------------- | ---- | ---- | -------- |
| Fast Decrease in Base Fees | block\_base\_fee\_rsd\_100b\_lo | Alert    | ETH PoS Alert | Sum  | Gas  | Ad hoc   |

**Interpretation**

A consistent decrease in Base Fees might occur naturally as a result of a decrease in demand for block space. In some circumstances, it may indicative of outages at infrastructure providers that service cryptoasset wallets. For example, when Infura, a popular node-as-a-service provider faces downtime, this can usually be captured by a decrease in Base Fees.

**Potential Root Causes**

Organic decrease in demand for block space.

Outage at a critical infrastructure provider preventing nodes from broadcasting transactions.

**Asset Coverage**

Ethereum (ETH)

\
