# DeFi Data Overview (Labs)

Decentralized Finance (DeFi) is a rapidly emerging ecosystem of applications and protocols used for trading, lending, and various other financial services. Rather than relying on centralized intermediaries, these protocols utilize permissionless blockchains such as Ethereum to conduct the majority of their activities and transactions on-chain.

## Decentralized Exchange Swaps Data

Our decentralized exchange (DEX) market data is collected directly from the blockchain and harmonized to match the format of our centralized exchange market data. Each liquidity pool contract is represented as a distinct market, with many pairs being traded across multiple liquidity pools with alternative fee structures.

Market coverage can be found by querying our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) or [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints. Decentralized exchanges can be identified as any market where the `experimental` parameter is set to `True`.

Currently we offer coverage of 3 DEX protocols:

<table><thead><tr><th width="181.33333333333331">Exchange</th><th width="217" align="center">Spot Market Count</th><th align="center">Start Date</th></tr></thead><tbody><tr><td>Sushiswap</td><td align="center">134</td><td align="center">2020-09-04</td></tr><tr><td>Uniswap v2</td><td align="center">407</td><td align="center">2020-07-04</td></tr><tr><td>Uniswap v3</td><td align="center">345</td><td align="center">2020-07-04</td></tr></tbody></table>

In addition to returning standard metadata such as the market's base and quote asset, DEX market entries in the catalog also contain several DeFi-specific fields:

* `contract_address`: The smart contract address of the liquidity pool contract.
* `fee`: The fee percentage charged for each swap. Fees are distributed pro-rata to the pool's liquidity providers.
* `base_address`: The address of the ERC-20 token contract associated with the _base_ asset.
* `quote_address`: The address of the ERC-20 token contract associated with the _quote_ asset.

## Data Available at the Market Level

Many of our data types are available at the market level. For decentralized exchanges, we define a market as a specific liquidity pool contract deployed on a specific decentralized exchange, like `uniswap_v2_eth-1inch-aave-spot` or `uniswap_v3_eth-2-wsteth-weth-spot` or `sushiswap_v1_eth-srm-weth-spot`. The data types listed below are available for each DEX liquidity pool:&#x20;

{% content-ref url="../market-data/market-trades.md" %}
[market-trades.md](../market-data/market-trades.md)
{% endcontent-ref %}

{% content-ref url="../market-data/market-candles.md" %}
[market-candles.md](../market-data/market-candles.md)
{% endcontent-ref %}

In addition to returning standard metadata such as the trade's size and price, DEX market entries in the catalog also contain several DeFi-specific fields:

* `block_hash`: The unique hash of the block containing the swap transaction.
* `block_height`: The height of the block containing the swap transaction.
* `txid`: The transaction hash associated with the swap.
* `initiator`: The Ethereum address which submitted the transaction, as a result of which the swap occurred.
* `sender`: The Ethereum address that invoked the liquidity pool smart contract's function for swapping.
* `beneficiary`: The Ethereum address credited with the output tokens upon the completion of a swap.

## Data Available at the Exchange-Asset Pair Level

Coin Metrics calculates several metrics for exchange-asset pairs such as `uniswap_v3_eth-usdc`, `sushiswap_v1_eth-aave`, and `uniswap_v2_eth-wbtc`. The exchange coverage can be found by querying our [`/catalog/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchangeAssets) or [`/catalog-all/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchangeAssets) API endpoints.

Data available at the exchange-asset level is available through the [`/timeseries/exchange-asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeAssetMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% embed url="https://docs.coinmetrics.io/exchange-asset-metrics/volume" %}

## Data Available at Exchange Level&#x20;

Coin Metrics calculates several metrics for decentralized exchanges such as `uniswap_v3_eth`, `uniswap_v2_eth`, and `sushiswap_v1_eth`. The exchange coverage can be found by querying our [`/catalog/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchanges) or [`/catalog-all/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchanges) API endpoints.

Data available at the exchange level is available through the [`/timeseries/exchange-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeMetrics) API endpoint and specific metrics are described in the pages linked in this section:&#x20;

{% embed url="https://docs.coinmetrics.io/exchange-metrics/volume" %}
