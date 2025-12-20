# XAI Sepsis Prediction Project

## Presentation

The main presentation for this project is available here:  
[Copy of XAI sepsis ppt - Presentation](https://www.canva.com/design/DAG75BrWeAs/zGZulJBVrkzzMhy9ZITY4Q/edit) [web:1]

## Project Overview

This project focuses on building a machine learning pipeline to predict **sepsis onset** and then applying **Explainable AI (XAI)** techniques to make the predictions transparent and clinically interpretable. The goal is not only to detect high‑risk patients early, but also to provide clear reasons for each prediction so that clinicians can trust and validate the model’s behavior.

## Objectives

- Detect patients at high risk of developing sepsis within a defined prediction window.
- Use clinically meaningful features (vital signs, labs, demographics, etc.).
- Apply XAI methods to:
  - Explain individual predictions (local explanations).
  - Understand global feature importance and model behavior.
- Present results in a way that is usable for clinicians and non‑technical stakeholders.

## Data and Features

- **Input data** typically includes:
  - Time‑series vital signs (e.g., heart rate, blood pressure, respiratory rate, temperature, SpO₂).
  - Laboratory measurements (e.g., lactate, WBC, platelets, creatinine).
  - Demographic and static information (e.g., age, sex, comorbidities).
- **Labels**:
  - Binary label indicating whether the patient develops sepsis (and possibly *when*).
- **Preprocessing**:
  - Handling missing values (imputation, masking).
  - Normalization or standardization of continuous variables.
  - Aggregation of time‑series into features (last value, trend, min/max, etc.) if needed.

## Modeling Approach

- **Baseline models**:
  - Traditional ML models such as Logistic Regression, Random Forest, Gradient Boosting.
- **Possible advanced models**:
  - Sequence models (e.g., LSTM/GRU) or transformer‑style architectures for longitudinal data.
- **Evaluation metrics**:
  - AUROC, AUPRC for discrimination.
  - Sensitivity, specificity, F1‑score at clinically meaningful thresholds.
  - Calibration curves to assess probability estimates.

## Explainable AI (XAI)

To move beyond “black‑box” predictions, the project integrates XAI methods:

- **Global explanations**:
  - Feature importance across the entire cohort (e.g., permutation importance, model‑specific importance).
  - Partial Dependence Plots (PDP) or Accumulated Local Effects (ALE) to show how risk changes with a feature.
- **Local explanations**:
  - SHAP or LIME‑style explanations for individual patients, highlighting which features pushed the prediction towards or away from sepsis.
  - Visualization of feature contributions over time for time‑series models (e.g., attention weights, temporal attribution).

These explanations are used to:
- Check alignment with medical knowledge.
- Detect spurious correlations or data leakage.
- Communicate model behavior to clinicians and domain experts.

## Clinical Perspective

- **Intended use**:
  - Support early warning systems in ICUs / wards by flagging high‑risk patients.
- **Constraints**:
  - Explanations must be simple enough to understand quickly in a clinical workflow.
  - Model outputs should be treated as decision support, not autonomous decision‑making.
- **Ethical and safety aspects**:
  - Bias analysis across patient subgroups.
  - Monitoring for shifts in data distribution over time (dataset drift).

## Repository Structure (Example)

- `notebooks/` – Exploratory data analysis, model development, and XAI experiments.
- `src/` – Reusable code for preprocessing, training, and explanation generation.
- `models/` – Saved model weights and configuration files.
- `figures/` – Plots and explanation visualizations used in the presentation.
- `README.md` – Project description and usage instructions (this file).

## How to Use This Repository

1. **Set up environment**
   - Create a virtual environment and install dependencies from `requirements.txt`.
2. **Prepare data**
   - Place raw data in the expected directory (documented in `data/README.md` or config files).
3. **Train models**
   - Run the training script or notebook to fit the sepsis prediction model.
4. **Generate explanations**
   - Run the XAI scripts/notebooks to compute global and local explanations.
5. **Reproduce figures**
   - Use the notebooks in `notebooks/` or scripts in `src/` to regenerate the plots shown in the Canva presentation.

## Future Work

- Integrate real‑time streaming data from hospital systems.
- Extend XAI to include counterfactual explanations (e.g., “what needs to change to reduce risk?”).
- Perform prospective validation in clinical settings.
- Package the model + explanations into a simple dashboard for clinicians.

---

For a high‑level visual summary and slides aimed at presentations, please see the main deck:  
[Copy of XAI sepsis ppt - Presentation](https://www.canva.com/design/DAG75BrWeAs/zGZulJBVrkzzMhy9ZITY4Q/edit) [web:1]
