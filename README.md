### Initial Report and Exploratory Data Analysis: Maternity Health Risk

#### Executive Summary
This analysis of maternal health risk data factors revealed blood pressure and blood sugar as key factors in evaluating pregnancy-related health risks.  Data exploration, cleansing, and logistic regression modeling is performed in order to develop a set of signals for healthcare providers to potentially when monitoring patients to optimize deployment of care personnel and resoures.  The model itself achieved around 80% accruacy in classifying patients as low, mid or high-risk.  Recommendations for further study include improvements to the data collection process as well as developing more advanced learning models to improve the prediction accuracy and precision.

#### Rationale
The rationale for this machine learning project is to provide healthcare providers with a means to identify high-risk pregnancies so they can add these signals to clinical workflows and triage care and resources accordingly, leading to improved health outcomes for the population.

#### Research Question
Can we build a model that can accurately predict maternal health risk in order to provide healtcare poroviders with a set of signals they can use in operations when monitoring patients in order to optimize the deploymenyt of care personnel, attention, and equipment?

#### Data Sources
The data comes from the UCI machine learning library and is title "Maternal Health Risk". https://archive.ics.uci.edu/dataset/863/maternal+health+risk

#### Methodology
Exploratory Data Analysis is performed for this submission, including data cleansing, outlier analysis, checking for missingness, checking for class imbalances, and standardization of data features as necessary.  A logistic regression model is fit to the data and evaluated.

#### Results
In summary, we explored the raw dataset to determine what data features may influence pregnancy risk.  Ultimately we build and score a basic logistic regression model to predict risk level based on age, blood pressure, heart rate, and blood sugar

1.  Initial Data Analysis and Cleanup Recommendations
    - the dataset had three risk categories:  low, mid, and high.  we converted these to numeric values for modeling purposes.
    - there was an abundance of duplicate values.  these have the potential to skew or bias the model results.  we remove these records from the analysis, but note the cause of the duplicates warrants further investigation and analysis
    - the risk levels as a target variable for the predictions was not balanced, this could be a purposeful data collection strategy or have some other legitimate business reason.  However, for purposes of modeling, we recommend balancing strategies be deployed in either sampling or in the modeling stages.
  
2.  Key Features/Influencers
    - Blood Sugar appears to show a strong correlation with risk level
    - Blood Pressure (both systolic and diastolic) have significant correlation with maternal risk categorization
    - Body Temperature was slightly less interesting in terms of correlation and heart rate did not seem to be too significant in terms of influence

3.  Logistic Regression Model and Performance
    - After standardizing the numeric features, the basic logistic regression performed decently for low-risk classification (79% precision, 66% recall) and high-risk classification (67% precision, 43% recall), but struggled to predict mid-risk classification (29% precision, 43% recall).
    - The ROC-AUC score, which measures how well the model differentiates between risk levels showed relatively decent predictive ability at about 80%.



#### Next Steps
Ideally, we'd like to improve the performance of predicting mid-risk and high-risk cases, as having misdiagnoses in those instances could theoretically lead to treatment delay or misallocation of personnel and resources.

To address this we will model improvements such as cross-validation, class-weight adjustments, and deploying more advanced models (XGBoost or Random Forest) that may provide better predictability.
