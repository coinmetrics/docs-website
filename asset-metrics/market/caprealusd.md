# Realized Market Cap (USD)

## Definition

The sum USD value based on the USD closing price on the day that a native unit last moved (i.e., last transacted) for all native units.

| Name                      | MetricID   | Category | Subcategory           | Type    | Unit | Interval |
| ------------------------- | ---------- | -------- | --------------------- | ------- | ---- | -------- |
| Realized Market Cap (USD) | CapRealUSD | Market   | Market Capitalization | Product | USD  | 1 day    |

## Details

* This metric takes the ledger state of the asset, assigns a date of last movement for each account/unspent output, multiplies the balance of the account/value of the output by the price at the date of last movement and sums all of those numbers for the asset’s ledger.
* The state of the ledger is the one at the last available block for that day.
* Only the native units balance is considered, L2 tokens (ERC-20, etc.) are not taken into account.
* For UTXO chains, last activity is the date of creation of the output.
* For account-based chains, last activity is either the last date the account was the sender of a ledger change, or its time of creation, whichever is more recent.

## Chart

![https://charts.coinmetrics.io/network-data/#581](../../.gitbook/assets/Market\_Cap\_and\_Realized\_Cap.png)

## Asset-Specific Details

* This metric is not available for assets that have full privacy, like Monero, Grin.
* For assets that have opt-in privacy features, like ZCash, it only takes the non-private balances into account. The realized cap is first computed over the non-private balances, then scaled so that ratios like MVRV can be computed:Realized Cap = Non-private realized Cap + Private Supply \* (Non-private realized cap/ (Total Current Supply - Private supply))This can be understood as taking the non-private supply’s price implied by the realized cap (Non-private realized cap / Non private supply) and assigning that price to the private supply.

## Example

For an asset whose ledger is:

| Account | Balance | Time of last movement | Price at last movement | Realized balance |
| ------- | ------- | --------------------- | ---------------------- | ---------------- |
| A       | 100     | 2010-01-01            | $0                     | $0               |
| B       | 1000    | 2016-01-01            | $10                    | $10,000          |
| C       | 500     | 2019-01-01            | $100                   | $50,000          |

The realized cap would be $0 + $10,000 + $50,000 = $60,000

For assets like ZEC, assuming there’s 5M native units outstanding, 1M private, 4M non-private. If the realized cap of the non-private supply is $1B, the total realized cap is computed as: $1B \* (1M \* ($1B / (5M - 1M)) = $1.25B

## Release History

* Conceptualized by [Coin Metrics](https://coinmetrics.io/realized-capitalization/)
* Released in the 1.0 release of NDP

## Interpretation

Realized capitalization (sometimes referred to as Realized Value) is one of Coin Metrics’ flagship metrics, first introduced in a [talk by Nic Carter](https://medium.com/@RainDogDance/bitcoin-as-a-novel-market-institution-nic-carter-talk-at-baltic-honeybadger-2018-e085f163b213) in 2018. Realized cap aggregates units of supply according to their market price when they last moved on-chain. The original intent was to discount the weight of long-lost coins, in particular in Bitcoin, as a significant fraction of supply is inert and has not moved since 2010 (and can be presumed lost). Additionally, realized cap is a more faithful measure of economic significance for forks with limited uptake, as conventional measures like market cap naively presume that the entire stock of coins is liquid and market-available. Interpretations vary, but realized cap is perhaps best-understood as a metric which captures the average cost basis of all current holders. It has been used to devise popular oscillators and derivative metrics.

## See Also

* [Introduction to Realized Cap](https://coinmetrics.io/realized-capitalization/)
* [SOTN: Realized Cap Passes $100B](https://coinmetrics.substack.com/p/coin-metrics-state-of-the-network-fe8)

## Availability for Assets

{% embed url="https://coverage.coinmetrics.io/asset-metrics/CapRealUSD" %}
