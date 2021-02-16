# Project 1: The Future of Standardized Testing
## Where Affirmative Action, Ethnicity and Standardized Testing Intersect
---

### Contents:

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Sources](#Data-Sources)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

---

### Problem Statement:

In November 2020, California voted on a proposition to reinstate affirmative action in public universities. If it had passed, Prop 16 would have allowed California public universities to consider a student's ethnicity and gender in admissions decisions, as well as their scores on the SAT and ACT and other academic measures. 

Despite heavy funding, Prop 16 failed with only 43% of Californians voting yes, however the margin between yes and no votes varied significantly by county. In partnership with the California College Admissions Board (CCAB), this analysis seeks to identify and understan any correlations between election results, ethnic make-up, and standardized testing results at the California county level. 

As a major supporter of Prop 16, this will help the CCAB make decisions on future affirmative action initiatives, and other factors that may influence and change the state's college admission process in the future. 

### Executive Summary

For this analysis, we looked at data on California SAT scores by school, district and county from 2019, California ACT scores by school, district and county from 2019, California Proposition 16 voting results by county from 2020, and Ethnicity percentages by California county from 2019. By rolling up testing data at the county level, then merging it with ethnicity and Prop 16 voting results, we can look for correlations beteen these factors, specifically to understand whether testing success and ethnicity impacted Californians' decision to vote for or against affirmative action. 

### Data Sources
* [`act_2019_ca.csv`](./data/act_2019_ca.csv): 2019 ACT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutact19.asp))
* [`sat_2019_ca.csv`](./data/sat_2019_ca.csv): 2019 SAT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutsat19.asp))
* [`prop_16_by_county`](./data/prop_16_by_county.csv): 2020 Calif Prop 16 Voting Results by County ([source](https://edsource.org/2020/live-election-results-for-propositions-15-16-and-18/642171))
* [`CA_2019_Ethnicity_by_County`](./data/CA_2019_Ethnicity_by_County.csv): 2019 Calif Population by Ethnicity by County ([source](https://en.wikipedia.org/wiki/California_locations_by_race))

### Data Dictionary

|Feature|Type|Source Dataset|Description|
|---|---|---|---|
|county|object|sat_2019_ca|Name of the California county| 
|enrolled_sat|float|sat_2019_ca|Total students enrolled in schools who participated in SAT testing in 2019
|testers_sat|float|sat_2019_ca|Total SAT test takers in schools that participated in SAT testing in 2019
|passed_sat_total|float|sat_2019_ca|Number of student test takers who passed both reading and math SAT benchmarks in 2019
|enrolled_act|float|act_2019_ca|Total students enrolled in schools who participated in ACT testing in 2019
|testers_act|float|act_2019_ca|Total ACT test takers in schools that participated in ACT testing in 2019
|passed_act_total|float|act_2019_ca|Number of student test takers who received a composite score of 21 or better on the ACT test in 2019
|y_vote_pct|float|prop_16_by_county|Percentage of Yes votes on 2020 Prop 16 for the county
|asian_pct|float|CA_2019_Ethnicity_by_County|Percentage of county population that is Asian in 2019
|black_pct|float|CA_2019_Ethnicity_by_County|Percentage of county population that is Black/African American in 2019
|county_pop|float|CA_2019_Ethnicity_by_County|County population as of 2019
|latino_pct|float|CA_2019_Ethnicity_by_County|Percentage of county population that is Latinx or Hispanic in 2019
|ntv_amer_pct|float|CA_2019_Ethnicity_by_County|Percentage of county population that is Native American in 2019
|other_pct|float|CA_2019_Ethnicity_by_County|Percentage of county population that is Other in 2019
|white_pct|float|CA_2019_Ethnicity_by_County|Percentage of county population that is White in 2019
|passed_sat_pct|float|sat_2019_ca|Percentage of student test takers who passed both reading and math SAT benchmarks in 2019
|passed_act_pct|float|act_2019_ca|Percentage of student test takers who received a composite score of 21 or better on the ACT test in 2019
|n_vote_pct|float|prop_16_by_county|Percentage of No votes on 2020 Prop 16 for the county
|county_pop_pct|float|CA_2019_Ethnicity_by_County|Percentage of California's population in the county

### Conclusions and Recommendations

#### Summary of Findings:
* Although passage of an Affirmative Action bill could benefit counties where a lower percentage of students achieve the minimum benchmarks for the SAT and ACT, this did not appear to be a consideration for voters in 2020. 

* The failure of Prop 16 and Affirmative Action in California is not cleanly related to SAT/ACT testing performance at the county level.

* However, ethnicity did play a role in how a county voted, with low-minority counties overwhelmingly voting No on Prop 16. Counties with lower minority make-up (<35%) overwhelmingly voted No on Prop 16. Counties with higher Latino/Hispanic make up, while also voting No overall, did so at a lower margin than heavily white counties. 

* One of the strongest correlations found in the data was between percentage of Latinos and the success rate on the SAT for a county. This warrants additional analysis.

#### Next Steps:

* Investigate the low testing success rates in heavily Latino/Hispanic communities, preferably at the student level.  For instance, are Latino/Hispanic minorities less likely to be first-language English speakers, and thus have a harder time with the tests?

* If the CCAB backs Affirmative Action initiatives in the future, consider how to better educate minorities on the perceived benefits. 

---


