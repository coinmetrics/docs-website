# Decrease in Total Block Fees Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the Total Block Fees of a given block are lower than its 100-block predecessors. Total Block Fees represent the total fees associated with a block. In Ethereum, this is the sum of all Base Fees and Priority Fees in a block.

**Dictionary**

| Name                               | AlertID                    | Category | Sub-category  | Type | Unit | Interval |
| ---------------------------------- | -------------------------- | -------- | ------------- | ---- | ---- | -------- |
| Decrease in Total Block Fees Alert | block\_fees\_rsd\_100b\_lo | Alert    | ETH PoS Alert | Sum  | Gas  | Ad hoc   |

**Interpretation**

A consistent decrease in Total Block Fees might occur naturally as a result of a decrease in demand for block space. In some circumstances, it may indicative of outages at infrastructure providers that service cryptoasset wallets. For example, when Infura, a popular node-as-a-service provider faces downtime, this can usually be captured by a decrease in Total Block Fees.

**Potential Root Causes**

Organic decrease in demand for block space. Outage at a critical infrastructure provider preventing nodes from broadcasting transactions.

**Asset Coverage**

Ethereum (ETH)

\




\
