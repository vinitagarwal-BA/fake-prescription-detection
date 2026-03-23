💊 Fake Prescription Detection
> ML classification system for healthcare fraud prevention — Random Forest model achieving **91% F1-Score** and **88% fraud recall**.
![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)
---
📌 Business Problem
Pharmaceutical fraud through falsified prescriptions costs health systems billions annually and directly endangers patient safety. Manual review processes are slow, inconsistent, and unable to scale with prescription volumes.
Business need: A reliable, automated classification system to flag suspicious prescriptions before dispensing — reducing fraud losses, protecting patients, and minimising manual review workload.
---
🎯 Project Objective
Build a machine learning classification pipeline to detect fraudulent prescriptions, optimising for Recall (catching fraud) rather than raw accuracy — since the cost of a missed fraud (false negative) far exceeds the cost of a false alarm.
---
📊 Key Results
Metric	Logistic Regression	Decision Tree	Random Forest
F1-Score	72%	81%	91%
Recall (Fraud)	73%	79%	88%
Precision	71%	83%	94%

Business Metric	Value
Fraud Recall Rate	88%
Manual Review Reduction	~60%
False Positive Rate	9%
Best Model	Random Forest
---
🛠️ Tools & Technologies
Category	Tools
Language	Python 3.10
ML Models	Logistic Regression, Decision Tree, Random Forest
Data Processing	Pandas, NumPy
Class Imbalance	SMOTE (imbalanced-learn)
Visualisation	Matplotlib, Seaborn
Additional Tool	Orange Data Mining
Environment	Jupyter Notebook
---
🔄 Approach
1. Business Problem Framing
Identified fraud detection as a binary classification problem with asymmetric costs
Chose Recall as the primary optimisation metric — missing fraud (false negative) is far costlier than a false alarm
Defined business threshold: minimum 85% recall for production viability
2. Data Audit & Understanding
Assessed class imbalance (genuine vs. fraudulent prescriptions)
Identified missing fields, outliers, and data quality issues
Mapped available features to fraud risk factors from domain knowledge
3. Feature Engineering
Prescriber features: unusual drug combinations, off-hours submissions, high-volume patterns
Patient features: frequency of prescriptions, multiple prescriber usage
Drug features: controlled substance flags, quantity-to-diagnosis ratios
Temporal features: submission time, day of week, time since last prescription
4. Class Imbalance Handling
Applied SMOTE (Synthetic Minority Over-sampling Technique) to the training set
Preserved original class distribution in the test set for realistic evaluation
5. Model Development
Logistic Regression — interpretable baseline
Decision Tree — rule-based classification for explainability
Random Forest — ensemble method with 200 estimators
All models trained with stratified 80/20 train-test split
6. Evaluation & Selection
Evaluated on F1-Score, Recall, Precision, and ROC-AUC
Random Forest selected — best Recall (88%) and F1-Score (91%)
Confusion matrix analysed to quantify business cost of each error type
7. Output: Risk Scorecard
Translated probability scores into actionable triage categories (Low / Medium / High risk)
Designed output format to meet compliance requirements for healthcare audit trails
Documented feature importance for regulatory explainability
---
📈 Feature Importance (Random Forest)
Rank	Feature	Importance
1	Prescriber anomaly pattern	0.31
2	Unusual drug combination	0.24
3	Off-hours submission	0.18
4	Quantity-to-diagnosis ratio	0.15
5	Patient prescription frequency	0.12
---
💼 Business Impact
88% fraud recall — flags the vast majority of fraudulent scripts before dispensing
Reduces manual pharmacist review workload by ~60% by prioritising high-risk scripts
Audit-ready risk score output meets compliance requirements in regulated healthcare settings
Reusable pipeline adaptable to different pharmacy chains and health systems
---
📁 Project Structure
```
fake-prescription-detection/
├── notebooks/
│   ├── 01_eda_and_feature_engineering.ipynb
│   ├── 02_model_training.ipynb
│   └── 03_evaluation_and_scorecard.ipynb
├── outputs/
│   └── risk_scorecard_sample.csv    # Sample risk score output
└── README.md
```
---
👤 Author
Vinit Agrawal — Business Analyst  
Master of Business Analytics, Kaplan Business School, Adelaide  
LinkedIn · Portfolio
