
# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: SAT and ACT Analysis

### Problem Statement
This project analyses the SAT and ACT participation rates along with the test scores in the USA. Performance and participation rates differ across states and the goal of the paper is to extract and analyse data using various forms of statistical inferences and visualization tools to provide recommendations to the college board to increase SAT participation rates. Analysis is based on SAT and ACT data in 2017 and 2018.

### Executive Summary
In general, the ACT is a more common mode of exam as compared to the SAT.

High participation rates on either the SAT or the ACT typically means low participation rates for the other test across states in the USA. This trend is heightened in states where the ACT is mandatory. Thus, it makes sense to channel the resources and funds to states where the ACT is not compulsory. As far as test scores are concerned, they remained fairly similar even at the high and low ends of the grades. However, a trend that emerges from the data is that states do not fare as well if tests are mandatory.In order to increase the SAT participation rates, the board should channel the resources to states where the ACT is not contracted. 

I would recommend the state of Pennsylvania for the following reasons: It is of close proximity to states where the SAT is contracted. Secondly, they have also experienced an increased in participation rates for the SAT from 65% to 70%. In addition, as discovered earlier in the preliminary analysis, high participation rates tend to correspond to low test scores. However, it is worth pointing out that Pennsylvania increased their SAT scores from 2017 to 2018. As such, this could indicate that the students are seeking out the SAT as opposed to the ACT. 

Another state one might consider is California as there is a lot of room for overall participation in the SAT. This would capitalise on absolute numbers instead of participation rate as there are 850, 000 students not covered by either the SAT or the ACT. This implies that a 1% increase in participation rate would lead to a much higher rise in absolute numbers in terms of participation.


|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT/SAT|Names of the 50 states in the USA| 
|sat_participation_17|float|ACT/SAT|State participation rate (%) in 2017|
|sat_erw_17|float|ACT/SAT|State mean score for Evidence-Based Reading and Writing in 2017|
|sat_math_17|float|ACT/SAT|State mean score for Math in 2017|
|sat_total_17|float|ACT/SAT|State mean total (Evidence-Based Reading and Writing and Math combined total) in 2017|
|act_participation_17|float|ACT/SAT|State participation rate (%) in 2017| 
|act_eng_17|float|ACT/SAT|State mean score for English in 2017|
|act_math_17|float|ACT/SAT|State mean score for Math in 2017|
|act_reading_17|float|ACT/SAT|State mean score for Reading in 2017|
|act_science_17|float|ACT/SAT|State mean score for Science in 2017|
|act_composite_17|float|ACT/SAT|State mean composite score (average score for English, Math, Reading, and Science) in 2017| 
|sat_participation_18|float|ACT/SAT|State participation rate (%) in 2018|
|sat_erw_18|float|ACT/SAT|State mean score for Evidence-Based Reading and Writing in 2018|
|sat_math_18|float|ACT/SAT|State mean score for Math in 2018|
|sat_total_18|float|ACT/SAT|State mean total (Evidence-Based Reading and Writing and Math combined total) in 2017|
|act_participation_18|float|ACT/SAT|State participation rate (%) in 2018| 
|act_eng_18|float|ACT/SAT|State mean score for English in 2018|
|act_math_18|float|ACT/SAT|State mean score for Math in 2018|
|act_reading_18|float|ACT/SAT|State mean score for Reading in 2018|
|act_science_18|float|ACT/SAT|State mean score for Science in 2018|
|act_composite_18|float|ACT/SAT|State mean composite score (average score for English, Math, Reading, and Science) in 2018| 


### Datasets

#### Provided Data

For this project, you'll have two provided datasets:

- [2017 SAT Scores](./data/sat_2017.csv)
- [2017 ACT Scores](./data/act_2017.csv)

These data give average SAT and ACT scores by state, as well as participation rates, for the graduating class of 2017.

You can see the source for the SAT data [here](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/), and the source for the ACT data [here](https://www.act.org/content/dam/act/unsecured/documents/cccr2017/ACT_2017-Average_Scores_by_State.pdf). **Make sure you cross-reference your data with your data sources to eliminate any data collection or data entry issues.**

#### Additional Data

2018 state-by-state average results and participation for the SAT are available in PDF reports [here](https://reports.collegeboard.org/sat-suite-program-results/state-results). 2018 ACT state-by-state mean composite scores and participation rates are [here](http://www.act.org/content/dam/act/unsecured/documents/cccr2018/Average-Scores-by-State.pdf) .

**This data has been compiled into CSV files which are also included in the *data* directory of this repo**
