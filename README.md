# KDD Project COVID19

Team Members:
-
- Khabiyrul Gainey
- Rikitha Muddana
- Sunil Kumar Mumudi Narasimhan
- Jack Phillips
- Sasha Zhyk

Project Introduction:
-
Coronavirus is the virus that causes respiratory infection regardless of age or gender. It affected the lives of every human across the globe.  The World Health Organization’s (WHO) chosen name, COVID-19, is just short for “coronavirus disease 2019”. Virus originated in late 2019 in the city Wuhan, China. Since then it spread quickly across the globe during the first months of 2020 and reached more than fifteen million confirmed cases by the second half of July.

As pandemic has spread across the globe, the virus has left a trail of deaths across continents and countries. Death numbers in Europe and North America are now much larger than in Asia. Where in Latin America, Caribbean and South America a number of  cases are still rising along with deaths. Different continents and countries  epidemics followed different trajectories however certain territories have been affected more than others.

Some of the countries were very successful in limiting the spread of virus and others were hit pretty hard. In order to slow down the spread of COVID-19  governments around the world have ordered its citizens to stay at home and practice distancing to help limit coronavirus pandemic. 

In our project we decided to look at the effect of stay at home policy on the number of  new cases by million  and confirm that there is a relationship between implemented measures and infection rate. 


Research Question:
-
Estimating impact of stay at home requirements to slow down the number of cases due to the Covid-19 using interrupted time series analysis technique. 

Relevant Domain:
-

https://academic.oup.com/jpubhealth/article/doi/10.1093/pubmed/fdaa087/5857763

https://thehill.com/changing-america/well-being/longevity/497097-those-who-died-from-covid-19-lost-more-than-a-decade-of

https://www.businessinsider.com/study-finds-that-people-who-have-coronavirus-could-die-10-years-early-2020-5

https://www.pewresearch.org/fact-tank/2020/04/22/populations-skew-older-in-some-of-the-countries-hit-hard-by-covid-19/

https://hub.jhu.edu/2020/04/02/stay-at-home-order-end-date-affects-compliance/

https://www.cidrap.umn.edu/news-perspective/2020/05/stay-home-orders-likely-slowed-covid-19-spread-study-finds

https://www.medscape.com/viewarticle/930614

https://www.minnpost.com/second-opinion/2020/05/stay-at-home-orders-linked-to-significant-decrease-in-covid-19-hospitalizations-u-of-m-study-finds/

https://www.bsg.ox.ac.uk/research/publications/variation-government-responses-covid-19
https://www.frontiersin.org/articles/10.3389/frai.2020.00041/full



Data Sources:
-

For our project we decided to merge two datasets:

https://ourworldindata.org/coronavirus-source-data

We first utilized data that was made available by European Center for Disease Prevention and Control (ECDC) that was made available to us by “our world in data”. ECDC  collects and harmonizes data from around the world via national health agencies  which allows us to compare and contrast what is happening in different  countries. 

https://ourworldindata.org/grapher/stay-at-home-covid?time=2020-01-01..
The Oxford Covid-19 Government Response Tracker (OxCGRT) collects systematic information on which governments have taken which measures, and when. This can help decision-makers and citizens understand governmental responses in a consistent way, aiding efforts to fight the pandemic. The OxCGRT systematically collects information on several different common policy responses governments have taken, records these policies on a scale to reflect the extent of government action, and aggregates these scores into a suite of policy indices.

The COVID-19 (coronavirus) outbreak has prompted a wide range of responses from governments around the world. There is a pressing need for up-to-date policy information as these responses proliferate, and governments weigh decisions about the stringency of their policies against other concerns. The authors introduce the Oxford COVID-19 Government Response Tracker (OxCGRT), providing a systematic way to track the stringency of government responses to COVID-19 across countries and time. 

For our purposes we are using their stay at home measures recorded for each country to join to our main dataset. This measure has three levels. Below are  coded  response categories for stay at home policy:

0 - No measures

1 - recommend not leaving the house

2 - require not leaving the house with exceptions for daily exercise, grocery shopping, and ‘essential’ trips

3 - Require not leaving the house with minimal exceptions (e.g. allowed to leave only once every few days, or only one person can leave at a time, etc.)

No data - blank


Approach:
-
  **Data Understanding and EDA:**
  
The main features we are looking at in our data are location (country), date, new cases per million, deaths per million, and stay at home requirements. 

We have performed Exploratory data analysis on our data. EDA refers to the critical process of performing initial investigations on data so as to discover patterns, to spot anomalies, to test  hypotheses and to check assumptions with the help of summary statistics and graphical representations. 

Our main concern was to check for correlation amongst  features, that lead us to using the correlation matrix in determining. Our idea is to pick a few countries that have been highly affected and then ultimately analyze the effect, the stay at home requirements has on the new_cases_per_million

Here we have a chart showing daily new cases per million for Italy :

![](https://i.imgur.com/Cxl1nfa.png)
  
  
  **Data Preparation:**
  Data preparation is a vital step of the data science process for any valuable insights to pop up. We must explore the quality of our data, seeking to understand both its state and limitations. The foremost and important step of the data preparation task that deals with correcting inconsistent data is filling out missing values and smoothing out noisy data. Our data contains a huge number of missing values that we are dealing with, all of which, either will be imputed or dropped depending on the effectiveness.

We would also like to check for few of the other cleaning methods that might be necessary for our data:
- Check the data for outliers and redundant values.
- Check for binning the categorical variables.
- Check if the data type for the columns needs to be converted. For instance, date columns.
- Check the data for multicollinearity.
- Check for skewness and Normality. If any of the variable does not follow normality, transformations such as log, inverse can be applied so that it does not affect the data
- Consider standardizing the features, if necessary.
- Consider feature engineering, if necessary. For instance, the date column can have separate columns for day and month.
- We can consider one hot encoding or creating dummy variables for the categorical features.


  
 **Machine Learning:**
  
Here we are going to use modeling techniques in order to predict future new covid cases. This will be done using an interrupted times series model. Currently we are using a ARIMAX model to predict new cases based on when countries inacted stay at home orders. 

Here we have a prototype of the ARIMAX model for Italy. A new variable was created called stay_3. This variable signifies the date when the stay at home orders reached a level 3. We are using that feature to measure the impact it had on new cases per million. As you can see it had a statistically significant negative effect on new cases per million once it was inacted :

![](https://i.imgur.com/tpqFPAs.png)
![](https://i.imgur.com/PxzGxZL.png)

  
  
Known Issues:
-
There are issues with few features in the dataset, for instance,  that either have no correlation or are highly correlated. A few of the features like diabetes_prevelance, and population are highly correlated considering their threshold. All the issues with the data has to do with it not being preprocessed or cleaned. Our data has to be prepared to be able to perform modeling on. For instance, dealing with missing values and also detecting and removing outliers since there is much of it. We will also consider other cleaning methods necessary to prepare our data for modeling to get a good score.

Conclusion:
-
Our main concern is to have a well-prepared data that has been cleaned and preprecessed, ready enough for it to be modelled. Before proceeding to the conclusion of the model, we will evaluate the model thoroughly and review the steps executed to construct the model, to be certain it properly achieves the business objectives. 

We also have concerns about modeling the data given the relatively limited sample since of data. 

Our key objective is to determine if there is some important business issue that has not been sufficiently considered. At the end of this phase, a decision on the use of the data mining results will be reached, that would eventually help us get a good score for our model built.

