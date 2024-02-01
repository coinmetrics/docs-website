# Mempool Disruption Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if in the previous five minutes no transactions were added to the mempool.

**Dictionary**

| Name                      | AlertID                | Category | Sub-category   | Type | Unit                  | Interval |
| ------------------------- | ---------------------- | -------- | -------------- | ---- | --------------------- | -------- |
| Mempool Disruption Alert  | mempool\_count\_5m\_lo | Alert    | Mempool Alerts | Sum  | Count of Transactions | Ad hoc   |

**Interpretation**

It would be very unusual for a cryptoasset's mempool to not receive any transactions over the course of five minutes, even in periods of low activity.

**Potential Root Causes**

There might be a severe problem with the node client that is preventing user transactions from being included in the mempool.

The network might be experiencing an unusually low period of inactivity.

**Asset Coverage**

Bitcoin (BTC)

\
