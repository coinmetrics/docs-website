# Index FAQs

### **How are the CMBI Single Asset Index and CMBI Multi Asset Index levels calculated?**&#x20;

The price inputs for our indexes are informed by our reference rates methodologies.  We have methodologies for both hourly rates and real-time rates. Our hourly and daily levels use our Hourly Reference Rates methodology and our 15 second levels use our Real-Time Reference Rates methodology. Links to the methodology documents are listed below.&#x20;

* [Coin Metrics Prices Policies](../market-data/methodologies/coin-metrics-prices-policies.md)
* [Coin Metrics Prices Methodology](../market-data/methodologies/coin-metrics-prices-methodology.md)

### **What's the difference between your reference rate and a single-asset index for the same asset?**&#x20;

The calculation methodology for reference rates and single asset indexes are identical and they both represent the price for a specific asset. However, the constituent markets used in the calculation can be different because our indexes require a higher consideration for investability. Additionally, single asset indexes are administered under different policies that are specific for indexes, such as additional reporting requirements and policies for dealing with corporate actions like hard forks and airdrops.&#x20;

Single asset indexes tend to select markets from regulated U.S.-based exchanges, while a reference rate for the same asset evaluates a larger pool of global constituent markets. You can learn more about our [Market Selection Framework](../market-data/methodologies/coin-metrics-prices-methodology.md#data-inputs) which selects high quality constituent markets for our reference rates. Our indexes then use these markets and excludes certain markets to enhance the investability of the index. &#x20;

Our single asset indexes are linked to investable financial products, so there is a stricter change and consultation process in the case of any methodology changes. Single asset indexes also have a different revision policy than our reference rates since trades or fund accounting may have occurred around printed levels, whereas we occasionally conduct recalculations of limited portions of reference rates history to increase the quality of the rates. &#x20;

### **Is there an index equivalent of the metric `AssetEODCompletionTime`? When should I expect an end-of-day index value to be published?**

Completion timing is less relevant for indexes as the publishing time for index values is largely deterministic. Blockchain metrics must wait a few blocks for finality and are impacted by non-deterministic block mining times. The index rates for end-of-day values (New York, Singapore, or UTC) are computed at 5 minutes past the hour and usually available within a minute.&#x20;

### **What are the constituent exchanges included in the CMBI Bitcoin Index, along with details such as the domicile, regulation and legal compliance?**

| **Exchange**    | **Domicile**           | **NY Bit License**   | **Money Service Business** | **Broker Dealer** |
| --------------- | ---------------------- | -------------------- | -------------------------- | ----------------- |
| Coinbase        | Delaware Corporation   | Yes                  | Yes                        | Yes               |
| Kraken          | Delaware Corporation   |                      | Yes                        |                   |
| Bitstamp (USA)  | Delaware Corporation   | Yes                  | Yes                        |                   |
| Gemini          | New York Trust Company | Yes                  | Yes                        |                   |

You can find the latest constituent markets in our [fact sheet](https://cmbi-indexes.coinmetrics.io/cmbibtc).

### **What are the criteria considered for an exchange to become a constituent exchange?**

Please refer to our [Market Selection Framework](../market-data/methodologies/coin-metrics-prices-methodology.md#data-inputs) for more information.

### **The methodology states that the index does not utilize data from over-the-counter markets or derivatives platforms but may do so in the future. What are the factors in determining whether to utilize data from the over-the-counter markets or derivative platforms?**

This clause in the methodology provides us with future optionality. Given the current market structure, our expectation is that spot markets with transparent pricing will retain meaningful trading volume, and we will not have to select over-the-counter or derivatives markets. That being said, there is a non-zero chance that over-the-counter or derivatives markets may become more dominant (similar to gold in which the primary market is the London Bullion Market, an over-the-counter market), in which case the Coin Metrics Oversight Committee, after considering all available information, may determine that these markets serve as the best venues to derive index pricing from.
