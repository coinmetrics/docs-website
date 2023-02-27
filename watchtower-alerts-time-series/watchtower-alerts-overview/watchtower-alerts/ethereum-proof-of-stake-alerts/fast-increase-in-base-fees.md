# Fast Increase in Base Fees

**Alert Definition**

Alerts if a block’s Base Fee is higher relative to its 100-block predecessors. For context, the concept of a Base Fee was introduced as part of EIP-1559 and it represents the portion of the total transaction fees that are destroyed and taken out of circulation (i.e. burnt). Ethereum post-1559 requires users to pay for a Base Fee as a prerequisite to include transactions in a block. The Base Fee can go up or down on the basis of the size (in gas units) of the previous block.

\
**Dictionary**

| Name                       | AlertID                         | Category | Sub-category  | Type | Unit | Interval |
| -------------------------- | ------------------------------- | -------- | ------------- | ---- | ---- | -------- |
| Fast Increase in Base Fees | block\_base\_fee\_rsd\_100b\_hi | Alert    | ETH PoS Alert | Sum  | Gas  | Ad hoc   |

**Interpretation**

A consistent increase in Base Fees might occur naturally as a result of an increase in demand for block space. Given the dynamics of EIP-1559, as blocks in the blockchain fill up, Base Fees increase. This causes short-term congestion as unprocessed transactions add up, and it is only resolved once the increase in fees disincentivizes users from transacting and the unprocessed transaction queue is cleared.

**Potential Root Causes**

Organic increase in demand for block space.

Market-driven events, such as market crashes and black swans, also tend to increase demand for block space.

**Asset Coverage**

Ethereum (ETH)

\
