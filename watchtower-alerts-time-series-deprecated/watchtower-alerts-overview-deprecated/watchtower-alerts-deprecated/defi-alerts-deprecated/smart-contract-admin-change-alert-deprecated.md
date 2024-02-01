# Smart Contract Admin Change Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the admin of a smart contract has changed.

**Dictionary**

| Name                              | AlertID                    | Category | Sub-category | Type | Unit  | Interval |
| --------------------------------- | -------------------------- | -------- | ------------ | ---- | ----- | -------- |
| Smart Contract Admin Change Alert | admin\_key\_change\_1b\_hi | Alert    | DeFi Alerts  | N/A  | Event | Ad hoc   |

**Interpretation**

Many DeFi applications are entirely controlled by a special key called the admin key. If compromised, hackers could use this key to effectively takeover the DeFi application it controls via an admin key change, or put simply , an ownership change. This would enable them to mint large sums of the application's token, pause the smart contract, censor users, or change the application in any arbitrary way.

**Potential Root Causes**

The admin was changed due to a planned operational/administrative change.

The admin key was compromised and an attacker is now in control of the application.

**Asset Coverage**

Aave (AAVE), SushiSwap (SUSHI), Paxos Gold (PAXG), RenBTC (RENBTC), Wrapped Bitcoin (WBTC), Tether Gold (XAUT), Binance USD (BUSD), Huobi USD (HUSD), USD Paxos (PAX), Circle USD (USDC), OkCoin USD (USDK), Tether USD on ETH (USDT\_ETH)
