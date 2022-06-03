# Project 1: Standardized Test Analysis

## Table of Contents
- [Problem Statement](#Problem-Statement)
- [Outside Research](#[Outside-Research)
- [Data Dictionary](#Data-Dictionary)
- [EDA](#EDA)
- [Conclusion & Recommendations](#Conclusion-&-Recommendations)
- [Citation](#Citation)

## Problem Statement
### How the College Board might work to increase the SAT participation rate in Minnesota based on 2017 & 2018 data?
[Return to top](#Table-of-Contents)

## Outside Research
It seems that ACT has take over SAT's market share since 2012. One of SAT's strategies to regain market share is to allow School Day testing.

"The primary driver behind this surprising growth was the expansion of the SAT’s School Day testing. In a single year the number of students who took the SAT during a school day increased from 460,000 to 780,000, from 27% to 36% of all SAT takers. That is a remarkable increase, and more states are contemplating a move towards school day testing. Here is the current map of states aligning with the SAT or the ACT for school day testing." [(source)](https://www.applerouth.com/blog/2018/11/13/the-sat-is-back-on-top/)

[Return to top](#Table-of-Contents)

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|State|object|ACT/SAT|State names that participated in ACT / SAT exam. Total 51 states.| 
|ebrw_sat_17|int|SAT_17|Average SAT Evidence Based Reading and Writing score for each state in 2017 (range 200 - 800)|
|math_sat_17|int|SAT_17|Average SAT Math score for each state in 2017 (range 200 - 800)|
|total_sat_17|int|SAT_17|Average SAT Total score for each state in 2017 (range 400 - 1600)|
|p_sat_rate_17|float|SAT_17|Participation rate in decimals in 2017 (range 0 - 1)|
|english_act_17|float|ACT_17|Average ACT English score for each state in 2017 (range 1 - 36)|
|math_act_17|float|ACT_17|Average ACT Math score for each state in 2017 (range 1 - 36)|
|reading_act_17|float|ACT_17|Average ACT Reading score for each state in 2017 (range 1 - 36)|
|sci_act_17|float|ACT_17|Average ACT Science score for each state in 2017 (range 1 - 36)|
|composite_act_17|float|ACT_17| Average ACT Composite score for each state in 2017 (range 1 - 36)|
|p_act_rate_17|float|ACT_17|Participation rate in decimals in 2017 (range 0 - 1)|    
|ebrw_sat_18|int|SAT_18|Average SAT Evidence Based Reading and Writing score for each state in 2018 (range 200 - 800)|
|math_sat_18|int|SAT_18|Average SAT Math score for each state in 2018 (range 200 - 800)|  
|total_sat_18|int|SAT_18|Average SAT Total score for each state in 2018 (range 400 - 1600)|  
|p_sat_rate_18|float|SAT_18|Participation rate in decimals in 2018 (range 0 - 1)|  
|composite_act_18|float|ACT_18|Average ACT Composite score for each state in 2018 (range 1 - 36)|  
|p_act_rate_18|float|ACT_18|Participation rate in decimals in 2018 (range 0 - 1)|  

[Return to top](#Table-of-Contents)

## EDA

Amoungst the data visualizations and explorations, the delta in participation best targets my problem statement. SAT/ACT scores provide some insight on the relativity and correlation to participation, and will be used in the Conclusion & Recommendations section. 

- ACT participation rate  
        - Ohio increases from 75% in 2017 to 100% in 2018  
        - Nebraska increases from 84% in 2017 to 100% in 2018  
        - Colorado drops from 100% in 2017 to 30% in 2018  
        - Minnesota drops from 100% in 2017 to 99% in 2018  
- SAT participation rate  
        - Colorado increases from 11% in 2017 to 100% in 2018  
        - Idaho increases from 93% in 2017 to 100% in 2018  
        - District of Columbia drops from 100% in 2017 to 92% in 2018  

Colorado's SAT participation rate increases from 11% in 2017 to 100% in 2018. I am keen to find out more about this phenomenon, and see if we can replicate this result for Minnesota. Also to learn from any shortcomings of their strategy so as to have relevant mitigations in place.   
	
Two key factors come up in my research:  
- SAT was made mandatory in 2018  
- SAT was made free for all participants  
[(source)](https://testive.com/colorado-sat-change-2017/)

[Return to top](#Table-of-Contents)

## Conclusion & Recommendations

I recommend the College Board to target to increase SAT participation rate in Minnesota with the following strategies:

1. Despite having low participation rates (3% - 4%), Minnesota students achieve top 1% scores in the whole country (see Figure 1). However, there is a strong negative correlation between participation rate and total score. This means that when more students participate, the scores drop. This correlation can be seen in Colorado's SAT scores (see Figure 1). The College Board could look into improving access to study materials, or commiting more resources to help the teaching staff better prepare students for the SATs. The College Board could also negotiate a deal with the state to subsidize test fees. These strategies would help SAT gain market share.

|Minnesota|SAT 2017|ACT 2017|SAT 2018|ACT 2018|
|---|---|---|---|---|
|Participation|3%|100%|4%|99%|

2. College Board could also implement School Day testing in Minnesota. Allowing students to take the test during a school day instead of the weekends will make the SAT more appealing to students. This strategy has proven successful in regaining market share from ACT. Tennessee and Ohio already have School Day testing for both ACT and SAT (see Figure 2).  


3. College Board could also sign a deal with Minnesota to make SAT a requirement. As seen in Figure 3, Minnesota currently does not have any requirements for ACT/SAT for college admissions. Back in 2017, Colorado had adopted a mandated SAT approach which helped swing SAT participation from 11% to 100%.

![](https://github.com/andretch/Andre_Projects/blob/master/project_1/images/figure1.JPG)  
Figure 1: Composite ACT vs Total SAT scores 2017 & 2018

![](https://github.com/andretch/Andre_Projects/blob/master/project_1/images/figure2.png)  
Figure 2: Map of states which have School Day testing

![](https://github.com/andretch/Andre_Projects/blob/master/project_1/images/figure3.png)  
Figure 3: Map of states which require ACT / SAT  

[Return to top](#Table-of-Contents)

## Citations:

https://www.applerouth.com/blog/2018/11/13/the-sat-is-back-on-top/

https://magoosh.com/hs/sat/states-that-require-the-act-or-sat/

https://www.washingtonpost.com/education/2018/10/23/sat-reclaims-title-most-widely-used-college-admission-test/

https://testive.com/colorado-sat-change-2017/

https://www.collegeraptor.com/getting-in/articles/act-sat/states-act-sat-given-free/  

[Return to top](#Table-of-Contents)