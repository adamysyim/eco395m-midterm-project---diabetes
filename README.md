# eco395m-midterm-project---diabetes

## Group Members
- Ashesh Shrestha
- Rishab Agarwal
- Seungwoon Shin
- Xiaohan Wu
- Youngseok Yim


## Data Source 
- The Behavioral Risk Factor Surveillance System (BRFSS) by the Centers for Disease Control and Prevention(CDC)
- BRSFF conducts health-related telephone surveys that collect state data about U.S. residents regarding their health-related risk behaviors, chronic health conditions, and use of preventive services. The current format started in 2011 with more than 500,000 interviews conducted in the states, the District of Columbia, participating U.S. territories, and other geographic areas.
- Although the overall survey structure and items are the same, new questions are added, and some old questions are omitted/corrected by the year. We selected 2017 data, for they have more detailed questions regarding food intake behaviors of U.S. residents compared to other years. (The most recent data is 2020)

  LINK: https://www.cdc.gov/brfss/annual_data/annual_2017.html

## The goal of the analysis
- As one of the most common chronic diseases in the United States, diabetes - type 1 and 2 - affects the health of millions of people. Diabetes is a severe chronic disease in which patients lose the ability to regulate glucose levels in the blood effectively, and it can lead to reduced quality of life and life expectancy. Complications like heart disease, vision loss, lower-limb amputation, and kidney disease are associated with chronically high levels of sugar remaining in the bloodstream for those with diabetes. 
- We would like to develop predictive models to identify risk factors for type 1 and 2 diabetes, which could help facilitate early diagnosis and intervention.
- Our research questions are:
  * What is the portion of diabetes patients among sex, income level, education level in the U.S.?
  * What lifestyle factors are most related to diabetes?
  * What medical risk factors are most predictive of diabetes risk?
- Although our analysis might be primitive in the eyes of the professional medical community, we believe this project would be a milestone experience for our team members to develop more sophisticated skills. 

## Methodology
- We analyzed cross-sectional data on XXX participants, including XXX with type 1 diabetes and XXXX with type 2 diabetes, from the 2017 Behavioral Risk Factor Surveillance System(BRSFF). 
- Based on what we have learned in the class, we utilized Pandas to import and clean the original data
....

## Summary on the documentation of the data

- Surveyees: noninstitutionalized adult population—aged 18 years or older—who reside in the United States in 2017. Respondents are identified through telephone-based methods
- The original BRFSS questionnaire consists of a core component, optional modules, and state-added questions:
  * Core component: queries about current health-related perceptions, conditions, and behaviors (e.g., health status, health care access, alcohol consumption, tobacco use, fruits and vegetable consumption, HIV/AIDS risks) as well as demographic questions.
  * Optional BRFSS modules: These are sets of questions on specific topics (e.g., pre-diabetes, diabetes, sugar-sweetened beverages, excess sun exposure, caregiving, shingles, cancer survivorship)
- We selected XXX survey questions among core components and optional modules. 
- We categorized them into Physical/mental health conditions, Behavioral factors(physical activity, food, alcohol, smoking), demography(sex, income, education, age group). For detailed descriptions of each item, refer to XXX.pdf 


### summarize what isn’t in the data. Limitations of the data
...

## Findings
...

## limitations of the analysis 
...

## Areas for more research 
...


## Instructions to rerun that analysis
#### Data download and cleaning
1. Download "2017 BRFSS Data (SAS Transport Format)" from https://www.cdc.gov/brfss/annual_data/annual_2017.html
2. Unzip the download, and you will get "LLCP2017.XPT". Rename the file by lowercase the letters to "llcp2017.xpt".
3. The xpt file is 1.29 GB big. When you import and run the file, make sure your system can handle the size of the file.
4. Run "data_importing_and_cleaning.ipynb" in "code" folder.
5. You will get "2017_diabetes_healthindicators" in the "data" folder.

#### Data analysis
1. run "xxx.ipynb"
