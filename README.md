# Data Transformation for Trading Models

Course 2 Project — *ML Pipeline for Feature Engineering* — from the Udacity AI Trading nanodegree (course CD13649, "Preparing for Data Analysis").

## Project Overview

The goal of this project is to practice the early stages of an ML pipeline for trading-related data. The focus is **not** on training a model, but on the data engineering steps that come before it: ingestion, cleaning, imputation, datetime alignment, resampling, feature standardization, exploratory data analysis, and exporting transformed datasets.

The datasets cover historical stock prices for Apple and Microsoft and U.S. macroeconomic indicators (GDP, monthly core inflation, and CPI).

## Skills Practiced

- Loading CSV data into Pandas DataFrames (local files with a GitHub raw-URL fallback)
- Inspecting and cleaning financial datasets
- Checking and forward-filling missing values
- Removing dollar signs and other non-numeric characters from price columns
- Converting date columns to Pandas `datetime`
- Aligning monthly time series to month-end dates with `pd.offsets.MonthEnd(0)`
- Upsampling and interpolating monthly inflation to weekly frequency
- Downsampling monthly inflation to quarterly averages
- Min-max standardizing GDP into a 0–1 feature
- Plotting time series, histograms, and a dual-axis rolling-volatility chart
- Computing daily stock returns and resampling them to monthly
- Building a 3×3 correlation heatmap (Apple returns, Microsoft returns, inflation change)
- Exporting cleaned datasets to CSV files

## Repository Layout

```text
data-transformation-trading-models/
├── Preparing-for-data-analysis-project-student.ipynb   # completed project notebook
├── README.md
├── requirements.txt
├── data/                                               # original Udacity datasets
│   ├── GDP.csv
│   ├── inflation_monthly.csv
│   ├── consumer_price_index.csv
│   ├── apple_historical_data.csv
│   └── microsoft_historical_data.csv
└── output/                                             # CSVs produced by the notebook
    ├── GDP_cleaned.csv
    ├── inflation_monthly_cleaned.csv
    ├── consumer_price_index_cleaned.csv
    ├── apple_historical_data_cleaned.csv
    ├── microsoft_historical_data_cleaned.csv
    ├── inflation_weekly_interpolated.csv
    ├── inflation_quarterly_average.csv
    └── correlation_dataset.csv
```

## How to Run

1. Clone the repo and create a fresh Python environment.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the notebook and run all cells:
   ```bash
   jupyter notebook Preparing-for-data-analysis-project-student.ipynb
   ```
   The notebook tries to read CSVs from `data/` first and falls back to the public Udacity GitHub repo if the local files are missing, so it works even if you only clone the notebook.

## Outputs Generated

- **Cleaned datasets** for Apple, Microsoft, GDP (with `GDP_standardized` column), inflation, and CPI
- **Weekly interpolated inflation** (upsampled from monthly)
- **Quarterly averaged inflation** (downsampled from monthly)
- **Correlation dataset** with monthly Apple returns, Microsoft returns, and inflation change
- **Plots inside the notebook**: Apple Open vs Close (last 3 months), Apple closing-price histogram (last 3 months), correlation heatmap (3×3), Apple closing price vs rolling weekly volatility (dual y-axis)

## Submission

This repository is intended as the **public GitHub repository** submission for the Udacity project *Data Transformation for Trading Models*.

## Data Source

Original CSVs come from the Udacity course repository:
[`udacity/CD13649-Project`](https://github.com/udacity/CD13649-Project/tree/main/Project)
