Happiness World Report
================
Corrie
February 23, 2019

The Data
--------

We will be using the data as provided by the World Happiness Report. The report from 2018 can be found [here](https://s3.amazonaws.com/happiness-report/2018/CH2-WHR-lr.pdf).

For the happiness score, respondents are asked where they stand on the *Cantril Ladder*. The Cantril Ladder consists of 10 steps, where the top is your best possible life and the bottom the worst possible life.

![](cantril_ladder.png)

In this report, the scale goes from 0 to 10, that is, 0 is the worst possible life and 10 the best possible.

The responses are averaged on a country-year level. The report also includes variables that could explain the differences in the happiness scores. Note that these explanatory variables were not used to compute the happiness score. A detailed description of these additional variables, their sources as well as number of respondents per year and country can be found [here](https://s3.amazonaws.com/happiness-report/2018/Appendix1ofChapter2.pdf).

The supporting data also includes a region indicator for the different countries. We can roughly sort these region indicators to their continents which makes it easier for plotting later. Note that Australia and New Zealand are in the same region as the US and Canada and thus landed on the continent Americas.

The World Happiness Report only provides the Log of the GDP and by the time of publication, the GDP of 2017 wasn't available yet and extrapolated in the report. We can use the updated version of the GDP as provided by the [World Bank](https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD). We use the GDP per capita in purchasing power parity (PPP) at constant 2011 international dollar prices.

How happy are people around the world?
--------------------------------------

So before we look at the explaining factors, let's have a look people are in general around the World. ![](EDA_files/figure-markdown_github/unnamed-chunk-5-1.png)

Even thought the ladder goes from 0 to 10, the worst average rating a country can have is around 2.5 and the best rating is around 7.6. On average, people seem to be more on the happier side.

An intersting question is here, did happiness improve over time? The report goes back to 2005 (though many countries are only included later) and the newest observation is from 2017. ![](EDA_files/figure-markdown_github/unnamed-chunk-6-1.png)

It seems that overall and for most countries, there is not much of a trend in the happiness score. The happiness drop at the year 2006 seems to be mostly due because that year more countries were included than in the year before. The top happiness scores seems to be dominated by European countries and the bottom scores are dominated by African countries. We can also see some African countries in the top range.

Let's have a closer look how the happiness scores are distributed geographically over the world. Since there didn't seem too much change in the happiness scores, we simply take the average for each country over all reported years. This way, we can include most countries since some countries have missing observations in some years. ![](EDA_files/figure-markdown_github/unnamed-chunk-7-1.png)

Most Western Countries seem to get a quite high happiness score in this report while many countries in Africa have quite low scores.

Interesting are here in particular countries such as Yemen, Afghanistan or Cambodia that have very low scores but are surrounded by countries with higher scores (Saudi Arabia and Oman for Yemen; Turkmenistan and Pakistan for Afghanistan; Thailand and Vietnam for Cambodia). Both Yemen and Afghanistan have been in the news the last decades because of ongoing conflicts and crises. While Cambodia has been stable for some time by now, their conflicts during the 90s still seem to affect their happiness level today.

Suporting Factors
-----------------

### Economic Factors

Let's have a closer at the supporting factors that are included in the report. Two different economical indicators are provided: The GDP per capita and the Gini index. The household Gini index measures the inequality among household incomes. A Gini index of 0 signifies perfect equality while a index of 1 means maximal inequality. The generosity factor is computed with relation to the GDP: People were asked if they have donated to charity in the past month. The binary answers are then aggregated on a national level and regressed on by the GDP per capita. The generosity value is then the residual, that is, it gives an indicator if people give more or less money to charity than would be expected by their GDP. ![](EDA_files/figure-markdown_github/unnamed-chunk-8-1.png)

We can see that the GDP has a positive correlation with the happiness score while the Gini index has a negative correlation (albeit weaker). Generosity only seems to be positively correlated with happiness for European countries.

### Social and Health Factors

Three social factors are included in the data:

-   `social`, the answer to the question "If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?", aggregated on a national level.
-   `health`, the Healthy Life Expectation, gives the number of years a person is expected to live in good health.
-   `pos_affect` is the average to three questions about how a person felt the previous day: Were they happy, laughed, smiled and were mostly enjoying themselves.
-   `neg_affect` is the average to three questions about how a person felt the previous day: Did they worry, were they sad or angry.

![](EDA_files/figure-markdown_github/unnamed-chunk-9-1.png)

Except for negative affect are all factors strongly positively correlated with happiness. Negative affect is obviously negatively correlated with happiness.

### Political Factors

The data provides 5 political factors:

-   `freedom`
-   `corruption`
-   `gov_confidence`
-   `democracy`
-   `delivery`

![](EDA_files/figure-markdown_github/unnamed-chunk-10-1.png)

![](EDA_files/figure-markdown_github/unnamed-chunk-11-1.png)

![](EDA_files/figure-markdown_github/unnamed-chunk-12-1.png)

Add Population Data
-------------------

We can easily add further data. For example, the World Bank also provides yearly [population data](https://data.worldbank.org/indicator/sp.pop.totl)

![](EDA_files/figure-markdown_github/unnamed-chunk-14-1.png)

[Temperature Data](https://datacatalog.worldbank.org/dataset/climate-change-knowledge-portal-historical-data)
