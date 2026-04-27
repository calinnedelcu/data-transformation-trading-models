# Data Transformation for Trading Models

Project for the Udacity AI Trading nanodegree (Course 2: Preparing for Data Analysis).

The notebook walks through cleaning and transforming historical stock prices for Apple and Microsoft together with a few macroeconomic series (GDP, monthly core inflation, CPI), and finishes with some EDA: a price chart, a histogram, a correlation heatmap, and a rolling volatility plot.

## How to run

1. Install the dependencies:
   ```
   pip install -r requirements.txt
   ```
2. Open `Preparing-for-data-analysis-project-student.ipynb` in Jupyter and run all cells.

The notebook reads the CSVs from the `data/` folder. Cleaned outputs are written to `output/`.

## Data

The original CSVs come from the Udacity course repo `CD13649-Project` and are included in `data/`.
