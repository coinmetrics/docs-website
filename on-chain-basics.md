---
description: Introduction to on-chain concepts
---

# On-Chain Basics

### Address

An address is the alphanumeric identifier that represents a unique account within a cryptoasset network. It’s usually a random string of characters, but it can also contain human readable words, or be composed of a domain address.

### Ledger change <a href="#ledger-change" id="ledger-change"></a>

A ledger change is any operation that can happen on an asset’s ledger. Another synonym could be operation. They can be initiated by users or occur automatically as part of the protocol itself.

Ledger changes usually have at least:

* one or more sources, no recipients
* one or more recipients, no sources
* both sources and recipients

Sources and recipients of ledger changes can be addresses, the protocol itself, or non specified.

| **Ledger Change**     | **Initiator/Source**    | **Beneficiary/Destination**                 |
| --------------------- | ----------------------- | ------------------------------------------- |
| Transfer              | Users                   | Users                                       |
| Transaction fees      | Users                   | Miner/Staker/Protocol/No destination (burn) |
| Founders reward       | Protocol                | Founders                                    |
| Community reward      | Protocol                | Users                                       |
| Mining/Staking reward | Protocol                | Users                                       |
| At-launch issuance    | Protocol                | Users                                       |
| Post-launch issuance  | Founders/Protocol       | Founders/Users                              |
| Post-launch burns     | Founders/Users/Protocol | No destination/Burn Address                 |

**Transfers**

Transfers are movements of native units between distinct addresses. Their value must be greater than 0 (otherwise, no movement of native units occurred).

For UTXO chains, transfers occur when new outputs are created with a value greater than 0 and that can be provably unlocked, or spent (e.g. non OP\_RETURN). We exclude outputs created in coinbase transactions from this definition as they are mining rewards.

**Transaction fees**

Transaction fees are what ledger users pay to the entities mining/validating their transactions. In most assets, transaction fees are paid to the miner/validator who included the transaction in a block. However, in some assets like XRP, transaction fees are burned.

**Founders reward**

Some assets, like ZCash, have a protocol rule that, up until a specific block height, newly created native units are credited to addresses controlled by the protocol’s founders/stewards. This differs from block validation rewards as founders do not engage in transaction validation..

**Community reward**

Some assets, like Decred, have a protocol rule that allows a portion of newly created native units to be credited to arbitrary accounts based on the outcome of a governance process. Those funds usually serve to finance initiatives proposals that were voted by the community(marketing, etc..). This differs from a founders reward as the beneficiaries are not necessarily founders of the protocol, and the proceeds are used within the scope of the proposed community initiative

**Mining/Staking reward**

Most protocol’s consensus mechanisms include some inflation process whose beneficiaries are miners or stakers.

**At-launch issuance**

An at-launch issuance is an inflation event that takes place prior, or during, the genesis block. It is relevant for assets that had a pre-sale, or a pre-mine, whereby the ledger did not start from n blank slate, as some accounts already credited with an amount of native units.

**Post-launch issuance**

A post-launch issuance is an inflation event that takes place after the genesis block. It only includes punctual, non-programmatic issuance, such as seigniorage, further token sales, inflationary air-drops etc..

**Post-launch burns**

A post-launch burn is a deflationary event whereby an entity is allowed to permanently destroy native units, often through its control of network-wide consensus..

### Transaction

A transaction represents a bundle of intended actions to alter ownership structures within the ledger. A transaction can fail or succeed depending on whether it is compatible with a protocol’s consensus rules. A transaction’s execution may result in subsequent [ledger changes](on-chain-basics.md#ledger-change).

### Block

A block usually consists of two parts; a header, and a separate data field where [transactions ](on-chain-basics.md#transaction)are listed. The header includes metadata about the block, such as its timestamp, previous block hash, version, etc... The transactions field may include an index of transactions that took place, or it may be empty.

### Normalizing Block Times

Converting the timestamps of a block into _human time_ is not always a straightforward process. In most blockchains, the Miners (or Validators) can decide the timestamp of a block. This can lead to strange timestamps recorded on-chain. If, for example, there is a bug on the software used by a block's Miner, its timestamp might not reflect the correct sequence of blocks. In other words, a block may have a timestamp that is _older_ than its predecessor.

Consider the Bitcoin block at height 156,114. The Miner of this block reported a timestamp that is two hours _older_ its predecessor, block 156,113. This is logically impossible. Even though this Miner was aware of the timestamp of block 156,113, they still reported a timestamp in the past. Often, incorrect timestamps are due to bugs in mining software, but they might also occur as a form of deliberate manipulation.

Data providers must account for such events, otherwise any time series data would be susceptible to incorrect ordering. This issue compounds when trying to convert blockchain time into "human" time intervals, such as days. For example, it may lead to situations where a day is made of block 1,000,000 to 1,000,100, but excludes block 1,000,099 if it was incorrectly timestamped. That exclusion leads to an incorrect assessment of the on-chain activity that occurred that day.&#x20;

**For this reason, Coin Metrics normalizes on-chain data using **_**Median-Time-Past,**_** a timestamp normalization approach developed by Bitcoin Core.** Given that there are security concerns related to miners manipulating timestamps (especially related to [_timelocks_](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch07.asciidoc)_)_, Median-Time-Past has been standardized in Bitcoin (and adopted by other Bitcoin-like protocols) via [BIP-0113](https://github.com/bitcoin/bips/blob/master/bip-0113.mediawiki) in 2015.&#x20;

We normalize the timestamp of every Bitcoin block using Median-Time-Past, which is the median timestamp of that block and its 11 predecessors. By using the median of roughly two hours worth of blocks, the impact of an erroneous or outright manipulated miner timestamp is eliminated. This ensures that the timestamps we use for metric calculation increase in tandem with block height and are never in the past, thereby making our time series data more accurate.&#x20;

Since not all crypto data providers go through the effort of normalizing timestamps, our time series data for human intervals, such as _days,_ may differ.&#x20;

### Asset Ledger

#### Account based blockchains

For account based blockchains, the asset ledger is its mapping of all account states.

The state of each account records:

* Its balance in native units
* The date of creation of the account (or time of first appearance of the creation is implicit)
* The date of the last ledger change this account was a source of (used for active supply)

#### UTXO Chains

For UTXO based chain, the asset’s ledger is the UTXO set (unspent transaction output set). It’s the set of outputs that are unspent to that moment in the ledger’s history.

The information relevant for each output is:

* its value in native units
* its time of creation
* its owner address (can be not present if there’s no address for this output)

OP\_RETURN outputs are not present in the asset’s ledger as they are provably unspendable.

#### &#x20;ERC-20 assets

For ERC-20 assets, we aim to replicate exactly the contract’s balances so that our supply figure matches exactly the contract’s total supply. Otherwise, the fields are identical to other account based chains.

### Assets Coverage

For some assets, our product only covers part of their history (ERC-20 before a transition to a mainnet, contract migration, depreciation, etc..). This table lists those assets and our coverage period:

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
