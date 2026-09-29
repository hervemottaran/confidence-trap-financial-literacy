# Reproducibility and publication notes

## What this repository contains

The notebook contains the completed analysis submitted for the Data Science Lab project. Its saved analytical outputs are retained so readers can inspect the results immediately. All reported estimates and figures are generated programmatically from the original Bank of Italy source data.

The data must be obtained separately as described in [`data/README.md`](../data/README.md). No private Google Drive folder or access to the authors' accounts is required.

## Environment

The submitted notebook records Python 3.13.15 and the analytical package versions pinned in `requirements.txt`. A separate local validation used Python 3.12.14 with the same NumPy, pandas, SciPy, statsmodels, Matplotlib, PyArrow and seaborn versions. Python 3.12 is the documented local setup.

JupyterLab is provided as the notebook interface. Its version does not enter the statistical calculations. Exact package versions can matter for fitted results, file formats and plotting behaviour.

### In Colab

The first code cell mounts your own Google Drive. The project root is `My Drive/The_Confidence_Trap`. Place the data at `The_Confidence_Trap/data/raw/Database_ENG.dta` before running the notebook.

Colab supplies many dependencies but its default environment can change. To install the recorded analytical versions, run the following in a temporary setup cell before the analysis:

```python
%pip install numpy==2.1.3 pandas==2.2.3 scipy==1.16.3 statsmodels==0.15.0 matplotlib==3.10.0 pyarrow==23.0.1 seaborn==0.13.2
```

If Colab requests a runtime restart after installation, restart it before running the analysis from the top. The notebook prints the installed versions in its environment-information cell.

### In local Jupyter

Install `requirements.txt` in a Python 3.12 virtual environment and open `notebooks/confidence_trap.ipynb`. Run Jupyter from either the repository root or its `notebooks` directory. Google Drive mounting is skipped and the root is resolved relative to the working directory.

Run the complete notebook in order from a clean kernel. Later modules use objects created by earlier modules; executing only the final model or figure cells is not sufficient.

## Validation

The original submitted analysis was independently run in an isolated local directory. All 70 analysis and setup cells executed successfully after replacing the Colab authentication and redirecting its two Drive paths. All 26 fitted models converged and passed the notebook's essential diagnostic checks. The run generated 43 CSV tables and nine figures, each in PNG and PDF format, including the report version of the outcome-probability figure.

The primary adjusted contrasts reproduce the report: +8.2 percentage points for financial incidents, −9.7 for careful affordability and +5.6 for long-term goals. Their respective 95% intervals are [2.7, 13.7], [−16.6, −2.8] and [−1.3, 12.5].

After adapting the setup for publication, all **71 code cells** were run sequentially in a fresh, isolated local project on 29 September 2026, without substituting or skipping any cell. All 26 models converged and passed the essential diagnostics. All 43 generated CSV tables matched the previously validated run at `rtol=1e-12` and `atol=1e-12`; only the `size_bytes` column in export manifests was excluded from comparison because it describes file sizes rather than analytical results. Both supported local working directories, the repository root and `notebooks/`, resolved correctly. The Colab-specific mount was preserved but was not retested in a live Colab session during this publication check.

Passing these checks establishes computational consistency with the documented workflow. Interpretation still depends on the model assumptions and limitations discussed in the report.

## Changes made for publication

The original submitted files remain separate. This portfolio copy makes only the following changes:

1. Update the notebook's introductory status and add short execution instructions.
2. Make Google Drive mounting conditional on running in Colab.
3. Resolve the project root for local Jupyter while retaining the existing Colab folder convention.
4. Reuse the same project-root variable when exporting the final report figure.
5. Clear the saved output of the two edited setup cells; retain all analytical outputs.
6. Remove student numbers, university email addresses and the old Google Drive link from the report's first-page author block. Retain all authors and the report's analytical content, figures, citations and AI declaration.

No variable definitions, model specifications, estimates, confidence intervals or analytical figure settings are changed. The generated figures copied to `assets/` are the original validated outputs.

## Generated files

Execution writes derived microdata to `data/processed/` and tables, figures and execution metadata to `outputs/`. It also creates working configuration files. These are ignored by Git. The published `assets/` directory contains only selected aggregate figures for the README.

The notebook's existing saved outputs document the submitted run. Their recorded package versions, dates and original Colab paths are historical execution information, not paths that a reader must possess.
