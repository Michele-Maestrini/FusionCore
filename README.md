<img width="273" height="121" alt="FusionCore" src="https://github.com/user-attachments/assets/692079cc-0f95-4386-bf88-2256625293c6" />

# FusionCore: Risk-Aware Predictive Maintenance System

**FusionCore** is a research-led framework designed to solve the "Structural Leakage" and "Uncertainty Quantification" problems in aerospace prognostics. Moving beyond standard regression, FusionCore implements a **Forensic Validation Gate** to ensure Remaining Useful Life (RUL) estimations are driven by physical degradation signals rather than temporal metadata artefacts.

---

## 1. Executive Summary

Predictive maintenance in safety-critical domains (Aerospace) demands more than just low RMSE; it requires **statistical honesty** and **quantifiable risk**. 

FusionCore v0 establishes a rigorous "Ground Truth" by subjecting State-of-the-Art (SOTA) architectures to forensic stress testing against the NASA CMAPSS dataset. The framework evaluates the trade-off between **Probabilistic Risk Assessment** (DeepAR), **Attention-Based Interpretability** (TFT), and **Local Semantic Pattern Recognition** (PatchTST).

---

## 2. The Problem: "Temporal Cheating" & Regime Blindness

Standard deep learning models often exhibit "too-good-to-be-true" performance in research settings due to two critical flaws:

1. **Structural Temporal Leakage:** Models often learn to "count down" using internal data indices rather than interpreting sensor physics. FusionCore identifies and remediates this through a **Forensic Stress Test**.
2. **Non-Stationarity:** Models mistake high-altitude cruise conditions for engine failure because they lack context-aware normalisation.

**The FusionCore Hypothesis:**
> *A physics-aware architecture that prioritises kinematic derivatives (Deltas and Rolling Means) over raw temporal sequences will demonstrate superior reliability under anomalous sensor failure, even if traditional metrics (MAE) appear higher.*

---

## 3. The Solution (FusionCore v0)

We benchmark three SOTA paradigms to solve the "Reliability Triangle" of Risk, Clarity, and Pattern Recognition.

| Architecture | Role | Why This Model? |
| --- | --- | --- |
| **DeepAR (Probabilistic)** | **The Risk Estimator** | Produces a probability distribution for RUL. Essential for calculating the **Probability of Failure (PoF)** rather than just a point estimate. |
| **Temporal Fusion Transformer (TFT)** | **The Glass Box** | Utilises **Variable Selection Networks** to provide interpretability, allowing engineers to audit which sensors drive the model's decisions. |
| **PatchTST (Transformer)** | **The Pattern Recogniser** | Segments time-series into semantic "patches" to capture local degradation trends whilst ignoring high-frequency sensor noise. |

---

## 4. Key Results (Phase 0 Diagnostics)

*Prior to benchmarking, our Forensic Audit (see `notebooks/04_Forensic_Stress_Test.ipynb`) revealed:*

* **Leakage Detection:** Identified that default Time-Series models achieved $10^{-9}$ MAE by "cheating" via temporal indices.
* **Remediation:** Established an **Honest Baseline (2.28 MAE)** using shuffled tabular regression and kinematic feature engineering.
* **Anomaly Sensitivity:** Validated that the physics-aware model reacts to synthetic sensor spikes with an immediate RUL reduction (17.26 cycles), whereas "Black Box" models ignore the fault.

---

## 5. Repository Structure

```text
FusionCore/
├── docs/                  # Technical deep-dives and PDF reports
│   └── technical_report_v0.pdf
├── notebooks/             # Exploratory Data Analysis & Stress Testing
│   ├── 01_EDA_Diagnostics.ipynb       # Initial sensor analysis
│   ├── 02_EDA_Regimes.ipynb           # Stationarity & Regime mathematics
│   ├── 04_Forensic_Stress_Test.ipynb  # Leakage audit & Anomaly injection
│   └── 05_SOTA_Benchmarking.ipynb     # DeepAR, TFT, and PatchTST
├── src/                   # Modular source code
│   ├── data/              # Kinematic feature engineering & v1_physics logic
│   └── models/            # DeepAR, TFT, and PatchTST definitions
├── requirements.txt       # Python dependencies
└── README.md              # This file
```

---
## 6. Author



**Michele Maestrini**

*Data Science | Specialising in Aerospace Predictive Maintenance | Time-Series Analysis*



[LinkedIn](www.linkedin.com/in/michele-maestrini)
