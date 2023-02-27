# Vintage Coins Spent

**Alert Definition**

Alerts if an Unspent Transaction Output (UTXO) from 2010 has been spent.

**Dictionary**

| Name                 | AlertID                   | Category | Sub-category      | Type | Unit  | Interval |
| -------------------- | ------------------------- | -------- | ----------------- | ---- | ----- | -------- |
| Vintage Coins Spent  | vintage\_coins\_spent\_hi | Alert    | Blockchain Alerts | N/A  | Event | Ad hoc   |

**Interpretation**

The movement of old coins can spook markets as their implied cost basis is substantially lower than current market levels. Often, these movements are interpreted as the coin's owner getting ready to liquidate the position. As such, the price of Bitcoin has negatively reacted to such events. This alert tracks the movement of Unspent Transaction Outputs (UTXOs) from 2010, which belong to the earliest adopters of Bitcoin.

**Potential Root Causes**

An early adopter has been able to recover previously-lost keys.

An early adopter has decided to move funds, either as a way to employ better security practices, or to sell funds.

**Asset Coverage**

Bitcoin (BTC)

\
