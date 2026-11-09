# Reproducing and Extending Machine Learning Models for Early Childhood Development Prediction

**COMP8240 – Applications of Data Science | Macquarie University**

## Project Overview

This repository contains the Python implementation, data-processing workflows, and experimental results for a reproduction and extension of the study by Tebeje et al. (2025), *Application of machine learning algorithms to predict early childhood development in children aged 24–59 months across three East African countries*.

The project investigates the reproducibility and generalisability of supervised machine learning methods for predicting whether children aged 24–59 months are developmentally on track, as measured by the Early Childhood Development Index 2030 (ECDI2030).

The project comprises three experimental components:

1. **Original study replication:** Reproducing the published machine learning experiments using DHS datasets from Kenya, Mozambique, and Tanzania.
2. **New existing datasets:** Extending the methodology to DHS datasets from the Philippines and Jordan.
3. **Newly constructed dataset:** Evaluating the classifiers on synthetic data with a more balanced developmental outcome distribution.

## Repository Structure

```text
COMP8240_Assignment2/
│
├── codes/
│   ├── append_select_data.ipynb
│   ├── Rep_main_ECD-checkpoint.ipynb
│   ├── Rep_ECD_Model_comparison-checkpoint.ipynb
│   ├── Rep_ECD_Resampling-checkpoint.ipynb
│   ├── New_main_ECD.ipynb
│   ├── New_ECD_Model_comparison.ipynb
│   ├── New_ECD_Resampling.ipynb
│   ├── new_data_construction.ipynb
│   ├── New_construction_main_ECD-checkpoint.ipynb
│   ├── New_constructed_data_ECD_Model_comparison.ipynb
│   ├── New_construction_ECD_Resampling-checkpoint.ipynb
│   └── LLM_Judge.ipynb
│
├── data_project/
│   ├── data_selected.csv
│   ├── data_selected_new_existing.csv
│   └── new_data_constructed.csv
│
└── README.md
```

## Data Description

**Original datasets:** DHS data from Kenya, Mozambique, and Tanzania were harmonised to reproduce the original study. The reconstructed analytical dataset contains 11,980 selected mother–child observations.

**New existing datasets:** DHS data from the Philippines and Jordan were processed using comparable eligibility and harmonisation procedures, producing 7,411 observations.

**Newly constructed dataset:** A synthetic dataset was generated using selected demographic, maternal, household, and child-level predictors. Its ECD-on-track prevalence was 53.28%, providing a controlled setting for investigating model behaviour under a more balanced outcome distribution.

### Data Availability and Privacy

Access to the DHS datasets was authorised by the DHS Program for the registered research project. The original DHS microdata are subject to data-use restrictions and must not be publicly redistributed.

Researchers seeking access should apply independently through the [DHS Program](https://dhsprogram.com/).

Only code, documentation, synthetic data that are safe to share, and non-disclosive analytical outputs should be made publicly available.

## Code and Methodology

The project uses Python notebooks for data selection, preprocessing, feature construction, model training, resampling, evaluation, and interpretation.

Seven supervised machine learning algorithms were evaluated: Logistic Regression, K-Nearest Neighbours, Support Vector Machine, Naive Bayes, Random Forest, Gradient Boosting, and XGBoost. Additional ensemble models were investigated.

The main Python libraries include `pandas`, `NumPy`, `scikit-learn`, `XGBoost`, `SHAP`, `Matplotlib`, and `Seaborn`.

Model performance was evaluated using accuracy, balanced accuracy, sensitivity, specificity, weighted F1-score, and AUC-ROC. SHAP was used to investigate predictor contributions.

## Main Findings

The replication produced results broadly consistent with the original study, with the RF–XGBoost ensemble achieving 0.67 accuracy and 0.70 AUC-ROC.

On the Philippines and Jordan datasets, the NB–GB ensemble achieved 0.78 accuracy but only 0.61 balanced accuracy, highlighting the limitations of accuracy under class imbalance.

On the synthetic dataset, Gradient Boosting achieved 0.84 accuracy and 0.90 AUC-ROC, demonstrating stronger discrimination under the simulated conditions.

Overall, the results highlight the importance of reproducibility, dataset characteristics, class-specific performance, and careful assessment of generalisability.

## Project Report

The accompanying COMP8240 report documents the research background, original study, dataset construction, replication methodology, experimental results, model interpretation, ethical considerations, limitations, and conclusions.

The report is prepared using the ACL two-column LaTeX format.

## Reference

Tebeje, T. M., et al. (2025). *Application of machine learning algorithms to predict early childhood development in children aged 24–59 months across three East African countries*. PLOS ONE, 20(9), e0332023.

https://doi.org/10.1371/journal.pone.0332023

## Acknowledgements

I acknowledge the original study authors for their research and supplementary materials, the DHS Program for granting data-access authorisation, and Weijun Li and the COMP8240 teaching team at Macquarie University for their guidance and support.

## Disclaimer

This repository is intended for academic research and reproducibility. The machine learning models are exploratory and should not be used as clinical or individual developmental diagnostic tools.
