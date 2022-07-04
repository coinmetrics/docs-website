# ERC-1155 Xfer Cnt

## Definition

The sum count of ERC-1155 transfers in that interval. Only transfers between two distinct addresses are counted. The ERC-1155 standard is an emerging standard for the issuance of both fungible and non-fungible tokens on Ethereum. As of this metric's release date, the standard has attained considerable traction in the ecosystem of Non-Fungible Tokens.&#x20;

| Name              | MetricID        | Category     | Subcategory | Type | Unit      | Interval |
| ----------------- | --------------- | ------------ | ----------- | ---- | --------- | -------- |
| ERC-1155 Xfer Cnt | TxTfrERC1155Cnt | Transactions | Transfers   | Sum  | Transfers | 1 day    |

## Details

* This metric is calculated by monitoring the blockchain for ERC-1155 _Transfer Events,_ as defined by the [EIP-1155 Standard Specification](https://eips.ethereum.org/EIPS/eip-1155).
* Like ERC-721 contracts, the activity of ERC-1155s is detected with the help of a secondary standard, ERC-165, which provides an interface for both 751 as well as 1155-compliant events.

## Asset-Specific Details

* As this metric is tailored to the Ethereum ecosystem, it is only available for ETH .

## Release History

* Released in Network Data Pro (NDP) version 5.1

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/TxTfrERC1155Cnt" %}
