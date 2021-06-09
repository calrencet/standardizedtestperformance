# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

#### Standardized tests score structure

SAT score range:  
Evidence-Based Reading and Writing (ERW): 200-800  
Math: 200-800  
(optional)Essay:2-8  
Pre-2016, the scoring structure was different. However, data is from 2017 hence our data is not affected.  
[source](https://collegereadiness.collegeboard.org/sat/scores/understanding-scores/interpreting)  
The benchmark as set by the college board is 480 for ERW and 530 for Maths
https://web.archive.org/web/20201224004347/https://www.cde.ca.gov/ds/sp/ai/glossarysat2019.asp

ACT score range:  
For each of the four sections: Between 1-36 which is average of correct answers in the section  
Composite score: average of scores for each section  
Scores are rounded to the nearest whole number  
(optional) Writing: 4 domain-level scores ranged 2-12  
1 subject-level score which is an average of the 4 domain-level scores  
[source](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)  

#### Additional research  

The Free and Reduced Priced Meal program is part of the National School Breakfast and Lunch Program for California. The United States Department of Agriculture provides funding to support five school meal and milk programs to assist schools, districts, and other non-profit agencies in providing nutritious meals and milk to children at reasonable prices or free to qualified applicants.  
[Source](https://www.benefits.gov/benefit/1953)  
  
Low-income children are eligible to receive reduced-price or free meals at school. Children in households with incomes below 130 percent of the poverty level or those receiving SNAP or TANF qualify for free meals. Those with family incomes between 130 and 185 percent of the poverty line qualify for reduced-price meals. When school is out of session in the summertime, children continue to receive nutritious meals and snacks through the Summer Food Service Program.  
[Source](https://www.feedingamerica.org/take-action/advocate/federal-hunger-relief-programs/national-school-lunch-program)    

Poverty rate in California in 2019 was 11.8%  
[Source](https://www.statista.com/statistics/205434/poverty-rate-in-california/)  

--- 

### Problem Statement

The state of California (California Department of Education) has many different school districts. They require the following analyses: (1) standardized test performance (both ACT and SAT) for the various districts in the state (2) data on students eligible for Free and Reduced Priced Meals (FRPM) for the various districts in the state, so they can identify whether there is a correlation between FRPM status and test performance in the schools, for the consideration of providing additional support to the students in need.

---

### Datasets

#### Provided Data


We will be using a subset of the below datasets where:
1. The schools exist in both the ACT and FRPM dataset or both the SAT and FRPM dataset;
2. There was at least 1 SAT or ACT taker within the school
  
  
act_2019_ca.csv  
2019 ACT Scores in California by School  
[Source](https://web.archive.org/web/20201223024015/http://www3.cde.ca.gov/researchfiles/satactap/act19.xlsx) [Data Dictionary](https://web.archive.org/web/20201224005341/https://www.cde.ca.gov/ds/sp/ai/reclayoutact19.asp)  
Contains County/District/School information, enrollment, and performance statistics of ACT scores in California for 2019

sat_2019_ca.csv  
2019 SAT Scores in California by School  
[Source](https://web.archive.org/web/20201223024015/http://www3.cde.ca.gov/researchfiles/satactap/sat19.xlsx) [Data Dictionary](https://web.archive.org/web/20201224004530/https://www.cde.ca.gov/ds/sp/ai/reclayoutsat19.asp)  
Contains County/District/School information, enrollment, and performance statistics of SAT scores in California for 2019



#### Additional Data
  

frpm1819.csv  
Free or Reduced Price Meals (FRPM) student data in California by School  
[Source](https://web.archive.org/web/20201016183202/https://www.cde.ca.gov/ds/sd/sd/filessp.asp) [Data Dictionary](https://web.archive.org/web/20201017154628/https://www.cde.ca.gov/ds/sd/sd/filesspfrpm.asp)  
Contains County/District/School information, enrollment, and statistics on Students who are eligible to receive FRPM either automatically based on their status or based on their application for the National School Lunch Program (NSLP), or who are determined to meet the same income eligibility criteria as the NSLP, through their local schools. This dataset includes schools where there are no students eligible to receive FRPM. 

#### Data Dictionary

|Feature|Type|Dataset|Description|
|:---|---|---|---|
|**school_code**|object|SAT/ACT/FRPM| The code of the California School|
|**school_name**|object|SAT/ACT/FRPM| The name of the California School|
|**district_name**|object|SAT/ACT/FRPM| The name of the California District|
|**county_name**|object|SAT/ACT/FRPM| The name of the California County|
|**enrollment**|float|SAT/ACT/FRPM| The number of 12th grade students enrolled in the School in the 2018-19 School Year|
|**num_sat_takers**|float|SAT|The number of 12th grade students, by school, who took the SAT in the 2018-19 School Year|
|**perc_sat_takers**|float|SAT|The percentage of 12th grade students, by school, who took the SAT in the 2018-19 School Year|
|**sat_num_read_write_benchmark**|float|SAT|The number of 12th grade students, by School, that took the SAT for Evidence-based Reading and Writing and scored above the mean score threshold set by the College Board in the 2018-19 School Year.|
|**sat_perc_read_write_benchmark**|float|SAT|The percentage of 12th grade students, by School, that took the SAT for Evidence-based Reading and Writing and scored above the mean score threshold set by the College Board in the 2018-19 School Year.|
|**sat_num_math_benchmark**|float|SAT|The number of 12th grade students, by School, that took the SAT for Mathematics and scored above the mean score threshold set by the College Board in the 2018-19 School Year.|
|**sat_perc_math_benchmark**|float|SAT|The percentage of 12th grade students, by School, that took the SAT for Mathematics and scored above the mean score threshold set by the College Board in the 2018-19 School Year.|
|**sat_total_num_both_benchmarks**|float|SAT|The number of 12th grade students, by School, that took the SAT and scored above the mean total score threshold set by the College Board in the 2018-19 School Year.|
|**sat_perc_both_benchmarks**|float|SAT|The percentage of 12th grade students, by School, that took the SAT and scored above the mean total score threshold set by the College Board in the 2018-19 School Year.|
|**num_act_takers**|float|ACT|The number of 12th grade students, by school, who took the ACT in the 2018-19 School Year|
|**perc_act_takers**|float|ACT|The percentage of 12th grade students, by school, who took the ACT in the 2018-19 School Year|
|**act_avg_score_read**|float|ACT|The average Reading score of 12th grade students, by School, that took the ACT in the 2018-19 School Year.|
|**act_avg_score_eng**|float|ACT|The average English score of 12th grade students, by School, that took the ACT in the 2018-19 School Year.|
|**act_avg_score_math**|float|ACT|The average Mathematics score of 12th grade students, by School, that took the ACT in the 2018-19 School Year.|
|**act_avg_score_sci**|float|ACT|The average Science score of 12th grade students, by School, that took the ACT in the 2018-19 School Year.|
|**act_num_above_21**|float|ACT|The number of 12th grade students, by School, that took the ACT and achieved a composite score above 21 in the 2018-19 School Year.|
|**act_perc_above_21**|float|ACT|The percentage of 12th grade students, by School, that took the ACT and achieved a composite score above 21 in the 2018-19 School Year.|
|**frpm_count**|int|FRPM|The number of 12th grade students, by School, who meet household income or categorical eligibility criteria for free meals or reduced meals based on one or more of the valid reasons in the 2018-19 School Year.|
|**frpm_perc**|float|FRPM|The percentage of 12th grade students, by School, who meet household income or categorical eligibility criteria for free meals or reduced meals based on one or more of the valid reasons in the 2018-19 School Year.|
|**low**|object|FRPM| Classification of whether the school has a frpm_perc at or below the 25th percentile.
|**med**|object|FRPM| Classification of whether the school has a frpm_perc at or below the 50th percentile.
|**high**|object|FRPM| Classification of whether the school has a frpm_perc at or below the 75th percentile.
|**very_high**|object|FRPM| Classification of whether the school has a frpm_perc above the 75th percentile.

---

### Executive summary

An analysis was conducted to identify the size of the population of students who are eligible for the FRPM among the entire population of students within the dataset.  

Further, analyses were conducted on the FRPM percentage of the various schools, as well as their standardized tests performances in terms of percentage of students who achieved above a score of 21 for the ACT or who met both college board benchmarks for the SAT.

Hypothesis testing was conducted using the Pearson's Correlation Coefficient (Pearson's R) test to ensure the scientific accuracy of the analysis.

𝐻0: There is no correlation between percentage of FRPM eligible students in Californian schools and percentage of students in the same schools who scored above 21 for the ACT or met the college board benchmark for the SAT
𝐻0: rho = 0

𝐻𝐴: There is a correlation between percentage of FRPM eligible students in Californian schools and percentage of students in the same schools who scored above 21 for the ACT or met the college board benchmark for the SAT
𝐻𝐴: rho ≠ 0

Independent variable = frpm_perc
Dependent variables = act_perc_above_21, sat_perc_both_benchmarks

Significance level: 2.5% (adjusted down for the Bonferroni correction)

The Pearsons's R test gave the following results:
The correlation coefficient between frpm_perc and act_perc_above_21 is -0.8401169556698439 and the p-value is 1.6064809915999597e-269.
The correlation coefficient between frpm_perc and sat_perc_both_benchmarks is -0.8369529417771113 and the p-value is 0.0.

---

### Conclusion/Recommendations

1. The p-value from our hypothesis test was small enough for us to reject the null hypothesis and accept the alternative hypothesis that there is a correlation between the percentage of FRPM eligible students in a school and the percentage of students achieving or meeting the benchmark of the standardized tests is therefore accepted.
2. This correlation is strongly negative, at around -0.84, which means that the higher the percentage of FRPM eligible students there are, the lower the percentage of students meeting the benchmarks.
3. While we only named the top 5 schools in terms of FRPM percentage in our analysis, we have identified that a whopping 56% of the students in our dataset are eligible for FRPM, which is several times higher than the poverty rate of 11.8% for California in 2019. With no other factors to go by, we make an assumption that FRPM-eligibility is an indicator that performance in the standardized test may be lower. It may thus be crucial and recommended that additional funding and/or help is provided not only to the schools with higher FRPM student percentages, but to the students who are FRPM eligible throughout all the schools.

