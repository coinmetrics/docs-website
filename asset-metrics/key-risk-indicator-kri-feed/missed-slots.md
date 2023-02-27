# Missed Slots

**Definition**

The count of missed slots within the most-recent 1-minute interval. For context, a slot represents an opportunity for a block producer (or validator) to create a block. If the validator fails to produce a block at the slot, it is considered missed and the blockchain progresses to the following slot.

**Dictionary**

| Name         | MetricID             | Category | Sub-category | Type | Unit  | Interval |
| ------------ | -------------------- | -------- | ------------ | ---- | ----- | -------- |
| Missed Slots | block\_missed\_slots | KRI      | Empty Blocks | Sum  | Slots | 1b       |

**Methodology**

This metric infers the number of missed slots on the basis of the time between blocks. If a block takes more than 12 seconds to arrive, it can be inferred that a slot has been missed as per Ethereum’s consensus rules. Note that if two slots are missed consecutively, we would still need to wait until for valid slot to arrive to capture it, as per the methodology.

**Available Assets**

Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=eth&frequency=1b&metrics=block_missed_slots&pretty=true" %}
