# Missed Slot Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if a slot has been missed by a Proof-of-Stake validator. For context, a slot represents an opportunity for a block producer (or validator) to create a block. If the validator fails to produce a block at the slot, it is considered missed and the blockchain progresses to the following slot.&#x20;

Our methodology is designed to infer the number of missed slots on the basis of the time between blocks. If a block takes more than 15 seconds to arrive, it can be inferred that a slot has been missed as per Ethereum’s consensus rules. Note that if two slots are missed consecutively, we would still need to wait until a valid to arrive to capture it, as per the methodology.

**Dictionary**

| Name              | AlertID              | Category | Sub-category  | Type  | Unit  | Interval |
| ----------------- | -------------------- | -------- | ------------- | ----- | ----- | -------- |
| Missed Slot Alert | 1b\_slot\_missed\_hi | Alert    | ETH PoS Alert | Count | Slots | Ad hoc   |

**Interpretation**

A missed slot might be the result of a validator going offline, or connectivity issues impacting the communications between validators. In more concerning scenarios where the missed slot rate consistently upticks, it might indicative of a bug, or a large cohort of validators going offline.

**Potential Root Causes**

The validator responsible to produce a block at that height is unavailable or otherwise unable to do so. If persistent, this could also be a sign of a bug at the client level.

**Asset Coverage**

Ethereum (ETH)

\
