# DeFi FAQs

### **Can the daily number of unique buyers be derived from DEX swaps data?**

Each DEX swap served via the _market-trades_ endpoint is associated with 3 different Ethereum addresses:

* **Initiator** is the Ethereum address which submitted the transaction, as a result of which the swap occurred
* **Sender** is the Ethereum address that invoked the liquidity pool smart contract's function for swapping
* **Beneficiary** is the Ethereum address credited with the output tokens upon the completion of a swap

The swap _beneficiary_ address can be used to approximate the number of unique buyer addresses over a given timeframe.

