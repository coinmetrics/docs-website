# Mempool Congestion Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the virtual size (vsize) of all mempool transactions exceeds 300,000,000 vBytes.

**Dictionary**

| Name                      | AlertID            | Category | Sub-category   | Type | Unit  | Interval |
| ------------------------- | ------------------ | -------- | -------------- | ---- | ----- | -------- |
| Mempool Congestion Alert  | mempool\_vsize\_hi | Alert    | Mempool Alerts | Sum  | vsize | Ad hoc   |

**Interpretation**

By default, the nodes of a cryptonetwork have a dedicated area to store unprocessed transactions, the mempool. Since mempools rely on local storage, their capacity to store unprocessed transactions must be limited. Otherwise, the mempool could be exploited by an attacker flooding it with transactions. If a mempool has reached 300M vB, nodes may begin discarding transactions to free up space, which can cause disruptions.

**Potential Root Causes**

Increase demand for block space leading to congestion, often caused by market volatility.

A mempool flood attack, a type of DDoS attack whereby the mempool is spammed with transactions.

**Available Assets**&#x20;

Bitcoin (BTC)

\
