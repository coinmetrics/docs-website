# Unknown Miner Predominance Alert

**Alert Definition**

Alerts if all of the previous six blocks observed in the blockchain were mined by unknown miners/mining pools.

**Dictionary**

| Name                             | AlertID                                   | Category | Sub-category  | Type | Unit   | Interval |
| -------------------------------- | ----------------------------------------- | -------- | ------------- | ---- | ------ | -------- |
| Unknown Miner Predominance Alert | block\_count\_by\_unknown\_miners\_6b\_hi | Alert    | Mining Alerts | Sum  | Blocks | Ad hoc   |

**Interpretation**

Miners identify themselves using a variety of techniques. In Bitcoin, miners identify themselves by encoding a message in the coinbase transaction, which rewards miners for successfully appending the blockchain. The industrialization of mining has made it unusual for six blocks to be mined sequentially by miners without identification in most, albeit not all, networks. As such, it is important to understand when such events take place.

**Potential Root Causes**

Miners no longer wish to identify themselves because of the privacy requirements when engaging in Miner Extractable Value (MEV), an activity that predominantly took place in Ethereum.

Large miners (or a cohort of miners) do not wish to identify themselves.

**Asset Coverage**

Bitcoin (BTC)
