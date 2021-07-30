# Index FAQs

#### **How are the CMBI Single Asset Index prices calculated?** 

The pricing inputs for our Indexes are informed by our Reference Rates methodologies.  We have methodologies for both hourly rates and real time rates. 

* [Real Time Reference Rates  ](https://coinmetrics.io/wp-content/uploads/2021/04/rtrr-methodology.pdf)
* [Hourly Reference Rates  ](https://coinmetrics.io/wp-content/uploads/2021/04/reference-rates-methodology.pdf)

Our hourly and daily CMBI levels use our Hourly Reference Rates and our 15 second levels use our Real Time Reference Rates.   

**What's the difference between your reference rate and a single-asset index for the same asset?** 

The calculation methodology for reference rates and single-asset indexes are identical and they both represent the price for a specific asset. However, the constituent markets can be different for indexes \(depending on the asset\) due to a higher consideration for investability. Additionally, single-asset indexes are administered under different policies that are specific for indexes, such as additional reporting requirements and policies for dealing with corporate actions like hard forks and airdrops. Additional information on the differences can be found here: 

* Single-asset indexes tend to use regulated U.S.-based exchanges as the constituent markets, while a reference rate for the same asset would not have this restriction and choose from a larger pool of global constituent markets. You can learn more about our Market Selection Framework [here](https://coinmetrics.io/wp-content/uploads/2021/02/reference-rates-market-selection-framework-v1-0-2.pdf). 
* Since single-asset indexes are investable financial products, there is a lot stricter change/consultation process in the case of any significant methodology changes.
* Since single-asset indexes are investable financial products, we generally don't recalculate history since trades or fund accounting may have occurred around printed levels \(defined in our recalculation policy\), whereas if we change the reference rate history, we may conduct a full historical value recalculation.

#### **Is there an Index equivalent of AssetEODCompletionTime for Indexes? When should I expect an EOD Index to complete its computation?**

Completion timing is less relevant for indexes as the publishing time for those values is largely deterministic and doesn't vary.  Blockchain metrics have to wait a few blocks for finality and suffer from the non-deterministic block mining times. However, the index rates for EOD \(either NYC, UTC, or Singapore\) are computed at 5 minutes past the hour and usually available within a minute or so. 

#### **What are all of the Constituent Exchanges included in the Bitcoin Index, along with details such as the domicile, regulation and legal compliance?**

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Exchange</b>
      </th>
      <th style="text-align:left"><b>Domicile</b>
      </th>
      <th style="text-align:left"><b>NY Bit License  </b>
      </th>
      <th style="text-align:left"><b>Money Service Business</b>
      </th>
      <th style="text-align:left"><b>Broker Dealer</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Coinbase</td>
      <td style="text-align:left">Delaware Corporation</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Kraken</td>
      <td style="text-align:left">Delaware Corporation</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Bitstamp (USA)</td>
      <td style="text-align:left">Delaware Corporation</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Gemini</td>
      <td style="text-align:left">New York Trust Company</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">itBit</td>
      <td style="text-align:left">New York Trust Company</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Binance.US (Operated by</p>
        <p>BAM trading Services)</p>
      </td>
      <td style="text-align:left">California</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Bittrex</td>
      <td style="text-align:left">Delaware Corporation</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>As of 2021-05-01</em>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

You can find the latest constituent markets in the single asset [fact sheet](https://coinmetrics.io/wp-content/uploads/2021/05/CMBI-Single-Asset-Series-Factsheet.pdf).

#### **What are the criteria considered for an exchange to become a Constituent Exchange?**

Please refer to our [market selection framework](https://coinmetrics.io/wp-content/uploads/2021/02/reference-rates-market-selection-framework-v1-0-2.pdf) for detailed information on this. 

**You state that the Index does not currently utilize data from over-the-counter markets or derivatives platforms but that may decide to do so in the future. What are the factors that the Index Provider considers in determining whether to utilize data from the over-the-counter markets or derivative platforms?**

This provides us with future optionality. Our expectation is that given the current market structure and momentum, public spot markets with transparent pricing will remain and we will not have to leverage OTC markets. But there is a non zero chance that OTC markets become more dominant \(similar to Gold whose primary market is the London Bullion Market which is OTC\), in which case the Oversight Committee may determine OTC markets as the best venue to derive index pricing from.  
  
  
****

