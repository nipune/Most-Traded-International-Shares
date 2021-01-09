# Project1 - Most Traded International Shares
## Our struggles

This project came about after a couple of pivots. 
Intially the team wanted to do a 'Green Energy" project, the idea was to look into Green Energy and ultimately answer a question such as
- How does Australia compare against other countries in terms of Green energy use?
![Greentech](https://github.com/nipune/Project1/blob/main/images/cleantech.png)
Upon investation the idea was too narrow in terms of available 'Green energy companies". 
Defining and finding supporting data was difficult e.g. AGL - How green is AGL if it sells both 100% renewable and also traditional energy?

This led to us pivoting into 'Clean Technology' - a slight difference which would broaden the available companies to research.
We found an Australian based (Deloitte) Cleantech list and an equivalent Canadian list but this item ran into difficulty 'pulling' the share price information.

Free ASX information via an API did not seem to exist, or our Python package was too new to work with e.g. RapidAPIs Yahoo Finance offering!

We decided to stick to the tools we knew worked to pull data, but stretch ourselves by applying them to a different question. 

Ultimately we found an interesting page on [(Commsec)](https://www.commsec.com.au/mosttradedinternationalshares)

## Our project - To validate whether top traded international shares had merit
![Commsec](https://github.com/nipune/Project1/blob/main/images/commsec.png)

Our objective became to understand whether the top traded international shares (by volume) from Australian Commsec clients actually outperformed the S&P 500.

Whilst the list contained 20 shares, we chose to look at 10 and compare this list to the S&P 500. The companies we analysed are:
1. Tesla (TSLA)
2. Apple (AAPL)
3. Pfizer (PFE)
4. Microsoft (MSFT)
5. MRNA (MRNA)
6. Nuveen Municipal Opportunity Fund (NIO)
7. Amazon (AMZN)
8. Nano Dimension Ltd. (NNDM)
9. Salesforce.com (CRM)
10. Nvidia (NVDA)

The hypothesis was that these shares should at least be returning more than an index at a minimum.

## Our Findings
The findings were interesting, and it has become apparent that a null check or inner join is not enough to confirm you have 'clean data'.
It only became apparent when interpreting the results. A key question/sense check was 'did any stock actually not outperform the SP500?

Our analysis showed that AAPL did not outperform the S&P500, which is extremely odd given their SP ended 2020 at ~$132. Further analysis showed
Fundamental Analysis to be the culprit, it can be seen that AAPL price was $498 on 28th of August 2020, then it drops dramatically to $128.

![dd1](https://github.com/nipune/Project1/blob/main/images/dd1.png)
![dd2](https://github.com/nipune/Project1/blob/main/images/dd2.png)

This behaviour is also apparent in TSLA whilst plotting their daily close prices.
![ddchart](https://github.com/nipune/Project1/blob/main/images/ddchart.png)

Following the trail and comparing the close prices to Google Finance, it is apparent that we've pulled data which needs further investigation i.e. is there
some sort of share consolidation in play that is not reflected? Has Google Finance data been normalised? Adjusted closing prices may offer further insight to this.

In conclusion, it appears most of the top ten stocks began to rally at the onset of global restrictions and search for solutions of the Covid-19 pandemic. Further, a majority of the top 10 stocks did perform better than the SP 500 index when viewed from a returns vs. risk perspective.

References:
1. [Clean Tech AU](https://www2.deloitte.com/content/dam/Deloitte/au/Documents/energy-resources/deloitte-au-enr-issue7-datcIndex-September2020.pdf)
2. [Clean Tech CAN](https://www.canadianinvestor.com/tsx-clean-technology-companies/)

