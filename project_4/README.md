## Table of Contents
1. [Problem Statement](#1-Problem-Statement)  
2. [Data Science Workflow](#2-Data-Science-Workflow)
3. [EDA Preview](#3-EDA-Preview)
4. [Recommendations and Conclusion](#4-Recommendations-and-Conclusion)  
5. [Future Steps](#5-Future-Steps)

## 1. Problem Statement
[Return to top](#Table-of-Contents)

- Given weather, location, testing, and spraying data, this competition asks you to predict when and where different species of mosquitos will test positive for West Nile virus. A more accurate method of predicting outbreaks of West Nile virus in mosquitos will help the City of Chicago and CPHD more efficiently and effectively allocate resources towards preventing transmission of this potentially deadly virus.

Stakeholders:
- Primary stakeholders: City of Chicago and the Chicago Department of Public Health (CDPH)
- Secondary stakeholders: General public for awareness

Datasets Used: 
- spray.csv
- weather.csv
- train.csv
- test.csv

## 2. Data Science Workflow  
[Return to top](#Table-of-Contents)  

Following the Data Science workflow:  
- Data Cleaning  
- Pre-Processing  
- EDA  
- Feature Engineering  
- Modeling  

## 3. EDA Preview  
[Return to top](#Table-of-Contents)  
Figure 1: Traps Visualization (Across years 2007,2009,2011,2013)  
![](https://github.com/andretch/GA_project_4/blob/master/images/traps.gif)  

Figure 2: 2011 Trap/Spray locations with Overlapping 1.3km radii for WNV+ traps  
![](https://github.com/andretch/GA_project_4/blob/master/images/2011%20trap%20spray%20overlap.png)  

Figure 3: 2013 Trap/Spray locations with Overlapping 1.3km radii for WNV+ traps  
![](https://github.com/andretch/GA_project_4/blob/master/images/2013%20trap%20spray%20overlap.PNG)  

## 4. Recommendations and Conclusion  
[Return to top](#Table-of-Contents)  

**Recommendations**  
Based on the AdaBoostClassifier predictions and it's identified feature importances, here are our recommendations:  

•	Identify corresponding positive traps with Lat, long values

•	Commence spraying in a radius of 1.3km around these traps a month in advance prior.

•	Maintain regular spray intervals of no longer than two weeks.

•	Coinciding traps with positive traps in its vicinity of 1.3km should also be sprayed due to the median flight range 	
of WNV carrying mosquito species.

•	Improve trap laying procedures by standardizing trap locations

**Conclusion**  
In this project, we cleaned and explored the traps, spray and weather data of Chicago to learn how variables of each play a part to determine mosquito populations and WNV presence in Chicago. Using insights gained during the data science process, we trained a selection of classifiers to predict WNV presence in traps to serve as a guide for timely effective allocation of resources.

The chosen model gave a decent ROC-AUC score of ~0.778, and very good recall score of ~0.901. Through the modelling process, we also learned about possible pitfalls when our scores can seem optimistic but may not necessarily generalize well on future data when look ahead bias is introduced in the training process.

In the cost-benefit analysis (CBA) we were able to extrapolate costs from previous studies done on Sacramento County to Chicago. With costs adjusted for inflation we were able to estimate that CDPH look to save ~$640 in medical costs $1 spent on sprays.

 The potential of WNV to bring about life-threatening complications also highlights the importance of prevention rather than cure as every life lost/ severely disrupted due to WNV is one too many.
 
https://www.cdc.gov/westnile/prevention/index.html
  
## 5. Future Steps  
[Return to top](#Table-of-Contents)  

•	Obtain data in increased quality and quantities

Provide the full range of data for an entire year. Should traps not be tested during winter months, methods can be used to impute the values of these traps (0 or mean for past/present year) to better account for the variability of weather data for a given trap.

In order to identify which traps to prioritise spraying, more information on actual population density of neighbourhoods or districts serve to better estimate the number of people covered by trap radii.

•	Include monitoring of WNV+ avian and equine species

Potential harbours of WNV+ can possibly include habitats of avian and equine species. Work should also be ongoing to identify new species of WNV+ mosquitoes.
