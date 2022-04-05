---
description: https://charts.coinmetrics.io/correlations/
---

# Correlation Tool

## Correlation Coefficient

A correlation coefficient is a number between -1 and 1 measuring the strength of a relationship between two variables.  A positive correlation means that returns move together.  If you plotted returns of two cryptoassets on a scatterplot, dots sloping upwards and right in a diagonal line would imply a positive correlation.  Note that no causality is inferred.  The actual derivation involves taking the covariance of two variables.  Covariance tells you whether two variables move together or not, but it is unbounded and unstandardized.  Finding a correlation involves standardizing those arbitrarily large figures by dividing by the sample standard deviations of both variables.  This reduces covariance to a range between -1 and 1, and it is now informative as to the magnitude of moves between two assets.  Put simply correlation tells you:

1. whether two variables are related, and
2. the magnitude of their inter-relatedness

## Tool Options

The tool offers the user several options for determining the correlation coefficient:

* Pearson vs. Spearman
* Log vs. Arithmetic Returns
* Timeframe:  30/60/90/180/360 days
* Handing of Data Gaps: Linearly Interpolate or Exclude

## Pearson and Spearman Correlation

Our tool presents two options for correlation:  Pearson and Spearman Correlation.

![Find this toggle below the chart](<../../.gitbook/assets/Screen Shot 2020-12-19 at 4.07.39 PM.png>)

The orthodox and conventional way of doing things in finance is to take the **Pearson** correlation of **logarithmic daily** asset **returns**, preferably over a long period.  If you aren’t interested in getting into any additional complexity, you can stop there and use those settings on the charts.

(A common mistake in correlating assets is to use raw prices rather than returns. This is a mistake, as prices are often trended and non-stationary, meaning that you often get spurious positive correlations.  Our tool uses the asset returns.)

### Pearson

Pearson correlation basically assumes that the relationship between the two variables is linear, and it measures it on this basis.  If you have nonlinear yet meaningful relationships, Pearson will report a weak correlation, when in fact there may be something interesting going on behind the scenes.

One solution to this problem is using [log daily returns](https://mathbabe.org/2011/08/30/why-log-returns/), which helps in processing data, and has some other useful properties if the data is normally distributed. &#x20;

### Spearman

To give our users an alternative, we introduced Spearman correlation.

Spearman correlation  takes a ranking of all the data points in the sample, and then it runs a Pearson correlation on the rankings data.  It then compares the two variables based on how much their _rankings_ move together.  This enables the ability to capture co-movements in datasets that are nonlinear. Spearman would find the correlation between a perfect exponential relationship as 1, whereas Pearson would declare it positive but not perfectly correlated.

For more on this, we suggest reading this [excellent breakdown](http://support.minitab.com/en-us/minitab-express/1/help-and-how-to/modeling-statistics/regression/supporting-topics/basics/a-comparison-of-the-pearson-and-spearman-correlation-methods/) in the differences between the two. To put it simply: if you think your variables are linearly related, and you want to measure the strength of those co-movements, use Pearson correlation. If you want to capture variables which move together, but not at a constant rate (as with an exponential relationship), consider Spearman correlation.  Spearman makes no assumptions as to linearity but simply assesses the relationship in terms of whether one variable increases when the other increases, and vice versa.

## Arithmetic vs Logarithmic Returns

While Arithmetic Returns are easily understood, as mentioned above, there are some good reasons for using a Logarithmic Return in certain occasions.  Our took allows you to choose Arithmetic or Logarithmic returns.&#x20;

![Find this toggle below the chart](<../../.gitbook/assets/Screen Shot 2020-12-19 at 5.17.07 PM.png>)

## &#x20;Timeframe

The tool allows you to  select the number of daily observations to consider when comparing returns to determine the data sets' correlation. &#x20;

![Find the timeframe options below the chart](<../../.gitbook/assets/Screen Shot 2020-12-19 at 4.46.22 PM.png>)

If, for example, you picked 180 days, the 180 daily returns prior to the point/date on the chart were considered when determining the correlation coefficient returned for the two data series at that point/date on the chart.  In other words, the number you see for _today_ refers to a sample of the previous 180 days.

Keep in mind that if you "exclude gaps" in the data set (see below), then the number of days selected will reflect only the number of days for which there are observations.

## Handling of Data Gaps

On occasion, you may want to compare a continuous data series with one with gaps (such as when you compare cryptoasset returns with a traditional index like S\&P500 that has no values on the weekends or holidays).  The tool gives you two options for handling this:

* Linearly interpolate the data to derive a value for the data gap prior to calculating the returns
* Exclude the observations on the dates where one data series has a gap, but the other doesn't prior to calculating the returns (note:  this results in fewer observations for the non-gapped series)

The tool will default to "excluding" data where gaps are identified.  You can adjust this setting from the settings menu on the right toolbar.

![Click on the "gear" to find the settings for Data Gaps](<../../.gitbook/assets/Screen Shot 2020-12-19 at 4.48.10 PM.png>)

## Interpretation

Let’s say you a Pearson correlation of the logarithmic returns for the previous 180 days. This number means “in the 180 days leading up to the point on the chart you’re looking at, the two assets that you have selected had co-movement in their daily returns of a magnitude corresponding to x.”   If x is 1, their daily returns were perfectly positively correlated in the 180-day period leading up to the date where you observe the coefficient of 1.  If x is 0.3, their returns moved together more often than not, but they weren’t particularly closely linked. &#x20;

## Constraints

Attempting to predict the future by looking at historical returns is always somewhat fraught. There’s no guarantee that a historical correlation will persist into the future. Because of this, we recommend looking for useful correlations over longer periods.

Things that should grab your attention: &#x20;

1. Very positive correlations between two assets, especially over longer periods of time.  Consistently high correlations deserve investigation.&#x20;
2. Persistent negative correlations of any sort are tremendously interesting, albeit rare.  The strength of the signal increases with the quantity of historical evidence.

Be aware that different market phases exist.   Longstanding correlations can break down during certain market conditions.    &#x20;

&#x20;Try to discern when your correlation analysis holds little explanatory power.  Avoid mistaking noise for signal.  And use this tool with caution.

It’s also worth reading more about the statistical underpinnings of correlation measures.  \
