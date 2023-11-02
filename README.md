# Unsupervised Machine Learning

Unsupervised machine learning involves extracting patterns, structures, or relationships from data without labeled outcomes. It encompasses techniques like clustering, dimensionality reduction, and anomaly detection, allowing algorithms to learn and explore data's inherent characteristics independently.

![image](https://github.com/JasmineBamba/CryptoClustering/assets/135666038/c49e2977-e146-4854-9384-e8f4ddb1efe5)


## Table of Contents

- [Project Overview](#project-overview)
- [Preparing Data](#preparing-data)
- [Finding the Best Value for K](#best-value-k)
- [Clustering Cryptocurrencies with K-means Algorithm](#clustering)
- [Optimizing Clusters with Principal Component Analysis (PCA)](#PCA-clustering)
- [Determining Optimal k using PCA Data](#pca-best-value-k)
- [Clustering Cryptocurrencies with K-means Using PCA Data](#clustering-pca-data)

## Project Overview

The project aims to leverage Python and unsupervised learning techniques to forecast the influence of 24-hour versus 7-day price fluctuations on cryptocurrencies. The goal is to analyze and predict the impact of short-term (24-hour) and longer-term (7-day) price changes within the cryptocurrency market using machine learning methodologies.

![image](https://github.com/JasmineBamba/CryptoClustering/assets/135666038/c6141d2e-3420-4ea4-94d3-142a2582eedd)

## Preparing Data

To normalize the data from the CSV file using StandardScaler() from scikit-learn and create a DataFrame with the scaled data while setting the "coin_id" index from the original DataFrame as the index for the new DataFrame.

SCREENSHOT

## Finding the Best Value for K

To determine the optimal value for 'k' using the elbow method, the following steps were employed:

- **Creating a List of K Values:** A list ranging from 1 to 11 was generated to evaluate different 'k' values.
- **Inertia Calculation:** An empty list was initialized to capture the inertia values for each 'k'.
- **Looping for Inertia Computation:** A for loop was utilized to calculate the inertia for each 'k' value.
- **Elbow Curve Data Dictionary:** A dictionary was constructed to contain the data necessary for plotting the elbow curve.
- **Visual Identification of Optimal 'k':** A line chart was plotted using the computed inertia values for different 'k' values to visually identify the elbow, indicating the optimal 'k' value.

  screenshot
  
The analysis revealed that the optimal value for 'k' is determined at the point where the inertia no longer significantly decreases, forming an 'elbow' in the plot. This 'elbow' point suggests the most suitable 'k' value for clustering the data effectively.

## Clustering Cryptocurrencies with K-means Algorithm

To cluster cryptocurrencies using the K-means algorithm with the original scaled data, follow these steps:

- **Initialization:** Initialize the K-means model using the best value for 'k'.
- **Model Fitting:** Fit the K-means model using the original scaled DataFrame.
- **Clustering:** Predict clusters to group cryptocurrencies based on the original scaled data.
- **Data Augmentation:** Create a copy of the original data and introduce a new column to hold the predicted clusters.
- **Visualization:** Utilize hvPlot to generate a scatter plot with the following configurations:
               - Set "PC1" for the x-axis and "PC2" for the y-axis.
               - Color the data points using the labels obtained from the K-means algorithm.
               - Include the "coin_id" column in the hover information to identify each cryptocurrency represented by the data point.

SCREENSHOT

## Optimizing Clusters with Principal Component Analysis (PCA)

In this section, we will use Principal Component Analysis (PCA) to optimize clusters in our data. Follow these steps to perform PCA and understand the explained variance:

- **Performing PCA**: Utilize the original scaled DataFrame to apply PCA and reduce feature dimensions to three principal components. You can achieve this using Python and libraries like scikit-learn.
- **Explained Variance**: Retrieve the explained variance for each of the three principal components. This step helps us understand the significance of each component in retaining information.
- **Total Explained Variance**: Calculate the total explained variance of the three principal components. This provides a measure of how much of the original data's variance is retained.
- **Creating a New DataFrame**: Generate a new DataFrame with the PCA-transformed data. Ensure that you set the "coin_id" index from the original DataFrame as the index for this new DataFrame.
- **Sample of the PCA DataFrame**: Below is a sample of the first five rows of the PCA DataFrame to give you an idea of its structure and contents:

SCREENSHOT

## Determining Optimal k using PCA Data

To identify the best value for 'k' using the elbow method on PCA-transformed data, follow these steps:

- **Creating a Range of k-values:** Generate a list of integers from 1 to 11 to represent the various k-values.
- **Storing Inertia Values:** Initialize an empty list to hold the inertia values computed for different k-values.
- **Computing Inertia for Each k:** Use a for loop to calculate the inertia for each k-value by fitting the K-means model on the PCA-transformed data.
- **Constructing a Dictionary for Plotting:** Create a dictionary with the computed inertia values against the respective k-values to generate the Elbow curve.
- **Visualization of Elbow Curve:** Plot a line chart displaying all the inertia values against the different k-values to visually determine the optimal value for k.

SCREENSHOT

## Clustering Cryptocurrencies with K-means Using PCA Data

To cluster cryptocurrencies and determine the optimal value for 'k' on the PCA data, below steps were followed:

- **Initializing K-means Model:** Set up the K-means model with the selected 'k' value for clustering.
- **Fitting the K-means Model:** Fit the K-means model using the PCA-transformed data.
- **Predicting Clusters:** Use the trained model to predict clusters for the cryptocurrencies based on the PCA data.
- **DataFrame Modification:** Make a copy of the DataFrame with the PCA data and introduce a new column to store the predicted clusters.
- **Visualization using hvPlot:**  Utilize hvPlot to generate a scatter plot with the following configurations:
                          - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
                          - Color the data points based on the labels derived from the K-means clustering.
                          - Include the "coin_id" column in the hover data to identify each cryptocurrency represented in the plot.

SCREENSHOT
                        
## References

Unsupervised ML image source:bigdata-madesimple.com

