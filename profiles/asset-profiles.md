---
description: /profile/assets
---

# Asset Profiles

## **Definition**

The asset profiles provide a descriptive overview of an asset.

## Details

For more information on the asset profiles see the [asset profiles overview](../reference-data/asset-profiles-overview.md).

## Endpoint Response

The **Profile/Assets** endpoint returns a profile for each asset.  The response is formatted as follows:

| Field                 | Description                                                                                                                                                                    |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `asset`               | Asset symbol                                                                                                                                                                   |
| `full_name`           | Asset name                                                                                                                                                                     |
| `description`         | Description of key features                                                                                                                                                    |
| `overview`            | Description of key features and an overview of how the asset solves the problem for which it was created.                                                                      |
| `website`             | Link to project website (if omitted, then no official website for the project was found)                                                                                       |
| `whitepaper_url`      | Link to whitepaper URL (if omitted, then no official whitepaper URL was found)                                                                                                 |
| `consensus_mechanism` | The protocols, algos, incentives and ideas that allow a network of nodes to agree on the state of a blockchain (if omitted, then the asset may not be a layer 1 or base asset) |
| `parent_chain`        | The base asset(s) a project or protocol is built on (if the asset is the base asset, field = "Native Asset"                                                                    |
| `creation_date`       | Genesis block or first included block                                                                                                                                          |
| `supply_cap`          | The max number of coins programmed to exist in the lifetime of a cryptoasset (if omitted, then supply is uncapped/unlimited/infinite)                                          |

## Example

A sample of the asset profile response for  `btc` is  shown below.

```
{
    "asset" : "btc",
    "full_name" : "Bitcoin",
    "description" : "Bitcoin is a peer-to-peer network that facilitates transfers between network participants without any central authority.",
    "overview" : "Bitcoin is a peer-to-peer network that facilitates transfers between network participants without any central authority. Bitcoin utilizes blockchain technology to create a trusted distributed ledger storing transaction and account data. The Bitcoin blockchain consists of blocks, added roughly every 10 minutes, that contain information on recent transactions, active addresses, and a link to previous blocks, ultimately providing a complete record of all transactions on the network. To add a block to the chain, miners must find a particular nonce that when hashed meets the requirements presented by the network. When a passable nonce is discovered the miner broadcasts it to all the nodes on the network, who in turn make sure each transaction on the block is valid and add it to their copy of the chain. To incentivize mining, the miner that finds the correct nonce is rewarded a fixed amount of bitcoin ( the reward amount halves every 210,000 blocks) and any transaction fees included. This cryptographic process is referred to as proof of work. The difficulty of each block is controlled by the network, which scales difficulty as the total hashing power on the network increases. To access the bitcoin network, users have wallets that allow them to see their available balance and transact with others. Each account has two keys associated with it: a public key and a private key. The public key gets converted into an address to which people can send you funds and the private key allows a user to prove ownership of bitcoin. When sending a transaction a user inputs the address of the intended recipient and the amount being transferred, signs the transaction with their private key, and specifies a transaction fee. Transactions wait in the mempool until they are added to blocks. Generally, a user can get a transaction included in a block earlier by paying a higher transaction fee. Since its inception, multiple second-layer solutions have been developed on the Bitcoin protocol. One of these solutions is the Lightning Network, which provides instant and low-cost micropayments between users. To use the network, two users open a payment channel that operates off-chain. Funds transferred through this channel are only settled on the blockchain when the users close the channel.",
    "website" : "https://bitcoin.org/en/",
    "whitepaper_url" : "https://bitcoin.org/bitcoin.pdf",
    "consensus_mechanism" : "Proof-of-Work (SHA256d)",
    "creation_date" : "2009-01-01",
    "supply_cap" : "21000000"
  }
```

## Release History

* **Version 1.0 on January 30, 2023**: Release of initial version of the asset profiles
