# Demand Forecasting with Linear Regression

This project implements A demand forecasting case study using linear regression and time-series features.
The goal is to predict future demand based on historical patterns and compare the model against a simple naive baseline.

Achieves ~46.8% RMSE improvement over a naive baseline.

---

## Dataset

The dataset consists of daily retail time series data.
Key variables include inventory level, units sold, and price.
The data is sorted chronologically to preserve the temporal structure of the time series.

---

## Approach

Feature engineering focuses on short-term demand dynamics:
- Lagged features (Lag 1, Lag 2)
- 7-day moving average (MA7)

A time-based train/test split (80/20) is used to avoid data leakage.
Only past information is available to the model at prediction time.

---

## Baseline

As a baseline, a naive lag-1 forecast is used:
the prediction for the next time step is simply the previous observed value.

This baseline represents the minimum performance threshold the model must outperform to be considered useful.

---

## Model

A linear regression model is trained on the engineered features.
Despite its simplicity, the model is able to capture short-term demand trends effectively when combined with lag features.

---

## Evaluation

Model performance is evaluated on a future hold-out test set using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

The linear regression model outperforms the naive lag-1 baseline by approximately **46.8% RMSE improvement**,
indicating substantial added predictive value beyond simple persistence.

---

## Results and Interpretation

The results suggest that demand dynamics in the dataset are largely driven by recent historical patterns.
Lag features and short-term moving averages contribute most strongly to model performance.

While the model does not capture extreme demand spikes perfectly, it consistently improves over the baseline.

---

## Limitations and Next Steps

- Only a single linear model is evaluated
- External factors such as promotions or seasonality are not explicitly modeled

Possible extensions include:
- Non-linear models (e.g. tree-based methods)
- Additional temporal or external features
- Walk-forward cross-validation

---

## How to Run

## Requirements
- Python 3.10+
- Git
- Jupyter Notebook (e.g. via VS Code or Jupyter Lab)

## Setup

### 1. Clone the repository

git clone https://github.com/Mafii61/demand-forecasting-linear-regression.git

cd demand-forecasting-linear-regression

## 2. Create a virtual environment

python -m venv env

## 3. Activate the virtual environment

Windows (PowerShell): env\Scripts\Activate.ps1

Windows (cmd): env\Scripts\activate.bat

macOS / Linux: source env/bin/activate

## 4. Install dependencies

pip install -r requirements.txt

## 5. Run the notebook

Open the Jupyter notebook and run all cells:

demand_forecasting_linear_regression.ipynb