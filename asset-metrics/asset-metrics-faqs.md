# Network Data FAQs

### **Why don’t you have Coinbase deposits/withdrawals (on-chain flows) supply data?**

We don't have on-chain metrics for Coinbase addresses because they don't reuse addresses. At this time, no data providers can get an accurate measurement on their on-chain activity.&#x20;

That said, we do offer full market data coverage for Coinbase through our Market Data Feed if you would like visibility into their trading volume.

### **Do your aggregate exchange deposit/withdrawal and supply (on-chain flows) metrics include any Coinbase flows?**

Our aggregate on-chain exchange metrics (eg. FlowOutExInclUSD or FlowOutExInclUSD) do include some Coinbase cold storage addresses. However, relative to the inputs from other constituent exchanges the the impact on the total aggregate flows is minimal.&#x20;

### **Why is your Current Supply (SplyCur) of XLM different from the supply reported on Stellar’s Dashboard? (**[**https://dashboard.stellar.org**](https://dashboard.stellar.org)**)**

This difference is due to how we treat the 55 billion tokens that the Stellar Development Foundation “burned”, or more accurately, rendered un-spendable. They sent the tokens to an address that cannot sign transactions. The public key that can sign for it has a weight set to 0, which makes transactions invalid. Since they technically still exist on the ledger, our Current Supply (SplyCur) includes them.&#x20;

### **What is the latency of block-by-block network data?**

The end-to-end latency for BTC BBB metrics is at most 54 seconds with a median of 14 seconds and an average of 20 seconds. For ETH BBB, this is at most 31 seconds with a median of 5 seconds.&#x20;

### **Why does your Market Capitalization metrics differ so heavily from other data providers?**

Generally, there is a great deal of inconsistency in the market with respect to Market Capitalization calculations. As a result, we have several Market Capitalization metrics.  Our metric labeled [Market Cap](market/capmrktcurusd.md) uses the [Current Supply](supply/splycur.md) (sum of all native units ever created and currently visible on the ledger) in its formulation.  Unlike some other data providers, it does not exclude illiquid supply held in escrow or foundation accounts. Our [Free Float Market Cap](market/capmrktffusd.md), however, does exclude native units held by company insiders, controlling investors and long term strategic holders.

Another way to think about our Market Cap is to equate it to the Fully Diluted Market Cap, while other many other market caps metrics use reported or an approximation of circulating supply - similar to our Free Float supply, but often not using reported, not on-chain data to validate the approximations.&#x20;

### **Do you have metrics for total blockchain size?**

No, but we do have a metric for[ Sum Block Size (in bytes) ](network-usage/blksizebyte.md)(BlkSizeByte), which you can sum up to get blockchain size.  You can also use our runningTotal function in our Formula Builder to show the size over time.&#x20;

![ https://charts.coinmetrics.io/formulas/#1178](../.gitbook/assets/BTC\_Total\_Blockchain\_Size\_\(in\_bytes\).png)

### **Do you have metrics for total transactions?**&#x20;

No, we don’t have total transactions, but we have [Tx Cnt](transactions/txcnt.md) (TxCnt or Transactions per interval), which you can sum up to get total transactions.  You can also use our runningTotal function in our Formula Builder to show total transactions over time.&#x20;

![https://charts.coinmetrics.io/formulas/#1179](../.gitbook/assets/BTC\_Total\_Transaction\_Count.png)

### **How can you calculate total transfer value on the Ethereum Blockchain (ETH + other ERC20s)?**&#x20;

You can calculate this manually by summing the [transfer value](transactions/txtfrvalntv.md) for ETH and ERC20s.  You can all use our charting tool to create a stacked view of all ERC20s' Transfer Values, or our formula builder to create an aggregate.

![https://charts.coinmetrics.io/network-data/#1181](../.gitbook/assets/ETH\_ERC20\_Xfer\_Val\_\(USD\).png)

### **What is the best source for daily volume for Tether-Omni, Tether-ERC20, USDC and DAI?**

We have a [Trusted Volume](volume/volume\_trusted\_spot\_usd\_1d.md) metric in Network Data Pro for stablecoins (USDT, USDC, DAI, PAX, BUSD, TUSD, etc.), which represents the volume for these assets on the most trusted exchanges (a subset of our coverage universe).&#x20;

We also have trading volume that occurs on centralized exchanges for every market in our coverage universe available via our Market Data feed.&#x20;

One note:  Centralized exchanges do not differentiate between Tether-Omni, Tether-ERC20, and Tether-TRON markets. They lump all the variants of Tether into one tradeable asset. So it's not possible to break out the trading volume of the different variants of Tether on centralized exchanges.

### **Is there a way to approximate the number of users for a specific blockchain?**&#x20;

You can use the "[Address Count with Balance](addresses/adrbal1inxcnt/)" metrics to approximate this, although you should keep in mind that users may have multiple addresses and certain addresses (e.g., custodian or exchange addresses) may represent multiple users. For day to day use, you can use our active addresses metrics. We provide aggregate [active address metrics](addresses/adractcnt.md) (AdrActCnt) as well as aggregates for [receiving](addresses/adractreccnt.md) and [sending](addresses/adractsentcnt.md) addresses (AdrActRecCnt and AdrActSentCnt).&#x20;

### **Do you have a metric for the number of days BTC is held between transactions?**&#x20;

Since the BTC network uses a UTXO-based data model, we can calculate the number of days BTC is held between transactions by looking at unspent transaction outputs. Our [UTXOAgeMean](https://docs.coinmetrics.io/asset-metrics/network-usage/utxoagemean) metric calculates the average number of days a UTXO-based asset is held between transactions, whereas our [UTXOAgeMed](https://docs.coinmetrics.io/asset-metrics/network-usage/utxoagemed) calculates the median.&#x20;

It's important to note that these metrics are only calculable for UTXO-based networks, so they won't work for account based networks such as Ethereum.&#x20;

### **Why does your FeeTotNtv metric for BTC slightly differ from other data providers?**

This discrepancy is likely the result of using differing timestamps. We use the median block timestamp for BTC, while many other providers calculate this using the miner timestamp.&#x20;

### **How are your aggregated Exchange Flows calculated?**&#x20;

Exchange flows are estimated using the [common-input-ownership heuristic](https://en.bitcoin.it/wiki/Common-input-ownership\_heuristic), which assumes that addresses that are inputs to the same transaction share an owner. This technique is precise, but requires at least one seed address for every exchange, limiting coverage to a predetermined universe of exchanges. The heuristic is also broken by [CoinJoins](https://en.bitcoin.it/wiki/CoinJoin) and [peeling chains](https://en.bitcoin.it/wiki/Privacy#Change\_address\_detection). You can find a bit more context around these methodologies in this [research piece](https://coinmetrics.io/following-flows-ii-where-do-miners-sell/).

### **How are your aggregated Miner Flows calculated?**&#x20;

Miner flows are estimated by basing clustering on an address’s distance in hops from the coinbase transaction. Addresses that have received a coinbase reward, or 0-hop addresses, are assumed to belong to mining pools. 1-hop addresses that have received payment from a 0-hop address are tagged as belonging to miners. This heuristic is less precise than the common-input-ownership heuristic, but roughly [mirrors the structure](https://braiins.com/blog/when-and-why-bitcoin-miners-sell-btc) of mining pool wallets and provides better coverage. You can find a bit more context around these methodologies in this [research piece](https://coinmetrics.io/following-flows-ii-where-do-miners-sell/).&#x20;

### What are the exchanges that serve as constituents for your Trusted Volume metric?&#x20;

Our trusted volume metric is an aggregation of the reported volume from exchanges that we consider the most accurate and trustworthy.  The full list of constituent exchanges included in our Trusted Volume is [here](https://docs.coinmetrics.io/asset-metrics/volume/volume\_trusted\_spot\_usd\_1d).&#x20;

### **Is there a way to calculate ETH staking yield metrics with your Consensus Layer metrics?**

A validator’s expected annual percentage return (APR) from staking rewards accumulated on the Consensus Layer, assuming perfect performance and uptime, can be estimated with the formula below based on protocol parameters ([source for derivation](https://eth2book.info/altair/part2/incentives/issuance#validator-rewards)):&#x20;

$$
2940.21 \div \,     \sqrt[]{ValidatorActOngCnt}
$$

For example, with 423,000 active validators as of September 9, 2022 this comes out to a 4.52% expected return on a validator’s 32 ETH effective balance. The expected annual protocol issuance can also be calculated from the following formula ([source for derivation](https://eth2book.info/altair/part2/incentives/issuance#overall-issuance)):

$$
940.87 \times  \,    \sqrt[]{ValidatorActOngCnt}
$$

With 423,000 active validators this comes out to 611,927 ETH issued per year.

After The Merge, validators will also receive user priority transaction fees on the Execution Layer – sometimes referred to as ‘tips’ – for proposing blocks. The magnitude of this additional source of yield can be inferred from the existing FeePrioTotNtv metric on the Execution Layer. Using a [30-day moving average of tips paid per block](https://charts.coinmetrics.io/formulas/#4308), we can estimate the impact of tips to the validator APR from CL awards above.

**First**, finding the average tips paid per block, which fluctuates greatly depending on the demand for Ethereum blockspace:

$$
sma(FeePrioTotNtv / BlkCnt, 30)
$$

This comes out to 0.07 ETH over the last 30 days.

**Next**, from the equation above we can find the yearly per-validator expected ETH reward from participating on the Consensus Layer with a specified number of active validators:

$$
940.87 \times \sqrt[]{ValidatorActOngCnt} \div ValidatorActOngCnt
$$

​This comes out to an average 1.45 ETH in yearly rewards with 423,000 active validators.

**Then**, with 2,629,800 chances to propose blocks on the Consensus Layer each year, the average number of times a validator will get the opportunity to propose a block (and collect tips) can be found from:

$$
(1/ValidatorActOngCnt) \times (2,629,800)
$$

​This comes to 6.22 with 423,000 active validators (assuming they all have an equal 32 ETH effective balance there is a 1 in _ValidatorActOngCnt_ chance of being selected to propose at a given slot on the CL).

**Finally**, taking this all together:

$$
100\times(((32 +1.45 + (0.07\times6.22))/32) - 1)
$$

​This comes out to 5.89%, an increase of roughly 140 basis points to the APR from Consensus Layer rewards.

However, it is important to note that the information above is purely an expected and theoretical yield given the current number of validators and historical demand for Ethereum blockspace. In practice, individual validator returns will vary by chance as well as performance. We anticipate releasing realized staking yield metrics that take into account validators’ actual observed performance.

To learn more, make sure to check out the Validator Economics section of our [Mapping out The Merge report.](https://coinmetrics.io/special-insights/ethereum-merge/)

### What asset ticker naming conventions does Coin Metrics use?

Coin Metrics assigns a unique ticker symbol for each asset in our coverage universe using the following naming convention: `parentasset[_fullname][_network][_chain]`, where the `fullname`, `network`, and `chain` are optional. Market data and aggregated network data are assigned to the `parentasset` ticker, where aggregated network data consists of data from individual network or chain-specific forms of an asset.&#x20;

To understand our naming convention, we first introduce some important context surrounding the two primary considerations regarding unique ticker symbols.&#x20;

First, what is thought as a singular asset may actually exist in various forms across multiple layer one and layer two blockchains. From the perspective of the blockchain ledger, each form resides on a separate blockchain, and Coin Metrics collects and produces data for each form independently. To differentiate between the specific form, Coin Metrics appends the blockchain ticker as a suffix to the asset ticker. For example, Tether (`usdt`) exists on Tron, Ethereum, Solana, and several other blockchains. To track the network activity of each form, Coin Metrics uses `usdt_tron`, `usdt_eth`, and `usdt_sol` tickers, respectively.&#x20;

Centralized exchanges, however, do not typically differentiate between different forms of an asset. They will allow users to deposit several forms of an asset and credit users internally with a generic parent form of the asset. Trading then occurs using the generic form of the asset, and all market data collected by Coin Metrics is assigned to the parent ticker.&#x20;

Returning to the Tether example, a centralized exchange may allow a user to deposit the ERC-20 form of Tether, which resides on Ethereum, as well as the TRC-20 form of Tether, which resides on Tron. Regardless of which form a user deposits, the user is credited with a generic parent form of Tether which is traded on all markets on the centralized exchange. Therefore, market data such as trades are assigned to the parent asset `usdt`.

Coin Metrics also aggregates data from individual forms of an asset to the parent asset for certain metrics. Therefore, metrics under the parent asset `usdt` represent an aggregation across `usdt_tron`, `usdt_eth`, and the other individual forms of Tether.&#x20;

Second, some assets may share the same display ticker as another asset. To resolve these ticker conflicts, Coin Metrics ensures that each asset ticker in our coverage universe is unique by appending the full name of the asset as a suffix to the asset ticker. For example, both Starcoin and Starchain share the same display ticker of `stc`. Coin Metrics resolves this ticker conflict by assigning the tickers `stc_starcoin` and `stc_starchain`, respectively.&#x20;
