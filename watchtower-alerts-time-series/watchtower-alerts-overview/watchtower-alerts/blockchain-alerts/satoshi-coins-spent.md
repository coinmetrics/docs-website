# Satoshi Coins Spent

**Alert Definition**

Alerts if a coin that was mined over the course of 2009 (thus, likely belonging to Bitcoin's creator, Satoshi Nakamoto) has been spent.

**Dictionary**

| Name                 | AlertID                   | Category | Sub-category      | Type | Unit  | Interval |
| -------------------- | ------------------------- | -------- | ----------------- | ---- | ----- | -------- |
| Satoshi Coins Spent  | satoshi\_coins\_spent\_hi | Alert    | Blockchain Alerts | N/A  | Event | Ad hoc   |

**Interpretation**

The movement of old coins tend to spook markets as their implied cost basis is substantially lower than current market levels. Often, these movements are interpreted as the coin's owner getting ready to liquidate the position. As such, the price of Bitcoin has negatively reacted to such events. This alert tracks the movement of the oldest of bitcoins - those that likely belong to its creator, Satoshi Nakamoto, and were generated over the course of 2009. These coins have never been moved (or spent) before, so there is high likelihood that they will generate volatility across markets.

**Potential Root Causes**

Satoshi has returned.

There was another entity other than Satoshi mining Bitcoin in 2009. The keys that once belonged to Satoshi have been compromised.

**Asset Coverage**

Bitcoin (BTC)

\


\
