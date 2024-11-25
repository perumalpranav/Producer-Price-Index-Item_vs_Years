# Exploring Food Price Trends: A Clustering and PCA Analysis

## Overview
This project analyzes historical food price data from the US Department of Agriculture (USDA), exploring annual percentage changes in food produce prices from 1974-2023. The analysis employs Principal Component Analysis (PCA) and clustering techniques (K-Means and DBSCAN) to identify patterns and relationships in price fluctuations across different food categories.

## Dataset
- Source: [USDA Food Price Outlook](https://www.ers.usda.gov/data-products/food-price-outlook/)
- Supplementary data: [St. Louis FRED](https://fred.stlouisfed.org/series/WPU01710703)
- Features: 16 different food categories
- Time span: 1974-2023 (49 years)
- ~900 total data points
- Note: Missing values for 'Farm-level eggs' (1983, 1984) were supplemented with St. Louis data

## Features
The project includes several key analysis components:

1. **Data Preprocessing**
   - Handling missing values
   - Data standardization
   - Creation of year-indexed and item-indexed dataframes

2. **Initial Data Visualization**
   - Time series visualization of price changes
   - Descriptive statistics analysis
   - Feature correlation analysis

3. **PCA Analysis**
   - Dimensionality reduction
   - Visualization of principal components
   - Cumulative explained variance analysis

4. **K-Means Clustering**
   - Elbow method for optimal k determination
   - Silhouette score analysis
   - Cluster visualization in PCA space

5. **DBSCAN Clustering**
   - K-distance analysis for epsilon determination
   - Noise point identification
   - Cluster comparison with K-Means results

## Requirements
```python
# Required Python packages
sklearn
pandas
numpy
matplotlib
seaborn
```

## Usage
```python
# Example usage of main analysis functions

# For PCA Analysis
pcaAnalysis(df, target='Year', features=feature_list)

# For K-Means Analysis
kmeansStats(df, features=feature_list)
kmodel(df, optimal_k=4, features=feature_list)

# For DBSCAN Analysis
DBSCANStats(df, features=feature_list)
performDBSCAN(df, features=feature_list, eps=44, min_samples=3)
```

## Key Findings
1. **Data Structure**
   - The dataset shows significant variation in price changes across different food categories
   - No clear year-to-year correlation patterns were identified

2. **PCA Results**
   - Limited explained variance with two principal components
   - Better separation achieved with year-indexed analysis compared to item-indexed

3. **Clustering Analysis**
   - K-Means identified 4 distinct clusters of years with similar price change patterns
   - DBSCAN results varied significantly based on parameter selection
   - Conflicting results between clustering methods suggest high data complexity

## Challenges and Limitations
- High data dimensionality and noise
- Limited explained variance in PCA with two components
- Inconsistent clustering results between different methods
- Complex temporal relationships in price changes

## Repository Structure
```
├── CS243FinalProject.ipynb     # Main analysis notebook
├── historicalppi.xlsx          # Raw data file
├── README.md                   # This file
└── requirements.txt            # Package dependencies
```

## Author
Pranav Perumal

## Date
November 26, 2024

## License
This project is licensed under the MIT License - see the LICENSE file for details.
