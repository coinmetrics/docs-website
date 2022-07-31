# Normalizing Block Times

Converting the timestamps of a block into _human time_ is not always a straightforward process. In most blockchains, the Miners (or Validators) can decide the timestamp of a block. This can lead to strange timestamps recorded on-chain. If, for example, there is a bug on the software used by a block's Miner, its timestamp might not reflect the correct sequence of blocks. In other words, a block may have a timestamp that is _older_ than its predecessor.

Consider the Bitcoin block at height 156,114. The Miner of this block reported a timestamp that is two hours _older_ its predecessor, block 156,113. This is logically impossible. Even though this Miner was aware of the timestamp of block 156,113, they still reported a timestamp in the past. Often, incorrect timestamps are due to bugs in mining software, but they might also occur as a form of deliberate manipulation.

Data providers must account for such events, otherwise any time series data would be susceptible to incorrect ordering. This issue compounds when trying to convert blockchain time into "human" time intervals, such as days. For example, it may lead to situations where a day is made of block 1,000,000 to 1,000,100, but excludes block 1,000,099 if it was incorrectly timestamped. That exclusion leads to an incorrect assessment of the on-chain activity that occurred that day.&#x20;

**For this reason, Coin Metrics normalizes on-chain data using **_**Median-Time-Past,**_** a timestamp normalization approach developed by Bitcoin Core.** Given that there are security concerns related to miners manipulating timestamps (especially related to [_timelocks_](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch07.asciidoc)_)_, Median-Time-Past has been standardized in Bitcoin (and adopted by other Bitcoin-like protocols) via [BIP-0113](https://github.com/bitcoin/bips/blob/master/bip-0113.mediawiki) in 2015.&#x20;

We normalize the timestamp of every Bitcoin block using Median-Time-Past, which is the median timestamp of that block and its 11 predecessors. By using the median of roughly two hours worth of blocks, the impact of an erroneous or outright manipulated miner timestamp is eliminated. This ensures that the timestamps we use for metric calculation increase in tandem with block height and are never in the past, thereby making our time series data more accurate.&#x20;

Since not all crypto data providers go through the effort of normalizing timestamps, our time series data for human intervals, such as _days,_ may differ.&#x20;
