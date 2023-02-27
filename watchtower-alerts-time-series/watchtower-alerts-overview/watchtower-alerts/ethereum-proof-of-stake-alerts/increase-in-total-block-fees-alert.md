# Increase in Total Block Fees Alert

**Alert Definition**

Alerts if the Total Block Fees of a given block are higher than its 100-block predecessors. Total Block Fees represent the total fees associated with a block. In Ethereum, this is the sum of all Base Fees and Priority Fees in a block.

**Dictionary**

| Name                               | AlertID                    | Category | Sub-category  | Type | Unit | Interval |
| ---------------------------------- | -------------------------- | -------- | ------------- | ---- | ---- | -------- |
| Increase in Total Block Fees Alert | block\_fees\_rsd\_100b\_hi | Alert    | ETH PoS Alert | Sum  | Gas  | Ad hoc   |

**Interpretation**

A consistent increase in Total Block Fees might occur naturally as a result of an increase in demand for block space. Given the dynamics of EIP-1559, as blocks in the blockchain fill up, Base Fees and Priority Fees tend to increase. This causes short-term congestion as unprocessed transactions add up, and it is only resolved once the increase in fees disincentivizes users from transacting and the unprocessed transaction queue is cleared.

**Potential Root Causes**

Organic increase in demand for block space.

Market-driven events, such as market crashes and black swans, also tend to increase demand for block space.

**Asset Coverage**

Ethereum (ETH)

\
\
