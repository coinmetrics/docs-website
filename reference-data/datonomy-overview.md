# datonomy Overview

datonomy, a digital asset classification system created by Coin Metrics, Goldman Sachs and MSCI, creates a consistent, standardized way for investors to analyze the digital assets ecosystem.

datonomy offers a new level of transparency into how the market is moving and serves as a powerful foundation for portfolio performance measurement, risk management, reporting, and investment strategy creation.

## Asset Coverage

The asset coverage can be found by querying our [`taxonomy/assets`](https://docs.coinmetrics.io/api/v4#operation/getTaxonomyAssets) API endpoint. &#x20;

To be eligible for classification, an asset must be widely available to an everyday investor.  See [methodology](methodologies/guiding-principles-and-methodology-for-datonomy.md) for details on how assets are selected for inclusion.

## Classifications

Assets are classified based on primary use as defined by the project creators themselves. The taxonomy has three levels.

<figure><img src="../.gitbook/assets/Screen Shot 2022-08-31 at 7.02.01 PM.png" alt=""><figcaption><p> </p></figcaption></figure>

Each asset in the coverage universe is in only one subsector and every covered asset has a **6-digit industry code** and **name.**

#### **Example**

| Level     | Code   | Name                 |
| --------- | ------ | -------------------- |
| Class     | 10     | Transaction          |
| Sector    | 1010   | Value Transfer Coins |
| Subsector | 101010 | Value Transfer Coins |

As of November 2022, there are four Classes, 14 Sectors, and 41 Sub-Sectors in datonomy.

## API Endpoints

Data available at the asset level is available through the [`taxonomy/assets`](https://docs.coinmetrics.io/api/v4#operation/getTaxonomyAssets)  API endpoint.  More details on these endpoints can be found in the sections below:

{% content-ref url="../taxonomy/taxonomy-for-assets.md" %}
[taxonomy-for-assets.md](../taxonomy/taxonomy-for-assets.md)
{% endcontent-ref %}
