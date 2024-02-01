# Admin Change with Issuance Event Alert - DEPRECATED

<mark style="color:red;">**THIS ENDPOINT HAS BEEN DEPRECATED AND WILL NO LONGER BE ACTIVELY MAINTAINED, UPDATED OR SUPPORTED**</mark>

**Alert Definition**

Alerts if the admin of a smart contract has changed and new units of the asset were printed over the course of the following 120 blocks (\~25 minutes).

**Dictionary**

| Name                                   | AlertID                                        | Category | Sub-category | Type | Unit  | Interval |
| -------------------------------------- | ---------------------------------------------- | -------- | ------------ | ---- | ----- | -------- |
| Admin Change with Issuance Event Alert | admin\_key\_change\_inflation\_event\_120b\_hi | Alert    | DeFi Alerts  | N/A  | Event | Ad hoc   |

**Interpretation**

Many DeFi applications are entirely controlled by a special key called the admin key. If compromised, hackers could use this key to effectively takeover the DeFi application controlled by the key via an admin key change. This would enable them to mint themselves large sums of the application's token, halt it altogether, censor users, or change the application in any arbitrary way.

**Potential Root Causes**

The admin was changed due to a planned operational/administrative change that coincided with a scheduled minting event.

The admin key was compromised: an attacker is now in control of it and is using this power to mint new units of the application's token.

**Asset Coverage**

Aave (AAVE), SushiSwap (SUSHI), Paxos Gold (PAXG), RenBTC (RENBTC), Wrapped Bitcoin (WBTC), Tether Gold (XAUT), Binance USD (BUSD), Huobi USD (HUSD), USD Paxos (PAX), Circle USD (USDC), OkCoin USD (USDK), Tether USD on ETH (USDT\_ETH)

\


\
