# Dynamic Pricing for Urban Parking Lots

## Project Overview
This project implements a dynamic pricing model for urban parking lots using real-time data analytics and stateful simulations. The goal is to optimize parking prices based on occupancy, queue length, traffic conditions, vehicle types, and special days to improve revenue and manage demand effectively.

## Author
Akshay Haldar

## Date
July 6, 2025

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

## Tech Stack
- Python 3.x
- Pandas for data manipulation
- Matplotlib and Seaborn for data visualization
- Pathway library for real-time data processing and stateful computations
- Jupyter Notebook for interactive analysis and simulation

## Architecture Diagram

flowchart TD
    A[Dataset: Parking Lot Data] --> B[Data Loading & Preprocessing]
    B --> C[Exploratory Data Analysis (EDA)]
    C --> D[Real-Time Data Streaming]
    D --> E[Stateful Simulation with Pathway]
    E --> F[Pricing Models]
    F --> G[Baseline Linear Model]
    G--> H[Demand-Based Pricing Model]
    H --> I[Price Updates]
    I --> J[Output Visualization & Results]
```

## Project Architecture and Workflow

1. **Data Loading & Preprocessing**  
The raw dataset contains, 18,368 records, needed cleaning and feature engineering to be appropriate for the simulation. The main steps involved using the Pandas , matplotlib.pyplot,seaborn  were:

1.Timestamp Consolidation: The LastUpdatedDate and LastUpdatedTime columns were merged into one, and make timestamp column. This was essential for Pathway to accurately order events in their time stream.

2.Unique Lot Identification: A unique parking_lot_id (0-13) was assigned to every distinct Latitude and Longitude coordinate pair. This ID was necessary to monitor the state (i.e., current price) of every single parking lot during the simulation.

3.Data Cleaning: Excess columns were removed, and the final, cleaned dataset was written to dataset_stream.csv to be used as the input for the real-time pipeline.

 **Real-Time Data Streaming and Stateful Simulation**  
   The Pathway library is used to simulate real-time data streaming and stateful computations. The cleaned dataset is streamed into Pathway, which maintains state tables for parking lot prices and updates them dynamically based on incoming data.

2. **Implement Model 1 (Baseline Linear Model)**  
 Adjusts prices based on occupancy rate using a simple linear formula.
✅ Step 3.1: Creating state table for prices...
   -> State table 'price_table' created from file with base price $10.0 for all 14 lots.
✅ Step 3.2: Reading parking data into a real-time stream.
✅ Step 3.3: Configured join between data stream and price table.
✅ Step 3.4: Applying pricing formula with ALPHA = 1.0.
✅ Step 3.5: Price update logic defined.
   - **Demand-Based Pricing Model 2:** 
   Incorporates multiple factors such as queue length, traffic conditions, vehicle type, and special days to calculate a demand score that influences pricing. This model uses weights for each factor and applies a nonlinear transformation to normalize demand.

3.**Stateful Pricing Simulation : FINAL DYNAMIC PRICES FROM PATHWAY PIPELINE**  
   The project simulates price updates in a stateful manner, where each event updates the current price for a parking lot based on the latest data. This approach reflects real-time dynamic pricing more accurately than batch processing.

4. **Output Visualization and Results**  
   Final dynamic prices for each parking lot are visualized using bar charts to show price evolution and distribution. The results demonstrate how prices can be adjusted dynamically to optimize revenue and manage demand.

   This chart clearly visualizes the final calculated price for each of the 14 parking lots. It effectively demonstrates:

---Price Differentiation: The model successfully assigned a unique price to each lot based on its demand history.
--Also has a hotspot identification and low-demand identification

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
