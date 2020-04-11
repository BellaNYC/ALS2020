# ALS2020 - ALS progression prediction Dream challenge
## Introduction
Amyotrophic Lateral Sclerosis (ALS) is a kind of disease that involves the death and degeneration of the nerve cells in the brain and spinal cord. Prognosis of ALS is heterogeneous. So progression prediction allows significant contribution for patient care. This Dream sub challenge is to fit the model developed using 0-3 months clinical trial dataset to 3-12 months progression and the broader ALS population. We cannot get access to broader ALS data, just focused on the 1st progression predictino task.
## Data
PROACT (Pooled Resource Open-Access ALS Clinical Trials) dataset has 13 csv files, which contains from over 10,000 ALS patients from 23 completed clinical trials. What we need is the trial information taken between 0-3 months, then select significant features that contribute to ALS progression, resulting in good prediction for 3-12 months ALS progression. Final dataset was saved as ALS_FINAL.csv in directory "files".
## Data preprocessing - R programming
Files: ALS_myself, ALS_myself2, ALS_FINAL.csv
* Combined 13 different files, including demographics, lab values, and family history and other 10 files, to one final data frame
* Moved variables that have more than 75% missing values
* Label embedding toAmyotrophic Lateral Sclerosis (ALS) is a kind of disease that involves the death and degeneration of the nerve cells in the brain and spinal cord. Prognosis of ALS is heterogeneous. So progression prediction allows significant contribution for patient care. This Dream sub challenge is to fit the model developed using 0-3 months clinical trial dataset to 3-12 months progression and the broader ALS population. We cannot get access to broader ALS data, just focused on the 1st task. convert categorical variables
* Missing values processing, computed the mean for variables that have multiple values for the same patient (e.g. glucose level at different time points)
* Imputed missing data using the Multivariate Imputation by Chained Equations (MICE) via cart method in the mice library
## EDA - Data visualization
* Looked at relationship between ALSFRS and other features, such as Sex, lab values, and if families have related disease, etc
## Methods of predictions and evaluations - Python
Files: jupyter notebook
* Scaled data
* Dimensionality reduction: PCA
* Random forest, Xgboost, Polynomial regression
* Using RandomizedSearch to tune parameters and hyperparameters
* Feature selection
* Best RMSE is 0.0309 
## References:
https://docs.google.com/presentation/d/1SrXVtQWmrkN-zw9i04m8nGu4ki6VJISL6MktlJv81G4/edit#slide=id.p
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5099532/pdf/ACN3-3-866.pdf
