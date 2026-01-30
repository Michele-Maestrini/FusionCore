

<img width="273" height="121" alt="FusionCore" src="https://github.com/user-attachments/assets/692079cc-0f95-4386-bf88-2256625293c6" />

# FusionCore v0 - Methods

## Scope

This document describes the **experimental methodology only**.
It intentionally excludes motivation, product context, and roadmap.

---

## Dataset

* **[NASA C‑MAPSS Turbofan Engine Degradation Dataset](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/)**
* Remaining Useful Life (RUL) regression task
* Windowed time-series formulation

All datasets undergo **identical preprocessing**.

---

## Data Preparation

* Fixed window length
* Shared feature set across all models
* Engine-level train / validation / test splits
* No leakage between engines or time windows

Once generated, datasets are **frozen** for all experiments.

---

## Models

### Temporal Fusion Transformer

* Encoder–decoder architecture
* Static and time-varying covariates
* Attention-based temporal reasoning

### TS Mixer

* Pure MLP architecture
* Temporal and feature mixing blocks
* No attention mechanisms

### AutoGluon TimeSeries

* Automated model selection and ensembling
* Includes statistical and deep learning models
* Configuration constrained for comparability

---

## Hyperparameter Tuning

* Model-specific search spaces
* No shared hyperparameters across architectures
* Tuning performed independently per model

Hyperparameter results are logged and reproducible.

---

## Validation Strategy

* Cross-validation at the engine level
* Consistent splits across models
* Evaluation performed on unseen engines

---

## Evaluation Metrics

Primary:

* RMSE
* MAE

Secondary:

* Error distributions
* Per-engine performance variance
* Stability across folds

---

## Visual Analysis

* Prediction vs ground truth
* Residual plots
* Cross-model comparison charts

Visualisations are used as **diagnostic tools**, not marketing artefacts.

---

## Outputs

* Trained model checkpoints
* Metric tables
* Comparative plots
* Concise technical report summarising empirical findings

---

## Experimental Constraints

* Single dataset
* Single task (RUL regression)
* No deployment or streaming assumptions
___

