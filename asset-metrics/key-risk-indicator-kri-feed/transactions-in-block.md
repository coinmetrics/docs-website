# Transactions in Block

**Definition**

The count of all transactions within the most recent block processed.

**Dictionary**

| Name                  | MetricID         | Category | Sub-category     | Type | Unit                  | Interval |
| --------------------- | ---------------- | -------- | ---------------- | ---- | --------------------- | -------- |
| Transactions in Block | block\_tx\_count | KRI      | Block Attributes | Sum  | Count of transactions | 1b       |

**Methodology**

The most recent block we processed within a 1-minute window is evaluated and the number of transactions within the block are counted. For UTXO based currencies, this includes the coinbase transaction.

**Available Assets**

Bitcoin (BTC), Ethereum (ETH)

**Sample Query**

{% embed url="https://api.coinmetrics.io/v4/timeseries/asset-metrics?api_key=%3Cyour_key%3E&assets=eth&frequency=1b&metrics=block_tx_count&pretty=true" %}
