# Tagging Meta Data

Coin Metrics Tagging Data is a powerful tool that provides users with a unique lens on blockchain data. It allows you to access blockchain addresses labeled with their real-world entity names or functions. By associating blockchain-level accounts/addresses with meaningful labels, you can gain a deeper understanding of the cryptocurrency world. The applications for this data can better explain activity around hot spots like smart contracts, exchanges, miners and many more.&#x20;

## [Tag Catalog](https://docs.coinmetrics.io/api/v4/#tag/Blockchain-Metadata/operation/getBlockchainMetadataTags)&#x20;

For accessing our Dictionary of tags you can leverage our Tag Catalog API Call. This returns a list of the tag options that can then be used ti query in the `tags` parameter of our `/tagged-entities` response. For detailed definitions or methodologies relating to specific tags. Please reach out to our team. \


Example: `https://api.coinmetrics.io/v4/blockchain-metadata/tags?&api_key={api_key}`

## [Entity and Tag Search](https://docs.coinmetrics.io/api/v4/#tag/Blockchain-Metadata/operation/getBlockchainMetadataEntities)

When utilizing the Tagging Data there are two query methods. The first is by searching for an Entity. Entities are addresses, accounts or contracts.&#x20;

Example: `https://api.coinmetrics.io/v4/blockchain-metadata/tagged-entities?entities={entity_list}&pretty=true&api_key={api_key}`

The second query method is for retrieving all entities defined under a defined tag. In the first release you are able to query for a single address.&#x20;

Example: `https://api.coinmetrics.io/v4/blockchain-metadata/tagged-entities?tags={tag_list}&pretty=true&api_key={api_key}`



### Example Result

```
// Result of Entity Search for Address "000000000006ec9792c0a516cbeb3b791e862949"
{
  "data": [
    {
      "entity": "000000000006ec9792c0a516cbeb3b791e862949",
      "tag": "ADDRESS_IS_CONTRACT",
      "location": "eth",
      "type": "ADDRESS",
      "tagger_type": "COINMETRICS",
      "tagger_method": "DETERMINISTIC",
      "start_time": "2021-01-26T22:14:08.000000000Z",
      "end_time": "2023-06-14T21:57:56.994603000Z",
      "start_block_hash": "dfe7e9cbbced47d27e4742e2002c56babd6d66de7077f2b1b6d6852c846b2a37"
    },
    {
      "entity": "000000000007232d9e1d5ae25a80a0d707e94a4b",
      "tag": "ADDRESS_IS_SWAPPER",
      "location": "uni_v2_eth",
      "type": "ADDRESS",
      "tagger_type": "COINMETRICS",
      "tagger_method": "DETERMINISTIC",
      "start_time": "2021-02-10T03:27:08.000000000Z",
      "end_time": "2023-06-14T21:57:56.994603000Z",
      "start_block_height": "11735382",
      "end_block_height": "11735401",
      "start_block_hash": "52eb7ff27c415b87a7917c9a884836186a46ffe5227c6f96a10500d5331db4f9",
      "end_block_hash": "b7f74e1614742d214b82dec0b85e188f843bcb587cd470b8c931bd6f6fc077ec"
    }
```

## Coin Metrics OPEN Values

It's essential to emphasize that the Coin Metrics Tagging Data operates in accordance with our Coin Metrics OPEN Values. The information provided by the API is gathered in a neutral and unbiased manner hoping to elucidate further understanding of blockchain activity and data.

## Release History

* **Beta Release on November 14, 2023**: Release of initial tagging data set and API

