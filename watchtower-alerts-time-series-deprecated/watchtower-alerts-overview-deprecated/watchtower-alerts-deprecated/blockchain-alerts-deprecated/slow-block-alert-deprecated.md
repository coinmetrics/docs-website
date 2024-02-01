# Slow Block Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if a block is taking an unusually long time to be mined.

**Dictionary**

| Name             | AlertID                | Category | Sub-category      | Type | Unit    | Interval |
| ---------------- | ---------------------- | -------- | ----------------- | ---- | ------- | -------- |
| Slow Block Alert | time\_inter\_block\_hi | Alert    | Blockchain Alerts | N/A  | Seconds | Ad hoc   |

**Interpretation**

Blockchain protocols often feature a time interval target between blocks. That time is called inter block time. Bitcoin, for example, targets an inter block time of ten minutes. Inter block targets, such as Bitcoin's ten- minute rule, may differ considerably from actual inter block times. There is a multitude of factors that influence block times, including the number of miners currently online, the difficulty of mining a block, amongst other factors. Since Proof-of-Work mining is a Poisson process, it is impossible to predict when a block will be mined. Nevertheless, it is important to identify when inter block time is exceedingly long.

**Potential Root Causes**

Proof-of-Work Mining is a Poisson process. As such, there is a probability that slow blocks will occur even if network conditions are stable.

Slow blocks might be caused by a large portion of miners might going offline at once and decreasing the network's hashrate.

**Asset Coverage**

Bitcoin (BTC)

\
