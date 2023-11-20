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
"data" : [ {
    "entity" : "000000000006ec9792c0a516cbeb3b791e862949",
    "tag" : "ADDRESS_IS_CONTRACT",
    "location" : "eth",
    "type" : "ADDRESS",
    "tagger_type" : "COINMETRICS",
    "tagger_method" : "DETERMINISTIC",
    "start_time" : "2021-01-26T22:14:08.000000000Z",
    "start_block_height" : "11734034",
    "start_block_hash" : "81c9410e149bfab4877faf08b01c3f1656d24bada66b1337f4802cc5304947af"
  }, {
    "entity" : "000000000006ec9792c0a516cbeb3b791e862949",
    "tag" : "ADDRESS_IS_SWAPPER",
    "location" : "uni_v2_eth",
    "type" : "ADDRESS",
    "tagger_type" : "COINMETRICS",
    "tagger_method" : "DETERMINISTIC",
    "start_time" : "2021-01-27T02:46:17.000000000Z",
    "start_block_height" : "11735233",
    "start_block_hash" : "10a39f4cdf992bfed5c62296804bf65a6e5f1eb18b32626235133a2cbab57959"
    }...
```

## Tagging Dictionary

For Descriptions on our tagging defintions and sourcing information please see the document below.

{% file src="../.gitbook/assets/Tag Dictionary v0.1 - Nov 2023.pdf" %}

## Coin Metrics OPEN Values

It's essential to emphasize that the Coin Metrics Tagging Data operates in accordance with our Coin Metrics OPEN Values. The information provided by the API is gathered in a neutral and unbiased manner hoping to elucidate further understanding of blockchain activity and data.

## Release History

* **Beta Release on November 14, 2023**: Release of initial tagging data set and API

