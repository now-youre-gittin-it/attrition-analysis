# Employee Attrition Analysis and Visualization

## Problem statement
Predict the attrition (Yes/No) of employees with 80% accuracy, identify what factors are significantly impacting it, and finally provide some suggestions on how to mitigate the attrition. 
Furthermore, create data visualizations to analyze attrition based on employee attributes like age, marital status, and work-life balance.

Data Source: <a href="https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset" target="_blank">**IBM HR Analytics Employee Attrition & Performance Dataset on Kaggle**</a>


## Objective

Primary business stakeholders- *HR Team of the company (IBM)*
They should be able to understand what factors contribute to attrition and take steps towards improving the situation based on the model results and final recommendations
Furthermore, visualizations will help understand employee performance trends based on certain employee attributes to enable focused and relevant decision making.

## Project Tasks
1. Feature Selection: Eliminate excess highly correlated numerical features using Pearson Correlation Heatmap
2. Data Transformation:
- Create dummy variables to represent categorical variables to allow processing by sklearn library
- Split data (70-30 split) into train and test sets for training model and testing the model's classification capability
- Class Imbalance Correction: Perform Minority ('Yes' class) Oversampling using SMOTE from imblearn library as 'Yes' class is crucial to our usecase
3. Random Forest
- Apply Random Forest Algorithm from sklearn
- Determine accuracy score for training datasets (with and without SMOTE) and test dataset
- Retrieve feature importance generated by RF classifier and identify the most important features
4. Logistic Regression
- Apply Logistic Regression from sklearn
- Perform recursive feature elimination (RFE) using statsmodels module (eliminate variables with p values > 0.05 at 5% level of significance)
- Apply Logistic Regression again on datasets after removing insignificant features obtained via RFE
- Determine accuracy score for training datasets (with and without SMOTE) and test dataset
- Identify feature importance generated by logistic regression model
5. Compare accuracy of both classification algorithms (RF and Logistic Regression)
6. Compare feature importance of both classification algorithms
7. Interpret classification results for implementation by the HR Team
8. Create data visualizations
- Reveal attrition pattern across age groups (derived attribute based on individual employee age) using plotly histogram
- Reveal work-life balance ratings of employees based on Marital_status attribute to identify suitable focus groups for remedial measures using plotly 
- Interpret data viz results for implementation by the HR Team

## Results 

1. **Model accuracy on test data is better for Random Forest than for Logistic Regression (86.6% vs 82.5%)**
We were able to achieve desired 80% accuracy for both models, which can be improved later through parameter tuning.

2. Moreover, **SMOTE helps in improving the training Accuracy for both models**, i.e. the models are able to tackle 'Yes' attrition cases too even though the original dataset had very few values for it.
3. Factors important to determine attrition (per RF classifier feature importance):
* Overtime_No, StockOptionLevel, Monthly Income, Years at Company, JobSatisfaction
5. Factors associated with 'Yes' attrition class (per LR classifier feature importance):
* BusinessTravel_Frequently, BusinessTravel_Rarely, Gender_Male, Department_Research & Development, Department_Sales
5. Millenials in the 24-40 yrs age group see most attrition, therefore this focus group either needs some drastic control measures if the organization wants to retain young talent, or they are prone to attrition due to unavoidable circumstances so IBM need not devote excessive resources on them.
6. Unmarried employees show attrition irrespective of their work-life balance rating.

## Recommendations

To minimize attrition in the most vulnerable groups, the company's HR team can introduce specific policies:
1. Minimize business travel (e.g. through remote work collaborations) as rare or frequent business travel are associated with attrition.
2. Attrition is higher among male employees. Modify the factors listed in Results (3.) in line with company policies to check if this reduces over time.
3. R&D and Sales departments tend to have more attrition. Introduce more exciting incentives to retain these employees.
4. Introduce policies/incentives catering to millienial and unmarried employees as these groups experience higher attrition.


