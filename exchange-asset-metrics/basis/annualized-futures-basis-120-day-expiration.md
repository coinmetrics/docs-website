# Annualized Futures Basis, 120 day expiration

## Definition

The annualized percent difference between the price of a theoretical futures contract that expires in 120 days and the price of its underlying spot market.

| Name                                         | MetricID                     | Category | Subcategory | Type       | Unit          | Frequency |
| -------------------------------------------- | ---------------------------- | -------- | ----------- | ---------- | ------------- | --------- |
| Annualized Futures Basis, 120 day expiration | basis\_annualized\_120d\_exp | Basis    | Future      | Percentage | Dimensionless | 1h, 1d    |

## Details

We calculate the basis using the price of a theoretical futures contract with a fixed number of days to expiration. A futures contract with the exact number of days to expiration may not exist in the market. Therefore, we calculate the price of a theoretical futures contract using a combination of the soonest to expire quarterly contract and and the subsequent quarterly contract.&#x20;

## Release History

* Release Version. Market Data Feed 2.5 (October 2021)&#x20;

## Availability for Exchange-Assets

{% embed url="https://coverage.coinmetrics.io/exchange-asset-metrics/basis_annualized_120d_exp" %}
