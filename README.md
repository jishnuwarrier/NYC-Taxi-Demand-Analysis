
# NYC Taxi Demand Analysis

## Project Overview
This project analyzes and forecasts taxi demand in New York City using approximately 19 million Yellow Taxi trip records from September 2023 to February 2024. The solution is implemented as a fully self-contained Jupyter Notebook using Apache Spark (PySpark) for data processing and Spark MLlib for machine learning.

The pipeline handles everything automatically - from downloading the raw data and shapefiles to cleaning, feature engineering, and training the Random Forest and GBT models.

## System Requirements
Because the analysis involves aggregating 19 million records, it requires significant memory.
* **Platform:** We recommend running this on Google Colab or a local machine with a UNIX-based OS.
* **Memory:** You need at least 12GB of RAM. The Spark driver is set to use 10GB by default.
* **Storage:** You need about 3GB of free space for the dataset downloads.
* **Python:** Version 3.10 or newer.

## Installation and Setup
You do not need to install libraries manually. The notebook includes an initialization script that checks your environment and installs the required packages (like pyspark, meteostat, and folium) when you run the first few cells.

## Data Acquisition
The notebook is self-contained and will fetch all necessary data for you.
1. **Taxi Data:** It downloads Parquet files directly from the NYC TLC.
2. **Geospatial Data:** It fetches the NYC Taxi Zone Shapefiles.
3. **Weather Data:** It queries the Meteostat API for historical hourly weather in Central Park.

## Execution Instructions
1. Open the file `NYC_Taxi_Demand_Analysis.ipynb` in your Jupyter environment or Google Colab.

2. Run the **Environment Setup** section first. This ensures PySpark and other dependencies are installed and ready.

3. Run the **Data Loading** section. This initializes the Spark Session with the necessary memory configurations and downloads the datasets. This might take a few minutes depending on your internet connection.

4. Run the remaining cells in order. The notebook follows a linear path:
   * **Data Cleaning** filters out invalid trips and coordinates.
   * **EDA** generates the maps and time-series plots.
   * **Feature Engineering** calculates the lag variables and time features.
   * **Modeling** trains the algorithms and prints the evaluation metrics.

5. All visualizations will appear directly in the notebook output, and the final RMSE and R2 scores will be printed at the end of the **Model Evaluation** section.
