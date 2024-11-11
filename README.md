CKW Energy Consumption Data - Customer Segmentation Tool

A Python tool for customer segmentation using household energy consumption data from CKW, aimed at generating insights from anonymized, monthly household energy data through meaningful consumption patterns and clustering.
Environment Setup

To set up the environment, run:

bash

conda env create -f environment.yml

Data Source

Data is sourced from the CKW Open Data Portal, providing anonymized household consumption data for segmentation and analysis.
Project Structure
Core Analysis File

    CKW.ipynb: Extracts seasonal energy profiles from monthly anonymized data provided by CKW, forming the basis for all subsequent analyses.

Preprocessing Files

    Day_profiles_preprocessing.ipynb: Creates daily profiles with 96 data points (15-minute intervals) from the seasonal profiles, representing typical daily usage patterns.

    Day_averaged_preprocessing.ipynb: Generates a yearly day-averaged energy consumption profile, calculating the average energy used per day.

    Weekdays_weekend_preprocessing.ipynb: Separates profiles into weekday and weekend patterns based on seasonal profiles, with customizable holiday dates.

Analysis and Clustering Files

    Analysis.ipynb: Conducts outlier analysis, calculates total energy consumption per household, and plots peak vs. total consumption.

    Seasonal_clustering.ipynb: Uses K-means clustering to identify seasonal consumption patterns from the profiles generated in CKW.ipynb. Cluster patterns are visualized to illustrate seasonal trends.

    Day-averaged-clustering.ipynb: Clusters the day-averaged profiles from Day_averaged_preprocessing.ipynb. Analyzes temperature impacts on consumption within clusters using a Generalized Additive Model (GAM).

    Day_clustering.ipynb: Clusters daily profiles (from Day_profiles_preprocessing.ipynb) using K-means, with seasonal variations visualized through Sankey plots. Demonstrates Time-of-Use price scheme design for each cluster.

    Weekday_weekend_clustering.ipynb: Applies K-means clustering to separate weekday and weekend profiles.

Clustering Methods and Validation Metrics

Each clustering notebook includes key metrics to assess cluster quality:

    Silhouette Score: Measures cohesion within clusters.
    Davies-Bouldin Index: Evaluates average similarity between clusters.
    Calinski-Harabasz Score: Assesses cluster separation and compactness.

Usage Instructions

    Data Extraction: Use CKW.ipynb to extract and format seasonal profiles from the CKW dataset.
    Data Preprocessing: Run preprocessing notebooks based on the analysis type.
    Analysis and Clustering: Choose the appropriate clustering notebook for grouping and analyzing profiles.
    Visualization and Insights: Each notebook contains visualizations and insights, revealing patterns in consumption and exploring potential Time-of-Use pricing schemes.

Additional Notes

    Holiday Adjustment: Remember to update holiday dates in Weekdays_weekend_preprocessing.ipynb as required.
    Temperature Effect Analysis: The Day-averaged-clustering.ipynb notebook incorporates temperature data to explore how weather impacts energy consumption.
