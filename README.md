# SUPPORT2: Survival modelling, proportional hazards diagnostics, and 180-day mortality prediction

Reproducible analysis notebooks for an independent, retrospective methodological comparison of original Cox proportional hazards regression, disease-group-stratified Cox regression, and random survival forests (RSF) using the public SUPPORT2 dataset.

## Contents

- `01_SUPPORT2_Main_Analysis.ipynb`: main analysis, model fitting, proportional hazards diagnostics, calibration, 180-day test-set performance, and paired bootstrap comparisons.
- `02_SUPPORT2_Stability_and_Calibration.ipynb`: ten repeated stratified 80/20 splits and paired, fixed-risk-group calibration bootstrap sensitivity analysis.
- `requirements.txt`: package names for the Python environment. The notebooks include Colab installation cells. **Exact package versions must be archived from the executed Colab environment before claiming environment-level reproducibility.**

These GitHub copies omit saved cell outputs to minimise repository size and avoid inadvertently publishing embedded outputs. Run notebooks to recreate results.

## Public data

The notebooks retrieve **SUPPORT2**, UCI Machine Learning Repository, dataset ID 880, through `ucimlrepo.fetch_ucirepo(id=880)` at runtime. The source dataset is **not redistributed** in this repository.

Data page: https://archive.ics.uci.edu/dataset/880/support2

## Running the analysis

1. Open either `.ipynb` file in Google Colab (recommended), with a Python runtime.
2. Run cells from the top in order. Each notebook contains its own installation and data-fetch steps.
3. Start with `01_SUPPORT2_Main_Analysis.ipynb` for the primary analysis; run `02_SUPPORT2_Stability_and_Calibration.ipynb` separately for the sensitivity analyses.
4. Review generated CSV tables and PNG figures before adding them to a manuscript. Output directories are ignored by Git by default.

The survival forests and Cox comparisons use the original project-specific model definitions; the repeated-split extension is a sensitivity analysis rather than an external validation.

## Interpretation and limitations

- Historical SUPPORT2 data do not establish contemporary clinical effectiveness.
- Exact availability at the intended prediction time cannot be independently verified for every predictor recorded in the public dataset.
- Repeated train/test splits are correlated and must not be interpreted as independent external validation samples.
- Fixed-risk-group bootstrap results for an absolute calibration-error metric can remain biased or shifted; do not infer superior calibration from intervals containing zero.
- No systematic RSF hyperparameter tuning or external validation is claimed.
- This project is **not** a clinically deployable mortality-risk calculator.

## Authorship and funding

Joshua Osejigbe Aguele — Independent Researcher, Netherlands. No external funding reported.

## Cite this code

Once you have uploaded the project to GitHub, use your **actual repository URL** in the manuscript's code availability statement. To archive a stable, citable research version, consider a tagged GitHub release and Zenodo DOI. Do not claim that a DOI exists until it has been minted.
