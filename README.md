# eco395m-midterm-project---diabetes

## Group Members
- Ashesh Shrestha
- Rishab Agarwal
- Seungwoon Shin
- Xiaohan Wu
- Youngseok Yim


## Data Source 
- The Behavioral Risk Factor Surveillance System (BRFSS) by the Centers for Disease Control and Prevention(CDC).
- BRSFF conducts health-related telephone surveys that collect state data about U.S. residents regarding their health-related risk behaviors, chronic health conditions, and use of preventive services. The current format started in 2011 with more than 500,000 interviews conducted in the states, the District of Columbia, participating U.S. territories, and other geographic areas.
- Although the overall survey structure and items are the same, new questions are added, and some old questions are omitted/corrected by the year. We selected 2017 data, for they have more detailed questions regarding food intake behaviors of U.S. residents compared to other years. (The most recent data is 2020).

  Link: https://www.cdc.gov/brfss/annual_data/annual_2017.html

## Summary on the documentation of the data

- Surveyees: noninstitutionalized adult population—aged 18 years or older—who reside in the United States in 2017. Respondents are identified through telephone-based methods
- The original BRFSS questionnaire consists of a core component, optional modules, and state-added questions:
  * Core component: queries about current health-related perceptions, conditions, and behaviors (e.g., health status, health care access, alcohol consumption, tobacco use, fruits and vegetable consumption, HIV/AIDS risks) as well as demographic questions.
  * Optional BRFSS modules: These are sets of questions on specific topics (e.g., pre-diabetes, diabetes, sugar-sweetened beverages, excess sun exposure, caregiving, shingles, cancer survivorship)
- We selected 13 survey questions among core components and optional modules. 
- We categorized them into Physical/mental health conditions, Behavioral factors(physical activity, food, alcohol, smoking), demography(sex, income, education, age group). For detailed descriptions of each item, refer to XXX.pdf 

## The goal of the analysis
- As one of the most common chronic diseases in the United States, diabetes - type 1 and 2 - affects the health of millions of people. Diabetes is a severe chronic disease in which patients lose the ability to regulate glucose levels in the blood effectively, and it can lead to reduced quality of life and life expectancy. Complications like heart disease, vision loss, lower-limb amputation, and kidney disease are associated with chronically high levels of sugar remaining in the bloodstream for those with diabetes. 
- We would like to develop predictive models to identify risk factors for the diabetes, which could help facilitate early diagnosis and intervention.
- Our research questions are:
  * What lifestyle factors, such as food intake, physical exercise, smoking/alchohol, are most related to diabetes?
  * What medical risk factors are most related to diabetes? 

## Methodology
- Step_0: to see the overall picture of diabetes, we selected several variables regarding demograhy, lifestyle factors, and the related medical conditions, and constructed basic plots. We witnessed that some patterns or correlations between diabetes and those variables. 
- Step_1: based on the overall picture of the data, we concluded that those tentative variables are worth analyzed to answer our research questions. We cleaned the data by dropping missing values, ambiguous answers such as 'don't know', we came up with one dependent variable and 13 independent variables. Since all of the answers in the original survey questions are designed for the respondents to answer with numerical or categorical numbers, we then further renamed and reorganized the each variables to fit the statistical model we were going to use. 
- Step_2: Also, by looking at detailed statistics of each variables, we excluded potential invalid samples. Finally, the total number of respondents(rows) is 211,319. You can see the summary statistics in the code.   
- Step_3: data analysis
  * correlation heat map to see the detailed correlations between variabels
  * simple multiple regression to see if it fits the dataset 
  * multiple logitstics regression for better fitting of the dataset
 

## Results and Findings

 ### Results 
 
  #### [Multiple Logitistics Regression]

<img width="417" alt="logit result" src="https://user-images.githubusercontent.com/97976503/159059404-6d90cbf5-1d2b-4259-99f9-beabdec79838.png">

  #### [To see how well a logistic regression model fits a dataset]

![ROC curve](https://user-images.githubusercontent.com/97976503/159059710-539d96fa-96b7-4d9d-a18d-5ad23ba68a89.png)

The closer area under the curve(AUC) is to 1, the better the model. And our model's AUC has 0.77 which is good. 

  #### [Odd Ratio] 

<img width="167" alt="odd ratio" src="https://user-images.githubusercontent.com/97976503/159067662-bcfe4ad5-c322-42f3-a9eb-a6fe4b25437e.png">


### Findings 
 #### From the Odd Ratios
  - There is 55% greater relative risk of having diabetes if you have heart conditions(michd) 
  - There is 80% greater relative risk of having diabetes if you have high cholesterol(hchol)
  - There is 137% greater relative risk of having diabetes if you have high blood pressure(hblpr)
  - There is 52% less relative risk of having diabetes if you earn annual income of $ 50,000 or more
  - There is 40% less relative risk of having diabetes if you have higher education(bachelor or more)

### Limitations of the data
  - One of the lifestyle factors that we wanted to analyze was the food intake such as vegetables, fruitjuice, etc. The original survey contains those data. For example, "Total vegetables consumed per day", "Total fruits consumed per day", "How often did you eat any kind of fried potatoes, including french fries, home fries, or hash browns?". However, the numbers contain too many extreme values that cannot be modified to get valid statistics. We dropped those variables. It is possible that many respondents misunderstood the questions and the interviewer didn't intervene to correct the answers.

### limitations of the analysis and Areas for more research 
  - According to the Odd Ratio, drinking(hvdr) and smoking(smok) seem to have reverse relationship with the diabetes. However, many medical studies show the opposite: if you drink or smoke, you would have higher chance of getting diabetes. The reverse relationship we obtained is due to the features of our cross-sectional data: cross-sectional data is simply a snapshot of samples in certain point in time. In order to elaborately examine the relationship we need a follow-up studies which traces smoking or alcohol intake behaviors of the subjects for certain time periods.

## Instructions to rerun that analysis

#### Environment and Setup
1. Open the GCP VErtex AI. Choose the Jupyter Lab.
2. Fork and Git-Clone this respiratory into the Jupyter Lab.

#### Data Acquisition
1. Download "2017 BRFSS Data (SAS Transport Format)" from https://www.cdc.gov/brfss/annual_data/annual_2017.html based on the original_data_download_instruction.txt file in "data" folder.
2. Unzip the downloaded zip file, and you will get "LLCP2017.XPT". Please upload this file into the project folder "eco395m-midterm-project---diabetes/data" in the GCP environment for preparation. The uploading process may take about 30 minutes due to the large size of the file. What is more, never git-push the "LLCP2017.XPT" since it's not small enough to be uploaded. Put the 'LLCP2017.XPT" file in the untracked category in the Jupyter Lab window.
3. The XPT file is 1.29 GB big. When you import and run the file, please make sure your system can handle the size of the file.

#### Requirementts of Python Packages, Modules, and Toolkits
1. Install all the required packages, modules, and toolkits listed in "requirements.txt" file.

#### Step0 Variable Selection & Data Overlook
1. Based on the codebook and our common sense, we manually selected 14 variables (including 1 dependent variable and 13 independent variables candidates). The detailed info is shown in the step_0_list_of_selected_variable.csv file in "data" folder.
2. Run "step_0_data_overlook.ipynb" in "code" folder. You will get the overlook of the categorical variables in the whole uncleaned dataset.

#### Step1 Data Cleaning
1. Run "step_1_data_importing_and_cleaning.ipynb" in "code" folder. You will get "2017_diabetes_cleaned.csv" in the "data" folder for the regression analysis.

#### Step2 Summary Statistics
1. Run "step_2_summary_statistics.ipynb" in "code" folder. You will get "2017_diabetes_cleaned_vld.csv" (cleaned dataset without potential invalid samples) in the "data" folder. You will get summary statistics of the 14 selected variables.

#### Step3 Data analysis & Model Selection
1. Run "step_3_data_analysis_and_model_selection.ipynb" in "code" folder. You will get the data analysis and the model selection process for the dataset from "2017_diabetes_cleaned_vld.csv".
2. Run "step_3_substep_ensemble_methods.ipynb" in "code" folder. You will get the additional model selection process.
