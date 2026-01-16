# Explainable Machine Learning Framework Based on Blood Biomarkers and Routine Health Information for Assistive Diagnosis and Risk Stratification of Acute Myocardial Infarction
## 1. Overview

Acute myocardial infarction (AMI) remains a major clinical challenge due to its rapid progression, high mortality rate, and the risk of delayed diagnosis caused by limited healthcare resources, particularly in high-volume outpatient settings. To address these challenges, this repository provides the implementation of a machine learning–based framework for assistive AMI diagnosis and risk stratification.

In this study, a total of 6,100 electronic medical records collected from Shanxi Cardiovascular Hospital were used to construct predictive models. Thirty-one clinical and biochemical features associated with AMI were extracted, including key cardiac biomarkers such as cardiac troponin I (cTnI), creatine kinase-MB (CK-MB), myoglobin (Myo), and N-terminal pro–B-type natriuretic peptide (NT-proBNP). Seven machine learning algorithms were developed and evaluated for binary AMI classification.

Among all evaluated models, the Light Gradient Boosting Machine (LightGBM) achieved the best diagnostic performance, demonstrating strong robustness and generalizability across both test and independent validation sets. To enhance model interpretability, SHAP (SHapley Additive exPlanations) was employed to quantify the contribution of individual features to model predictions, highlighting the dominant role of cardiac biomarkers such as cTnI and CK-MB.

In addition to binary diagnosis, this framework incorporates a risk stratification strategy designed to further analyze cases predicted as negative by the classification model. By integrating SHAP-based explanations, potentially high-risk individuals can be identified among negative predictions, thereby reducing the likelihood of missed diagnoses. Overall, this repository aims to support reproducible research and provide a transparent, interpretable, and extensible framework for assistive AMI diagnosis and risk stratification.

## 2. Data Description

The dataset used in this study consists of 4087 anonymized electronic medical records collected from Shanxi Cardiovascular Hospital. Each record corresponds to an individual presenting for clinical evaluation and includes both AMI-positive and AMI-negative cases.

A total of 31 features were extracted, comprising routine demographic information, clinical measurements, and blood-based cardiac biomarkers. The target label indicates whether the patient was diagnosed with acute myocardial infarction (AMI).

To protect patient privacy, the raw clinical data are not publicly released. The repository provides all data preprocessing, model training, and evaluation scripts to ensure reproducibility of the proposed framework when applied to compatible datasets.

## Repository Structure

├── Data preprocessing.ipynb
│   Implements data preprocessing procedures, including stratified dataset
│   partitioning (6:2:2) and SMOTE-based oversampling of the training set,
│   with outputs saved for downstream model training and testing.


├── Heatmap.ipynb
│   Computes and visualizes the feature correlation matrix to assess
│   inter-feature relationships.

├── Model Training.ipynb
│   Conducts feature selection, hyperparameter tuning, model training, and
│   performance evaluation across multiple machine learning classifiers.


├── SHAP.ipynb
│   Conducts SHAP-based model interpretation and secondary risk stratification
│   analysis for the optimized LightGBM classifier.

└── README.md
   Documentation describing the project overview, environment setup,
   repository structure, and usage instructions.

## 4. Workflow and Usage

The recommended workflow for reproducing the experiments in this repository is as follows:

1. **Data preprocessing**  
   Run `Data preprocessing.ipynb` to perform stratified dataset splitting (6:2:2) and SMOTE-based class imbalance correction on the training set.

2. **Exploratory correlation analysis**  
   Use `Heatmap.ipynb` to visualize inter-feature correlations and assess potential multicollinearity.

3. **Model training and evaluation**  
   Execute `Model Training.ipynb` to conduct genetic algorithm–based feature selection, hyperparameter optimization, and performance evaluation across multiple machine learning models.

4. **Model interpretation and risk stratification**  
   Run `SHAP.ipynb` to perform SHAP-based interpretability analysis and secondary risk stratification for negative predictions.

All intermediate datasets and figures are automatically saved during execution.


## 3. Environment & Dependencies

All experiments were conducted using Python in a standard scientific
computing environment. The code is platform-independent and can be
executed on Windows, Linux, or macOS systems.

### Hardware Configuration (Reference)

Performance evaluation was conducted on a standard PC platform equipped with an Intel(R) Core(TM) i7-10750H CPU @ 2.60 GHz (6 physical cores, 12 threads, 64-bit architecture). The optimized LightGBM model exhibits low storage requirements and fast inference speed, indicating potential feasibility for deployment in resource-constrained or portable clinical settings.

### Python Version
- Python 3.8 or later

### Required Libraries
The main Python packages required to run the notebooks include:
- numpy
- pandas
- scikit-learn
- lightgbm
- shap
- matplotlib
- seaborn

### Installation
It is recommended to create a virtual environment before installing
dependencies. The required packages can be installed using:

```bash
pip install numpy pandas scikit-learn lightgbm shap matplotlib seaborn

