# Time-Series Analysis

A minimal workspace for exploring and modeling time-series data using a single Jupyter Notebook.

## Project Structure

- [code.ipynb](code.ipynb): Main notebook containing data exploration, visualization, and modeling steps.

## Prerequisites

- Python 3.10+ (Windows)
- VS Code (recommended) or Jupyter Notebook

Recommended Python packages:

- jupyter, ipykernel
- numpy, pandas
- matplotlib, seaborn, plotly
- scikit-learn
- statsmodels

Optional packages (install only if needed):

- prophet (advanced forecasting; install may take longer on Windows)

## Quick Start (Windows, PowerShell)

Set up an isolated environment, install dependencies, and open the notebook.

```powershell
# 1) Create and activate a virtual environment
python -m venv .venv
.venv\Scripts\Activate.ps1

# If activation is blocked, allow local scripts
# Set-ExecutionPolicy -Scope CurrentUser RemoteSigned

# 2) Upgrade pip and install core packages
python -m pip install --upgrade pip
pip install jupyter ipykernel numpy pandas matplotlib seaborn plotly scikit-learn statsmodels

# (Optional) Install prophet only if required by your analysis
# pip install prophet

# 3) Register the kernel for use in Jupyter/VS Code
python -m ipykernel install --user --name time-series --display-name "Python (time-series)"

# 4) Launch Jupyter Notebook (or use VS Code's notebook UI)
jupyter notebook
```

Open [code.ipynb](code.ipynb) and select the kernel "Python (time-series)". Run cells top-to-bottom.

## Typical Workflow in the Notebook

- Import and configure libraries
- Load data from CSV/Parquet or a database
- Clean, resample, and transform series (handling missing values, scaling)
- Visualize trends, seasonality, and anomalies (line plots, decomposition)
- Assess stationarity (e.g., ADF), autocorrelation (ACF/PACF)
- Fit baseline models (e.g., ARIMA/SARIMA via statsmodels)
- Evaluate with appropriate metrics (e.g., RMSE, MAPE)
- Iterate on feature engineering or advanced models (optional)

## Data & Outputs

- Place input data files in a local `data/` folder (create if needed) and reference them from the notebook.
- Save figures and artifacts to an `outputs/` folder for easy review.

## Reproducibility

Capture the environment for future runs.

```powershell
pip freeze > requirements.txt
```

To recreate later:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Troubleshooting (Windows)

- Activation script blocked: run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, then retry activation.
- Kernel not appearing: re-run `python -m ipykernel install --user --name time-series --display-name "Python (time-series)"` and restart VS Code/Jupyter.
- Plots not showing: ensure the cell enabling inline plots is executed; restart the kernel if needed.

## Notes

- This repository intentionally stays minimal. Extend the notebook for your datasets and models.
- If you add scripts or data, update this README with paths and usage.