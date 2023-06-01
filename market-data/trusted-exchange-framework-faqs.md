# Trusted Exchange Framework FAQs

Coin Metrics maintains our [Trusted Exchange Framework](https://coinmetrics.io/special-insights/trusted-exchange-framework/) which quantitatively and rigorously assesses exchanges across various dimensions of quality.

### How often is the trusted exchange list updated?

The list is updated semi-annually in Q1 and Q3.

### When is the data collected and reviewed?

The trusted exchange results will reflect data representative as of the end of the previous quarter. In other words, Q1 results will reflect data collected as of the end of the previous year’s Q4, and Q3 results will reflect data collected as of the end of Q2 of that year.

### Would you consider including \_\_\_\_ as part of the criteria?

We welcome any feedback on how to improve the trusted framework. Note that the ability to add criteria to the framework depends on if this data is publicly available.

### Does the trusted exchange framework include futures exchanges?

Yes. However, we only assess the data quality score for spot exchanges. The lack of data quality score does not count against a futures exchange’s overall score, but it does disqualify them from being included in the trusted spot volume metric.

### Is there a certain score level that separates trustworthy from not?

It depends on the use case, which features are most important to the user, and the threshold that a user is willing to accept. Generally, we consider anything above 0.8 in a subscore to be of high quality, particularly for the data quality score. Please see [Why are certain subscores assigned different weights?](https://app.gitbook.com/o/-MQCo4hL7kbGqmZBgS2j/s/-MO23j33wWGzm0NrZseN/\~/changes/866/market-data/trusted-exchange-framework-faqs#why-are-certain-subscores-assigned-different-weights) for more information.

### Why are certain subscores assigned different weights?&#x20;

These weights and overall scores reflect a holistic average of an exchange’s overall capabilities. However, we acknowledge that an exchange’s trustworthiness depends on the use-case, i.e. as a custodian, data provider, and so on. We generally recommend users to focus on the sub scores they find most useful for their use-case.

### How should we interpret the overall score?

Please see [Why are certain subscores assigned different weights?](https://app.gitbook.com/o/-MQCo4hL7kbGqmZBgS2j/s/-MO23j33wWGzm0NrZseN/\~/changes/866/market-data/trusted-exchange-framework-faqs#why-are-certain-subscores-assigned-different-weights) for more information.

### How should we interpret the data quality / infrastructure / resilience / compliance scores?

Generally these scores are composite pass/fail scores based on a given criteria (e.g. does it pass Benford’s Law). Often these features are assigned binary scores with equal weights with respect to the other features in the same category. These scores are not to be represented as probabilities.&#x20;

### Can the list of trusted exchanges be accessed via the API?

As of May 2023, we do not surface this list via the API.

### What’s the difference between the Market Selection Framework and Trusted Exchange Framework?

The "Trusted Exchange" framework assesses exchanges for presence of organic trade volume, using features such as fake volume tests and regulatory features. It informs which exchanges make up our "trusted volume" calculation and the trusted exchanges for datonomy.&#x20;

The Market Selection Framework assesses exchange-asset-pair markets to input for CM reference rates. This framework may use exchange-specific features that overlap with the trusted exchange framework but it produces a separate output and is not an input to datonomy.&#x20;

### Why was \_\_\_ exchange given this score?

We are happy to elaborate deeper as to why exchanges are assigned their scores. Please reach out to us at info@coinmetrics.io.
