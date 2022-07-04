# ERC-1155 Contracts Cnt

## Definition

The sum count of unique smart contracts implementing the ERC-1155 standard present in the blockchain at the end of the interval. A smart contract exists in a blockchain network as a special address that contains and can execute code. The ERC-1155 standard is an emerging standard for the issuance of both fungible and non-fungible tokens on Ethereum. As of this metric's release date, the standard has attained considerable traction in the ecosystem of Non-Fungible Tokens.

| Name                   | MetricID       | Category     | Subcategory | Type | Unit      | Interval |
| ---------------------- | -------------- | ------------ | ----------- | ---- | --------- | -------- |
| ERC-1155 Contracts Cnt | ContERC1155Cnt | Transactions | Contracts   | Sum  | Contracts | 1 day    |

## Details

* This metric is calculated by monitoring the blockchain for contracts that comply with the ERC-1155 standard_,_ as defined by the [EIP-1155 Standard Specification](https://eips.ethereum.org/EIPS/eip-1155).
* Like ERC-721 contracts, the activity of ERC-1155s is detected with the help of a secondary standard, ERC-165, which provides an interface for both 751 as well as 1155-compliant events.

## Asset-Specific Details

* As this metric is tailored to the Ethereum ecosystem, it is only available for ETH .

## Release History

* Released in Network Data Pro (NDP) version 5.1

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/ContERC1155Cnt" %}
