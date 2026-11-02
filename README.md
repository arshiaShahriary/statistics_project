# Statistical Analysis of Alzheimer's Progression using NACC Data

Welcome to the repository for my Statistics course project (Fall 2026) at Sharif University of Technology. 

## 📌 Project Overview
This project investigates the relationship between brain structural features and cognitive decline in patients diagnosed with Mild Cognitive Impairment (MCI) and Dementia. Specifically, it explores to what extent the reduction in average cortical thickness in key Alzheimer's-related regions (such as the Entorhinal Cortex and Precuneus) can predict the decline in cognitive assessment scores (like MoCA and Verbal Fluency).

The analysis is conducted systematically across five phases, progressing from exploratory data analysis and probability distributions to advanced multiple regression modeling, with a strong emphasis on reproducible research and rigorous statistical foundations.

## 📊 Dataset
The multimodal dataset utilized in this project is sourced from the **National Alzheimer's Coordinating Center (NACC)**. It involves the integration of two main components:
*   **UDS (Uniform Data Set):** Clinical, cognitive, and demographic data.
*   **MRI Data:** Morphometric brain features (e.g., Cortical Thickness, Gray Matter Volume).

> **Note:** Due to data privacy regulations and file size constraints, the raw data files (`udslong_imputed.csv` and `mriscanclean.csv`) are **not** uploaded to this repository. Please refer to the `data/README.md` for information on the data structure and variables.

## 🗂️ Repository Structure
This repository is organized following standard reproducible research practices:

```text
statistics_project/
│
├── data/                   # Data documentation (raw datasets are gitignored)
│   └── README.md
├── notebooks/              # Jupyter notebooks for step-by-step data analysis
├── src/                    # Reusable Python scripts and helper functions
├── figures/                # Generated plots and data visualizations
├── reports/                # LaTeX source codes and compiled PDF reports
│   ├── phase1/
│   ├── phase2/
│   ├── phase3/
│   ├── phase4/
│   └── final/
├── PROJECT_CARD.md         # Statistical framework, variables, and main hypotheses
├── requirements.txt        # Python dependencies
└── README.md               # Project overview