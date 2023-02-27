# Hashrate Decrease Alert

**Alert Definition**

Alerts if there has been a drop in hashrate greater than 10% over the course of a day.

**Dictionary**

| Name                     | AlertID                | Category | Sub-category  | Type | Unit     | Interval |
| ------------------------ | ---------------------- | -------- | ------------- | ---- | -------- | -------- |
| Hashrate Decrease Alert  | hashrate\_drop\_1d\_lo | Alert    | Mining Alerts | Sum  | Hashrate | Ad hoc   |

**Interpretation**

Drops in hashrate can be indicative of miners going offline and may predict network disruptions, such as feerate increases, as well as market volatility.

**Potential Root Causes**

Miner profitability has decreased, which has led miners to pull the plug and go offline.

Another protocol with the same hashing algorithm is more profitable to mine and miners have relocated their hashrate.

Potential problems with major mining pools (or with their constituents).

**Asset Coverage**

Bitcoin (BTC)

\


\
