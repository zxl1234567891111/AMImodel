# Explainable Machine Learning Framework Based on Blood Biomarkers and Routine Health Information for Assistive Diagnosis and Risk Stratification of Acute Myocardial Infarction
## 1. Overview

Acute myocardial infarction (AMI) remains a major clinical challenge due to its rapid progression, high mortality rate, and the risk of delayed diagnosis caused by limited healthcare resources, particularly in high-volume outpatient settings. To address these challenges, this repository provides the implementation of a machine learning–based framework for assistive AMI diagnosis and risk stratification.

In this study, a total of 6,100 electronic medical records collected from Shanxi Cardiovascular Hospital were used to construct predictive models. Thirty-one clinical and biochemical features associated with AMI were extracted, including key cardiac biomarkers such as cardiac troponin I (cTnI), creatine kinase-MB (CK-MB), myoglobin (Myo), and N-terminal pro–B-type natriuretic peptide (NT-proBNP). Seven machine learning algorithms were developed and evaluated for binary AMI classification.

Among all evaluated models, the Light Gradient Boosting Machine (LightGBM) achieved the best diagnostic performance, demonstrating strong robustness and generalizability across both test and independent validation sets. To enhance model interpretability, SHAP (SHapley Additive exPlanations) was employed to quantify the contribution of individual features to model predictions, highlighting the dominant role of cardiac biomarkers such as cTnI and CK-MB.

In addition to binary diagnosis, this framework incorporates a risk stratification strategy designed to further analyze cases predicted as negative by the classification model. By integrating SHAP-based explanations, potentially high-risk individuals can be identified among negative predictions, thereby reducing the likelihood of missed diagnoses. Overall, this repository aims to support reproducible research and provide a transparent, interpretable, and extensible framework for assistive AMI diagnosis and risk stratification.

