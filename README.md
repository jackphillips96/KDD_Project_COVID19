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

In our project we decided to look at the life expectancy,  by country, where the population is greater than ten million and confirm that there is a relationship between age of people that were infected by the virus and death rate.  


Research Question:
-
Comparing life expectancy across countries  to determine if it has an  effect on the number of deaths per million due to  COVID.

Relevant Domain:
-
https://academic.oup.com/jpubhealth/article/doi/10.1093/pubmed/fdaa087/5857763

https://thehill.com/changing-america/well-being/longevity/497097-those-who-died-from-covid-19-lost-more-than-a-decade-of

https://www.businessinsider.com/study-finds-that-people-who-have-coronavirus-could-die-10-years-early-2020-5

https://www.pewresearch.org/fact-tank/2020/04/22/populations-skew-older-in-some-of-the-countries-hit-hard-by-covid-19/

Data Sources:
-
https://ourworldindata.org/coronavirus-source-data

In this project we utilize data that was made available by European Center for Disease Prevention and Control (ECDC). ECDC  collects and harmonizes data from around the world via national health agencies  which allows us to compare and contrast what is happening in different  countries.

Confirmed cases and deaths: this data comes from the European Centre for Disease Prevention and Control (ECDC). Note: the number of cases or deaths reported by any institution—including the ECDC, the WHO, Johns Hopkins and others—on a given day does not necessarily represent the actual number on that date. This is because of the long reporting chain that exists between a new case/death and its inclusion in statistics. This also means that negative values in cases and deaths can sometimes appear when a country sends a correction to the ECDC, because it had previously overestimated the number of cases/deaths.

Testing for COVID-19: this data is collected by the Our World in Data team from official reports.

Other variables: this data is collected from a variety of sources (United Nations, World Bank, Global Burden of Disease, Blavatnik School of Government, etc.).

Approach:
-
  **Data Understanding and EDA:**
  
The main features we are looking at in our data are location (country), date, total cases per million, deaths per million, and life expectancy. 

We have performed Exploratory data analysis on our data. EDA refers to the critical process of performing initial investigations on data so as to discover patterns, to spot anomalies, to test  hypotheses and to check assumptions with the help of summary statistics and graphical representations. 

Our main concern was to check for correlation amongst  features, that lead us to use the correlation matrix in determining. There were very few features that had optimum correlation, for instance, the age_65_older, age_75_older, diabetes_prevalance, life_expectancy and so on. Finally, we have chosen to go with life expectancy with a correlation between 0.5 and 0.7, that leads to the spread of COVID. 

Here is an image showing some of the variables and a heatmap showing correlation values:


![](https://i.imgur.com/Qh0LOOk.png)

  
  
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
  
We are dealing with an unsupervised learning model as it only has input data and no corresponding output variables. As we have unlabelled data(No Y), we would try to use unsupervised techniques such as K-means clustering to detect patterns and group different countries into categories. This would enable us to find out whether certain countries have similarities related to spread of COVID 19. 

Also since we have so many variables, we would also use Principal Component Analysis to reduce the number of variables while capturing variance among different variables.

  
  
Known Issues:
-
There are issues with few features in the dataset, for instance,  that either have no correlation or are highly correlated. A few of the features like diabetes_prevelance, and population are highly correlated considering their threshold. All the issues with the data has to do with it not being preprocessed or cleaned. Our data has to be prepared to be able to perform modeling on. For instance, dealing with missing values and also detecting and removing outliers since there is much of it. We will also consider other cleaning methods necessary to prepare our data for modeling to get a good accuracy.

Conclusion:
-
Our main concern is to have a well-prepared data that has been cleaned and preprecessed, ready enough for it to be modelled. Before proceeding to the conclusion of the model, we will evaluate the model thoroughly and review the steps executed to construct the model, to be certain it properly achieves the business objectives. 

Our key objective is to determine if there is some important business issue that has not been sufficiently considered. At the end of this phase, a decision on the use of the data mining results will be reached, that would eventually help us get a good score for our model built.

