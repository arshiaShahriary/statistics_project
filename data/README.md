# 📂 Data Documentation

**IMPORTANT:** Following the course guidelines and data privacy best practices, the raw dataset files (`udslong_imputed.csv` and `mriscanclean.csv`) are **NOT** uploaded to this GitHub repository. This README serves as the official documentation for the data source and the reproducible steps required to reconstruct the analytical dataset used in this project.

## 📌 Data Source
The dataset utilized in this project is a pre-processed, multimodal subset provided by the course instructional team (Statistics Course, Fall 2026, Path C). It originates from the **National Alzheimer's Coordinating Center (NACC)**. 

The NACC database aggregates longitudinal clinical and neuropathological data collected from Alzheimer's Disease Research Centers (ADRCs) across the United States.

*   **Official Source:** [NACC - National Alzheimer's Coordinating Center](https://naccdata.org/)
*   **Data Type:** Observational clinical and neuroimaging (MRI) data.
*   **Unit of Observation:** Independent participants (Index Visit) - 1,237 unique individuals.

## 📁 Required Raw Files
To reproduce the analysis locally, the following files must be placed in this `data/` directory:

1.  `udslong_imputed.csv`: Contains the Uniform Data Set (UDS) clinical variables, including demographics (`NACCAGE`, `SEX`, `EDUC`), family history (`NACCFAM`), diagnostic status (`NACCUDSD`), and cognitive test scores (`MOCATOTS`, `ANIMALS`, `TRAILA`, `TRAILB`).
2.  `mriscanclean.csv`: Contains structural MRI features (Gray Matter Volume and Average Cortical Thickness) for various brain regions based on the Desikan-Killiany atlas.

## ⚙️ Data Preprocessing & Reconstruction Pipeline
The scripts in the `notebooks/` and `src/` directories expect the raw files to be present here. The analytical dataset is reconstructed through the following programmatic steps (detailed in `reports/phase1.pdf` and `notebooks/phase1_analysis.ipynb`):

1.  **Multimodal Merge:** The UDS and MRI datasets are inner-joined using the unique participant identifier (`NACCID`).
2.  **Handling Missing/Invalid Codes:** Standard NACC missing/refusal codes (e.g., `88`, `95-98`, `995-998`, and values imputed out of bounds) are systematically converted to `NaN` to prevent statistical bias.
3.  **Target Population Filtering:** For the main predictive and correlational analyses, the merged dataset is filtered to include only participants clinically diagnosed with Mild Cognitive Impairment (MCI, `NACCUDSD=3`) or Dementia (`NACCUDSD=4`). Normal cognition individuals (`NACCUDSD=1`) are excluded from the main regression models but used for baseline group comparisons.

For detailed descriptive statistics, code implementation, and a comprehensive data dictionary of the selected variables, please refer to the **Phase 1 Report** and the `PROJECT_CARD.md`.