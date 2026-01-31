# uidai-capacity-pressure-score
Data-driven framework to analyse capacity pressure in Aadhaar update operations using aggregated UIDAI datasets.
# UIDAI Capacity Pressure Score (CPS) Framework

This repository presents a data-driven framework to identify and compare operational capacity pressure across Indian states using Aadhaar enrolment and update data provided by UIDAI.

The framework introduces a composite indicator — **the Capacity Pressure Score (CPS)** — designed to highlight states experiencing sustained update load, operational volatility, and atypical update composition relative to enrolment capacity.

---

## Project Objective

Aadhaar enrolment and update services operate at massive scale across diverse regions. While enrolment volumes provide a proxy for baseline capacity, demographic updates introduce variable and sometimes uneven operational pressure.

This project aims to:
- Quantify update-related capacity pressure at the state level
- Detect anomalous spikes in update activity
- Identify sustained trends indicating rising or stabilising pressure
- Convert complex signals into actionable state-level categories

---

## Data Used

The analysis uses the official UIDAI datasets provided for the hackathon:
- Aadhaar Enrolment Data
- Aadhaar Demographic Update Data
- Aadhaar Biometric Update Data

Data is aggregated at the **state-month level** to balance temporal sensitivity with administrative relevance.

> **Note:** Raw datasets are not included in this repository in compliance with UIDAI data usage guidelines.

---

## Repository Structure
- notebooks/
        ├── 00_data_assembly.ipynb
        ├── 01_cps_core_logic.ipynb
        └── 02_validation_and_visual_evidence.ipynb
- data  # Placeholder (raw data not uploaded)
- outputs # Generated plots and summary tables
- docs   # Final PDF report


---

## Methodology Overview

The Capacity Pressure Score (CPS) is constructed using three complementary signals:

1. **Update Intensity**  
   Ratio of adult demographic updates to adult enrolments (18+), used as a proxy for sustained operational load.

2. **Update Volatility**  
   Month-to-month variability in update intensity, capturing operational instability.

3. **Adult–Child Update Skew**  
   Relative dominance of adult updates over child updates, highlighting atypical update composition.

All components are normalised to a 0–100 scale and combined using a weighted composite score.

CPS = 0.40 × Update Intensity
+ 0.30 × Update Volatility
+ 0.30 × Adult–Child Skew


CPS is a **relative operational indicator**, not a predictive or forecasting model.

---

## Outputs

- State-wise CPS scores and classifications (Red / Yellow / Green)
- Stress tests on weighting and threshold sensitivity
- Anomaly detection using z-score based spike identification
- Trend direction analysis using simple linear slopes
- Visual evidence supporting all claims

---

## Reproducibility

Each notebook is structured for step-by-step execution with clear intermediate outputs and validation checks.

The analysis can be reproduced end-to-end using the provided notebooks and UIDAI datasets.

---

## Disclaimer

This work is an analytical exercise conducted as part of the UIDAI Hackathon.  
Findings are based solely on the provided datasets and do not represent official UIDAI assessments or policy positions.
