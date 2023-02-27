# Admin Change with Large Issuance Event Alert

**Alert Description**

Alerts if the admin of a smart contract has changed followed by a large token issuance event. We consider an issuance event to be "large" when over 5% of the token's total supply was minted in the 120 blocks that followed the admin key change.

**Dictionary**

| Name                                          | AlertID                                          | Category | Sub-category | Type | Unit  | Interval |
| --------------------------------------------- | ------------------------------------------------ | -------- | ------------ | ---- | ----- | -------- |
| Admin Change with Large Issuance Event Alert  | admin\_key\_change\_inflation\_highvol\_120b\_hi | Alert    | DeFi Alerts  | N/A  | Event | Ad hoc   |

**Interpretation**

Many DeFi applications are entirely controlled by a special key called the admin key. If compromised, hackers could use this key to effectively takeover the DeFi application controlled by the key via an admin key change. This would enable them to mint themselves large sums of the application's token, which is the potential scenario captured by this alert.

**Potential Root Causes**

The admin was changed due to a planned operational/administrative change that coincided with a large minting event. This issuance event might have been part of a predetermined schedule or a protocol improvement proposal that also required an admin key change.

The admin key was compromised, an attacker is now in control of it, and the new admin is using this power to mint significant quantities of the application's token, likely to sell it in the marketplace.

\
**Asset Coverage**

Aave (AAVE), SushiSwap (SUSHI), Paxos Gold (PAXG), RenBTC (RENBTC), Wrapped Bitcoin (WBTC), Tether Gold (XAUT), Binance USD (BUSD), Huobi USD (HUSD), USD Paxos (PAX), Circle USD (USDC), OkCoin USD (USDK), Tether USD on ETH (USDT\_ETH)

\
