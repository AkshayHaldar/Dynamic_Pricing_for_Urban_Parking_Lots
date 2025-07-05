# Dynamic Pricing for Urban Parking Lots

## Project Overview
This project implements a dynamic pricing model for urban parking lots using real-time data analytics and stateful simulations. The goal is to optimize parking prices based on occupancy, queue length, traffic conditions, vehicle types, and special days to improve revenue and manage demand effectively.

## Author
Akshay Haldar

## Date
July 7, 2025

## Description
The project leverages a dataset containing parking lot occupancy, queue lengths, vehicle types, and traffic conditions. It preprocesses the data, performs exploratory data analysis (EDA), and applies machine learning models to simulate dynamic pricing strategies.

## Data
- The dataset includes features such as Latitude, Longitude, Capacity, Occupancy, QueueLength, VehicleType, TrafficConditionNearby, IsSpecialDay, and timestamps.
- Data preprocessing involves combining date and time columns into a single timestamp and cleaning the dataset for analysis.

## Methodology
- Exploratory Data Analysis (EDA) to understand patterns and correlations in the data.
- Implementation of two pricing models:
  - Model 1: Baseline linear model adjusting prices based on occupancy rate.
  - Model 2: Demand-based pricing model incorporating multiple factors such as queue length, traffic conditions, vehicle type, and special days.
- Stateful simulations using the Pathway library to update prices in real-time based on incoming data streams.

## Setup and Installation
1. Ensure Python 3.x is installed.
2. Install required libraries:
   ```
   pip install pathway pandas matplotlib seaborn
   ```
3. Place the dataset file `dataset.csv` in the project directory.
4. Run the Jupyter notebook `Dynamic_Pricing_for_Urban_Parking_Lots.ipynb` to execute the analysis and simulations.

## Usage
- The notebook guides through data loading, preprocessing, EDA, and model implementation.
- Visualizations include time-series patterns, correlation heatmaps, and price evolution charts.
- The final output includes dynamic pricing recommendations for each parking lot.

## Results
- The models demonstrate how prices can be adjusted dynamically based on real-time data.
- Visualizations help in understanding occupancy trends and the impact of various factors on pricing.

## Notes
- The project uses the Pathway library for real-time data processing and stateful computations.
- The dataset and models can be extended or adapted for other urban mobility or resource allocation problems.

## References
- Pathway library documentation: https://pathway.com
- Data visualization with Matplotlib and Seaborn

---

This README provides an overview and instructions to understand and run the dynamic pricing project for urban parking lots.
