**CKW Energy Consumption Data - Customer Segmentation Tool**

A Python tool for customer segmentation using household energy consumption data from CKW. This tool is specifically designed to analyze anonymized, monthly household energy data and generate meaningful consumption patterns and clusters.

To create the environment, run:
```bash
conda env create -f environment.yml

Data source: CKW Open Data Portal
Project Structure
Core Analysis Files

    CKW.ipynb: Extracts seasonal profiles from monthly anonymized data provided by CKW. These profiles are used as the foundation for further analyses.

Preprocessing Files

    Day_profiles_preprocessing.ipynb: Creates representative day profiles with 96 data points (15-minute intervals) based on the seasonal profiles.

    Day_averaged_preprocessing.ipynb: Generates a day-averaged energy consumption profile for the entire year, averaging the energy consumed per day.

    Weekdays_weekend_preprocessing.ipynb: Creates weekday and weekend profiles from the seasonal profiles. Adjust the holiday dates in this file as needed.

Analysis and Clustering Files

    Analysis.ipynb: Performs outlier analysis, calculates the total energy consumption per household, and plots peak vs. total consumption distributions.

    Seasonal_clustering.ipynb: Applies K-means clustering to seasonal profiles generated in CKW.ipynb. Clusters are visualized to show patterns across the seasons.

    Day-averaged-clustering.ipynb: Clusters day-averaged profiles using K-means. This notebook also examines the effect of temperature on energy consumption within each cluster using a Generalized Additive Model (GAM).

    Day_clustering.ipynb: Uses K-means to cluster the representative day profiles from Day_profiles_preprocessing.ipynb. Seasonal variations in clusters are visualized using Sankey plots. This file also demonstrates cluster-specific Time-of-Use price scheme design.

    Weekday_weekend_clustering.ipynb: Clusters weekday and weekend profiles separately using K-means.

Clustering Methods and Validation Metrics

Each clustering notebook includes the following validation metrics to assess clustering performance:

    Silhouette Score
    Davies-Bouldin Index
    Calinski-Harabasz Score

Usage Instructions

    Data Preparation: Use CKW.ipynb to extract and format seasonal profiles from the CKW dataset.
    Preprocessing: Run the preprocessing notebooks as needed based on the analysis type.
    Analysis and Clustering: Use the appropriate clustering notebook to group and analyze profiles.
    Visualization and Insights: Each notebook includes visualizations of the clustering results, along with insights derived from the profiles and patterns.

Additional Notes

    Holiday Adjustment: Remember to update holiday dates in Weekdays_weekend_preprocessing.ipynb as required.
    Temperature Effect Analysis: The Day-averaged-clustering.ipynb notebook incorporates temperature data to explore how weather impacts energy consumption.
