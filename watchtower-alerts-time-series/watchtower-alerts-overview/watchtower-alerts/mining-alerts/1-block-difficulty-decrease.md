# 1-Block Difficulty Decrease

**Alert Definition**

Alerts if there has been a drop in difficulty over the course of a block.

**Dictionary**

| Name                         | AlertID                      | Category | Sub-category  | Type | Unit             | Interval |
| ---------------------------- | ---------------------------- | -------- | ------------- | ---- | ---------------- | -------- |
| 1-Block Difficulty Decrease  | difficulty\_decrease\_1b\_lo | Alert    | Mining Alerts | Sum  | Block Difficulty | Ad hoc   |

**Interpretation**

A blockchain's difficulty parameter, as the name suggests, determines how many attempts miners will likely have to perform in order to successfully mine a block. A drop in difficulty over the course of a block often is not, by itself, a concerning event. However, if the incidence of this alert is high, it might be a sign of more worrisome circumstances.

**Potential Root Cause**

A decrease in hashrate, or an unexpectedly slow block, depending on how the protocol adjusts difficulty.

**Asset Coverage**

Bitcoin (BTC)

\
