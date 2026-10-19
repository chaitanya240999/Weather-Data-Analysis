# Weather Data Analysis, Forecasting & Visualization

End-to-end weather analytics combining a **real-time API feed** (OpenWeatherMap) with
**historical analysis and forecasting** on 96K hourly observations (2006–2016),
served through an interactive Streamlit dashboard.

## Results

Next-hour temperature forecasting on a temporal holdout (19,257 test rows):

| Model               | MAE   | RMSE  |
|---------------------|-------|-------|
| Naive (persistence) | 0.841 | 1.210 |
| Ridge               | 0.547 | 0.685 |
| **Gradient Boosting**   | **0.116** | **0.182** |

Gradient boosting reduces MAE by **86%** over the naive baseline.

## What's inside

- **Part 1 — Real-time collection:** `WeatherCollector` class pulling current conditions
  for 7 cities via the OpenWeatherMap API
- **Part 2 — Historical data:** 96,453 hourly observations, cleaning and validation
- **Part 3 — EDA:** monthly temperature climatology, daily cycle analysis, feature correlations
- **Part 4 — Feature engineering:** calendar features, 1h/24h/7-day lag features,
  24h rolling means and standard deviations
- **Part 5 — Forecasting:** naive / Ridge / gradient boosting with a strict temporal
  train/test split (no shuffling), MAE & RMSE evaluation, feature importances,
  forecast-vs-actual visualization
- **Part 6 — Dashboard:** Streamlit app with Live, Historical Trends, and Forecast tabs

## Run it

[![Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://www.kaggle.com/)

1. Open the notebook in Kaggle or Colab
2. Add the [Historical Hourly Weather Data](https://www.kaggle.com/datasets/muthuj7/weather-dataset)
   dataset (or upload `weatherHistory.csv`)
3. Run all cells top to bottom
4. For the live feed, add your OpenWeatherMap API key
   ([free tier](https://openweathermap.org/api)) — never commit keys to the repo

## Tech

Python · pandas · scikit-learn · Plotly · Streamlit · OpenWeatherMap API
