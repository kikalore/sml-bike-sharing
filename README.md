# sml-bike-sharing
Final Project for the Scalable Machine Learning Course. We will predict the availability of bike sharing points in the city of Trento (Italy).

### Overview

This project aims to predict daily usage of bike sharing service for the city of Trento (Italy) accordingly to weather info.

The system is designed as an end-to-end MLOps pipeline, which includes:

* Backfilling a feature store with historical data.

* A daily feature pipeline to ingest new data.

* A training pipeline to create and update a predictive model.

* A batch inference pipeline to generate daily forecasts.
  
### Technology used

* Feature Store: Hopsworks

* Bike sharing data: City Bikes (https://data.citybik.es/)

* Weather: Open-Meteo API

* ML Model: XGBoost (XGBRegressor)

+ GitHub Actions (for daily pipeline scheduling)


### Project Workflow & Components

The project is broken down into four main pipelines, represented by the notebooks:

1. **Feature Backfill**: To populate the Hopsworks feature store with historical data. 
Firstly we read historical bikes data from local parquet files (for 85 stations in Trento starting from November 2024) and the corresponding historical weather data from the Open-Meteo API are fetched.
Finally, after having defined data validation rules using `GreatExpectations`, data are ingested into two feature groups in Hopsworks: `bikes_trento` and `weather_trento`.

2. **Feature Pipeline**: A daily scheduled pipeline to fetch new data and keep the feature store up-to-date.
It fetches data for today's usage of shared-bikes for all 85 stations from the City Bikes API, then fetches the today's weather data and the upcoming 7-day forecast from the Open-Meteo API.
At the end, the new daily data and forecast data are inserted into the `bikes_trento` and `weather_trento` feature groups.

3. **Training Pipeline**: To train the prediction model using the available features.
A feature view is created in Hopsworks to join the `bikes_trento` and `weather_trento` feature groups and a training dataset is generated from this feature view.
This feature view is used to train an XGBoost regression model to predict the next day's usage of shared-bikes.
The trained model is saved to the Hopsworks model registry.

4. **Batch Inference Pipeline**: A daily pipeline to generate batch predictions for the upcoming days.
The latest trained model from the Hopsworks Model Registry is loaded and a batch inference feature view is created, which gathers the 7-day predictions.
After that predictions are saved back to a new feature group (`monitoring_fg`) for monitoring and application use.

### Setup
To run the 4 notebooks in this repository: 
Clone the repository.

Install the required Python dependencies `pip install -r requirements.txt`.

Set up your .env file with the following:

* Hopsworks Project Name and API Key