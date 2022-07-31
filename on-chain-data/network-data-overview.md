# Network Data Overview

Network Data Pro (NDP) provides insightful, aggregate network data metrics for a wide-variety of cryptoasset networks. We run blockchain nodes to collect and harmonize information from dozens of blockchains. &#x20;

Our network data is aggregated at the asset level.  &#x20;

## Network Data Asset Coverage

Coin Metrics calculates network data pro metrics for assets such as `btc` and `eth`.  The asset coverage can be found by querying our [`/catalog/assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAssets) or [`/catalog-all/assets`](https://docs.coinmetrics.io/api/v4#operation/getCatalogAllAssets) API endpoints. &#x20;

For some assets, our product only covers part of their history (ERC-20 before a transition to a mainnet, contract migration, depreciation, etc.). This table lists those assets and our coverage period:

| **Asset** | **Coverage start** | **Coverage end** |
| --------- | ------------------ | ---------------- |
| QTUM      | 2017-07-06         | 2017-09-12       |
| AION      | 2017-09-28         | 2018-09-18       |
| LRC       | 2017-07-19         | 2019-05-08       |
| VET       | 2017-08-15         | 2018-06-30       |
| ZIL       | 2018-01-12         | 2019-04-21       |
| ICX       | 2017-09-12         | 2018-06-24       |
| AE        | 2017-09-02         | 2018-11-13       |
| NAS       | 2017-07-10         | 2018-05-01       |
| BTM       | 2017-07-13         | 2018-04-23       |
| KCS       | 2017-08-22         | 2021-02-10       |
| PIVX      | 2016-01-30         | 2021-01-28       |

## Data Available at Asset Level&#x20;

Data available at the asset level is available through the [`/timeseries/asset-metrics`](https://docs.coinmetrics.io/api/v4#operation/getTimeseriesAssetMetrics) API endpoint (`network data` product parameter) and specific metrics are described in the pages linked in this section:

{% content-ref url="../asset-metrics/addresses/" %}
[addresses](../asset-metrics/addresses/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/economics/" %}
[economics](../asset-metrics/economics/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/exchange/" %}
[exchange](../asset-metrics/exchange/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/fees-and-revenue/" %}
[fees-and-revenue](../asset-metrics/fees-and-revenue/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/market/" %}
[market](../asset-metrics/market/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/mining/" %}
[mining](../asset-metrics/mining/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/network-usage/" %}
[network-usage](../asset-metrics/network-usage/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/supply/" %}
[supply](../asset-metrics/supply/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/transactions/" %}
[transactions](../asset-metrics/transactions/)
{% endcontent-ref %}

{% content-ref url="../asset-metrics/wallets/" %}
[wallets](../asset-metrics/wallets/)
{% endcontent-ref %}
