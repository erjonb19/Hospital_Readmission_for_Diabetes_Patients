# Diabetes Readmission Prediction Project



## Project Overview



This project aims to predict the likelihood of hospital readmission for diabetic patients within 30 days of discharge. The dataset used for this project includes various patient attributes, hospital admission details, and medical procedures, which are used to build and evaluate predictive models. The goal is to identify high-risk patients and improve healthcare outcomes by providing timely interventions.


## Install Requirements
pip install -r requirements.txt


## Dataset



The dataset contains the following key attributes:



- Encounter ID: Unique identifier of an encounter
- Patient Number: Unique identifier of a patient
- Race: Patient's race (e.g., Caucasian, Asian, African American, Hispanic, and other)
- Gender: Patient's gender (e.g., male, female, and unknown/invalid)
- Age: Age group of the patient (grouped in 10-year intervals)
- Weight: Patient's weight in pounds
- Admission Type: Type of hospital admission (e.g., emergency, urgent, elective, newborn, and not available)
- Discharge Disposition: Discharge status of the patient (e.g., discharged to home, expired, and not available)
- Admission Source: Source of hospital admission (e.g., physician referral, emergency room, and hospital transfer)
- Time in Hospital: Number of days between admission and discharge
- Payer Code: Code of the payer (e.g., Blue Cross/Blue Shield, Medicare, and self-pay)
- Medical Specialty: Specialty of the admitting physician
- Number of Lab Procedures: Number of lab tests performed during the encounter
- Number of Procedures: Number of procedures (other than lab tests) performed during the encounter
- Number of Medications: Number of distinct medications administered during the encounter
- Number of Outpatient Visits: Number of outpatient visits in the year preceding the encounter
- Number of Emergency Visits: Number of emergency visits in the year preceding the encounter
- Number of Inpatient Visits: Number of inpatient visits in the year preceding the encounter
- Diagnosis 1, 2, 3: Primary and secondary diagnoses
- Number of Diagnoses: Total number of diagnoses recorded
- Serum Glucose Test Result: Range of serum glucose test results
- A1c Test Result: Range of A1c test results
- Change of Diabetes Medication: Indicates if there was a change in diabetic medications
- Diabetes Medication Prescribed: Indicates if any diabetes medication was prescribed
- 24 attributes for medications: Information about specific diabetic medications prescribed or changed
- Readmitted: Indicates if the patient was readmitted within 30 days (`<30`), after 30 days (`>30`), or not readmitted (`No`)



## Data Preprocessing



1. Handling Missing Values: Replaced missing or invalid values with NaN and removed columns with a significant number of missing values.
2. Feature Engineering: Created new features such as age_group, weight_group, and categorized diagnosis codes.
3. Data Cleaning: Removed duplicate entries and unnecessary columns, and mapped categorical values to numerical values where necessary.
4. Outlier Removal: Used interquartile range (IQR) to remove outliers from the dataset.



## Exploratory Data Analysis (EDA)



Conducted EDA to understand the distribution of key variables and their relationships. Visualizations included:



- Heatmap of feature correlations
- Bar plots of categorical variables (e.g., admission_type, discharge_disposition)
- Boxplots of numerical variables to identify outliers
- Frequency distribution plots for age groups and primary diagnoses



## Modeling



### Logistic Regression



- Pipeline: Included preprocessing steps (one-hot encoding of categorical variables) and oversampling using SMOTE to handle class imbalance.
- Grid Search: Performed hyperparameter tuning to find the best regularization parameter (`C`).
- Evaluation: Generated classification reports to evaluate model performance.



### Decision Tree Classifier



- Pipeline: Similar preprocessing steps as logistic regression with SMOTE for balancing the dataset.
- Grid Search: Tuned parameters such as max_depth and min_samples_leaf.
- Evaluation: Generated classification reports to evaluate model performance.



## Results



### Logistic Regression



- Best parameters: {'classifier__C': 0.1}
- Model performance: Detailed classification report with accuracy, precision, recall, and F1-score.



### Decision Tree Classifier



- Best parameters: {'classifier__max_depth': 20, 'classifier__min_samples_leaf': 2}
- Model performance: Detailed classification report with accuracy, precision, recall, and F1-score.



## Conclusion



This project demonstrates the process of building and evaluating predictive models for hospital readmission among diabetic patients. By identifying high-risk patients, healthcare providers can implement targeted interventions to reduce readmission rates and improve patient outcomes.



## Future Work



- Explore additional machine learning models (e.g., Random Forest, Gradient Boosting) for improved performance.
- Investigate feature importance to understand the most significant factors contributing to readmission.
- Implement a real-time prediction system for deployment in healthcare settings.



## Repository Structure



- data/: Contains the dataset used for the project.
- notebooks/: Jupyter notebooks with detailed steps for data preprocessing, EDA, and modeling.
- scripts/: Python scripts for data cleaning and model training.
- results/: Output files including model evaluation reports and visualizations.
- README.md: Project overview and instructions.



## Dependencies



- pandas
- numpy
- seaborn
- matplotlib
- plotly
- scikit-learn
- imbalanced-learn



## How to Run



1. Clone the repository:
git clone https://github.com/erjonb19/diabetes-readmission-prediction.git
