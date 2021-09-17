# Market Data Overview

The [CM Market Data Feed](https://coinmetrics.io/market-data-feed/) \(MDF\) provides access to historical and real-time data from the world’s leading spot and derivatives crypto exchanges. We offer a wide range of harmonized datasets such as trades, candles, order book snapshots, several futures-specific data types, several options-specific data types, several market data metrics, and more. ****

Our data is available at several different levels: asset, exchange, market, asset pair, exchange-asset pair, and institution. Our coverage universe currently consists of 2,171 assets, 34 exchanges, 12,553 spot markets, 6,353 futures markets, 14,883 options markets, 2,698 asset pairs, 2,595 exchange-asset pairs, and one institution. 

## Data Available at Market Level 

Many of our data types are available at the market level. We define a market as a specific listed pair or derivatives contract that trades on a specific exchange, like `coinbase-btc-usd-spot` or `binance-BTCUSDT-future` or `deribit-BTC-16MAY21-58000-C-option`. The market coverage can be found by querying our [`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) or [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets) API endpoints.

Data available at the market level is served through the API endpoints below, which are described in the pages linked in this section: 

* \`\`[`/catalog/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogMarkets) and [`/catalog-all/markets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllMarkets)\`\`
* \`\`[`/timeseries/market-trades`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketTrades)\`\`
* \`\`[`/timeseries/market-openinterest`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketOpenIntereset)\`\`
* \`\`[`/timeseries/market-liquidations`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketLiquidations)\`\`
* \`\`[`/timeseries/market-funding-rates`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketFundingRates)\`\`
* \`\`[`/timeseries/market-orderbooks`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketOrderbooks)\`\`
* \`\`[`/timeseries/market-quotes`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketQuotes)\`\`
* \`\`[`/timeseries/market-candles`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesMarketCandles)\`\`

{% page-ref page="derivatives-contract-specifications.md" %}

{% page-ref page="market-trades.md" %}

{% page-ref page="market-open-interest.md" %}

{% page-ref page="futures-liquidations.md" %}

{% page-ref page="futures-funding-rates.md" %}

{% page-ref page="market-order-book.md" %}

{% page-ref page="market-quotes.md" %}

{% page-ref page="market-candles.md" %}

{% page-ref page="market-data-faqs.md" %}

## Data Available at Asset Level 

Coin Metrics calculates several metrics for assets such as `btc` and `eth`. The asset coverage can be found by querying our [`/catalog/assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssets) or [`/catalog-all/assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssets) API endpoints.

Data available at the asset level is available through the [`/timeseries/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) API endpoint and specific metrics are described in the pages linked in this section: 

{% page-ref page="../asset-metrics/market/referenceratesusd.md" %}

{% page-ref page="../asset-metrics/market/referencerateeur.md" %}

{% page-ref page="../asset-metrics/open-interest/" %}

{% page-ref page="../asset-metrics/volume/" %}

## Data Available at Exchange Level 

Coin Metrics calculates several metrics for exchanges such as `coinbase`, `binance`, and `deribit`. The exchange coverage can be found by querying our [`/catalog/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchanges) or [`/catalog-all/exchanges`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchanges) API endpoints.

Data available at the exchange level is available through the [`/timeseries/exchange-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeMetrics) API endpoint and specific metrics are described in the pages linked in this section: 

{% page-ref page="../asset-metrics/volume/" %}

{% page-ref page="../asset-metrics/open-interest/" %}

## Data Available at Exchange-Asset Pair Level 

Coin Metrics calculates several metrics for exchange-asset pairs such as `coinbase-btc`, `binance-eth`, and `deribit-usdt`. The exchange coverage can be found by querying our [`/catalog/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogExchangeAssets) or [`/catalog-all/exchange-assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllExchangeAssets) API endpoints.

Data available at the exchange-asset level is available through the [`/timeseries/exchange-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesExchangeMetrics) API endpoint and specific metrics are described in the pages linked in this section: 

{% page-ref page="../asset-metrics/volume/" %}

{% page-ref page="../asset-metrics/open-interest/" %}

{% page-ref page="../asset-metrics/basis/" %}

## Data Available at Asset Pair Level 

Coin Metrics calculates several metrics for asset pairs such as `grayscale`. The institution coverage can be found by querying our [`/catalog/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssetPairs) or [`/catalog-all/pairs`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssetPairs) API endpoints.

Data available at the asset pair level is available through the [`/timeseries/pair-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesPairMetrics) API endpoint and specific metrics are described in the pages linked in this section: 

{% page-ref page="../asset-metrics/volume/" %}

{% page-ref page="../asset-metrics/open-interest/" %}

## Data Available at Institution Level 

Coin Metrics calculates several metrics for institutions such as `grayscale`. The institution coverage can be found by querying our [`/catalog/institutions`](https://docs.coinmetrics.io/api/v4#operation/getCatalogInstitutions) or [`/catalog-all/institutions`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllInstitutions) API endpoints.

Data available at the institution level is available through the [`/timeseries/institution-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesInstitutionMetrics) API endpoint and specific metrics are described in the pages linked in this section: 

{% page-ref page="../institution-metrics/grayscale/" %}



