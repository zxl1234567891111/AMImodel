# Explainable Machine Learning Framework Based on Blood Biomarkers and Routine Health Information for Assistive Diagnosis and Risk Stratification of Acute Myocardial Infarction
## 1. Overview

Acute myocardial infarction (AMI) remains a major clinical challenge due to its rapid progression, high mortality rate, and the risk of delayed diagnosis caused by limited healthcare resources, particularly in high-volume outpatient settings. To address these challenges, this repository provides the implementation of a machine learning–based framework for assistive AMI diagnosis and risk stratification.

In this study, a total of 6,100 electronic medical records collected from Shanxi Cardiovascular Hospital were used to construct predictive models. Thirty-one clinical and biochemical features associated with AMI were extracted, including key cardiac biomarkers such as cardiac troponin I (cTnI), creatine kinase-MB (CK-MB), myoglobin (Myo), and N-terminal pro–B-type natriuretic peptide (NT-proBNP). Seven machine learning algorithms were developed and evaluated for binary AMI classification.

Among all evaluated models, the Light Gradient Boosting Machine (LightGBM) achieved the best diagnostic performance, demonstrating strong robustness and generalizability across both test and independent validation sets. To enhance model interpretability, SHAP (SHapley Additive exPlanations) was employed to quantify the contribution of individual features to model predictions, highlighting the dominant role of cardiac biomarkers such as cTnI and CK-MB.

In addition to binary diagnosis, this framework incorporates a risk stratification strategy designed to further analyze cases predicted as negative by the classification model. By integrating SHAP-based explanations, potentially high-risk individuals can be identified among negative predictions, thereby reducing the likelihood of missed diagnoses. Overall, this repository aims to support reproducible research and provide a transparent, interpretable, and extensible framework for assistive AMI diagnosis and risk stratification.

## Repository Structure

├── Data preprocessing.ipynb
│   Implements data preprocessing procedures, including stratified dataset
│   partitioning (6:2:2) and SMOTE-based oversampling of the training set,
│   with outputs saved for downstream model training and testing.


├── Model Training.ipynb
│   Implements the training and evaluation of multiple machine learning
│   models for acute myocardial infarction (AMI) diagnosis, including
│   performance comparison across algorithms.

├── SHAP.ipynb
│   Conducts SHAP-based model interpretability analysis to quantify the
│   contribution of individual clinical and biochemical features to model
│   predictions.

├── Heatmap.ipynb
│   Generates correlation heatmaps to visualize relationships among
│   clinical and biochemical features used in the study.

├── ROC_curves_comparison.png
│   Visualization of ROC curves comparing diagnostic performance across
│   different machine learning models.

├── calibration_curves_with_brier_scores.png
│   Calibration curves with corresponding Brier scores to assess model
│   probability calibration performance.

├── Risk Stratification on Test Set.png
│   Visualization of the proposed risk stratification results on the test set.

├── Risk Stratification on Validation Set.png
│   Visualization of the proposed risk stratification results on the
│   independent validation set.

├── SHAP_bar_plot.png
│   SHAP feature importance bar plot showing global feature contributions.

├── SHAP_summary_plot.png
│   SHAP summary plot illustrating the distribution and magnitude of
│   feature impacts on model predictions.

├── SHAP_waterfall_sample_15.png
│   SHAP waterfall plot providing a local explanation for an individual
│   sample prediction.

├── SHAP_waterfall_sample_55.png
│   SHAP waterfall plot providing a local explanation for another
│   representative sample prediction.

└── README.md
   Documentation describing the project overview, environment setup,
   repository structure, and usage instructions.

## 3. Environment & Dependencies

All experiments were conducted using Python in a standard scientific
computing environment. The code is platform-independent and can be
executed on Windows, Linux, or macOS systems.

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
