---
description: /security-master/assets
---

# Security Master Assets

## Definition

The Coin Metrics Security Master contains references data about all assets in our coverage universe.

## Details

The reference data for assets includes the asset ticker, asset code, the smallest divisible unit of the asset, the creation date, the asset type, the parent asset, and the token contract if the asset is an ERC-20 asset.

## Example

A sample of the futures and options contract specification data from our [`/security-master/assets`](https://docs.coinmetrics.io/api/v4/#tag/Security-Master/operation/getSecurityMasterAssets) API endpoint is shown below.&#x20;

```
{
  "data" : [ {
    "asset" : "btc",
    "code" : "C758EA35B0",
    "description" : "Bitcoin is a peer-to-peer network that facilitates transfers between network participants without any central authority.",
    "overview" : "Bitcoin is a peer-to-peer network that facilitates transfers between network participants without any central authority. Bitcoin utilizes blockchain technology to create a trusted distributed ledger storing transaction and account data. The Bitcoin blockchain consists of blocks, added roughly every 10 minutes, that contain information on recent transactions, active addresses, and a link to previous blocks, ultimately providing a complete record of all transactions on the network. To add a block to the chain, miners must find a particular nonce that when hashed meets the requirements presented by the network. When a passable nonce is discovered the miner broadcasts it to all the nodes on the network, who in turn make sure each transaction on the block is valid and add it to their copy of the chain. To incentivize mining, the miner that finds the correct nonce is rewarded a fixed amount of bitcoin ( the reward amount halves every 210,000 blocks) and any transaction fees included. This cryptographic process is referred to as proof of work. The difficulty of each block is controlled by the network, which scales difficulty as the total hashing power on the network increases. To access the bitcoin network, users have wallets that allow them to see their available balance and transact with others. Each account has two keys associated with it: a public key and a private key. The public key gets converted into an address to which people can send you funds and the private key allows a user to prove ownership of bitcoin. When sending a transaction a user inputs the address of the intended recipient and the amount being transferred, signs the transaction with their private key, and specifies a transaction fee. Transactions wait in the mempool until they are added to blocks. Generally, a user can get a transaction included in a block earlier by paying a higher transaction fee. Since its inception, multiple second-layer solutions have been developed on the Bitcoin protocol. One of these solutions is the Lightning Network, which provides instant and low-cost micropayments between users. To use the network, two users open a payment channel that operates off-chain. Funds transferred through this channel are only settled on the blockchain when the users close the channel.",
    "website" : "https://bitcoin.org/en/",
    "whitepaper" : "https://bitcoin.org/bitcoin.pdf",
    "consensus_mechanism" : "Proof-of-Work (SHA256d)",
    "decimals" : "8",
    "creation_date" : "2009-01-03",
    "type" : "utxo"
  } ]
}
```

* **`asset`**:  Unique symbol of the asset.\

* **`code`**: The unique and immutable code for each asset. Each code is 10 digit alphanumeric string that starts with C and ends with a checksum digit. This code is immutable so it will not change if an asset undergoes a rebranding or symbol change.\

* **`description`**:  The description of the asset.\

* **`website`**: The URL of the asset's website. If omitted, then no official website for the asset was found.\

* **`whitepaper`**: The URL of the asset's whitepaper. If omitted, then no official whitepaper for the asset was found.\

* **`consensus_mechanism`**: The protocols, algorithms, incentives, and ieas that allow a network of nodes to agree on the state of a blockchain. If omitted, then the asset may not be a layer 1 or native asset.\

* **`decimals`**: The number of decimal places that represent the smallest divislbe unit of the asset.\

* **`creation_date`**: The date of the confirmation of first block of the asset.\

* **`type`**: The type of the asset.

## Release History

* **Coin Metrics Security Master v1.0 on September 18, 2023**: Initial release.
