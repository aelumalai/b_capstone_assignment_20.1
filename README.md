# b_capstone_assignment_20.1
capstone_assignment_20.1 

**Initial Report and Exploratory Data Analysis (EDA)**

The research question you intend to answer:
**Predicting Hospital Readmission within 30 Days :**
Diabetic patient readmissions within 30 days of discharge represent a critical and costly issue for healthcare systems. These preventable readmissions significantly strain hospital resources, lead to substantial financial penalties, and most importantly, compromise patient well-being and recovery. Identifying patients at highest risk of readmission relies heavily on subjective assessments, leading to inefficient resource allocation and missed opportunities for timely intervention. This project leverages advanced machine learning techniques on a rich historical dataset of diabetic patient hospitalizations to develop a predictive model. This model will accurately identify patients at elevated risk of 30-day readmission upon discharge

Your expected data source(s) (as either a link to existing data or a sentence describing where you will source the data from)
Dataset Name: Diabetes 130-US hospitals for years 1999-2008 Data Set

Source: UCI Machine Learning Repository

Link : https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008Links to an external site.

The techniques you expect to use in your analysis:
Will be applying the following techniques learnt:
EDA  - exploratory data analysis  and feature engineering:

Handling Missing Values: Techniques like imputation (mean, median, mode, or more sophisticated methods) will be crucial, as real-world healthcare datasets often have missing data.
Categorical Feature Encoding: Convert categorical variables (e.g., race, gender, diagnoses codes) into numerical formats using One-Hot Encoding or Label Encoding.
Feature Scaling: Standardize or normalize numerical features (e.g., laboratory results, number of procedures) to ensure that no single feature dominates the model due to its scale.
Creating Interaction Features: Explore creating new features by combining existing ones (e.g., age * number of diagnoses) to capture complex relationships.
Visualization Techniques:
Machine Learning Models: Given the nature of the problem (predicting a binary outcome) and the potentially large dataset, starting with interpretable models like Logistic Regression and then progressing to more powerful ensemble methods like Random Forests or Gradient Boosting Machines would be a sound approach. Feature importance from these models will directly address the 'most influential predictive factors' part of your research question.

Logistic Regression
Random Forests
Gradient Descent (GD), Stochastic Gradient Descent (SGD)
Support Vector Machines (SVMs)

Evaluation Metrics:
Accuracy
Precision and Recall
F1-Score
ROC AUC (Receiver Operating Characteristic Area Under the Curve
Confusion Matrix
The expected results : For the capstone project on predicting 30-day hospital readmission, the expected results would encompass several key areas:
High Predictive Performance on re-admissions
Identification of Key Predictive Factors : The models are expected to reveal the most influential features contributing to 30-day hospital readmission.

Actionable Insights for Intervention: These identified factors can provide valuable clinical insights into the drivers of readmission, which can then inform targeted interventions
Why this question is important:  This problem is very important as it causes stress and discomfort for patients and is expensive for hospital due to penalties when re-admissions happen within 30 days.
The research on predicting the re-admissions in hospital will help to generate practical information for doctors and nurses, case managers and administrators can use.  The model will support in identifying patterns in patient data that humans might miss.
**Following are the benefits:**
Better patient outcome.
Cost savings for hospitals
Improved efficiency and quality of care.
