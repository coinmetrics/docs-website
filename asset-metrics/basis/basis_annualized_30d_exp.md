# Annualized Futures Basis, 30 day expiration

## Definition

The annualized percent difference between the price of a theoretical futures contract that expires in 30 days and the price of its underlying spot market.

| Name | MetricID | Category | Subcategory | Type | Unit | Frequency |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Annualized Futures Basis, 30 day expiration | basis\_annualized\_30d\_exp | Basis | Future | Percentage | Dimensionless | 1h, 1d |

## Details

We calculate the basis using the price of a theoretical futures contract with a fixed number of days to expiration. A futures contract with the exact number of days to expiration may not exist in the market. Therefore, we calculate the price of a theoretical futures contract using a combination of the soonest to expire quarterly contract and and the subsequent quarterly contract. 

## Release History

* Release Version. Market Data Feed 2.5 \(October 2021\) 

