# Uber-Rides-Data-Analysis

**DATASET**
The datasets are provided in parts because of the upload size constraints. Each of the datasets consists of the date, longitudinal value, latitudinal value. 


The provided code demonstrates a Python script for performing a variety of data analysis and visualization tasks using Uber ride data. Let's break down the code into different sections and provide explanations for each one:

**Data Loading and Preparation:**
The script begins by importing the necessary libraries and loading Uber ride data from multiple CSV files representing different months (April to September) of the year 2014 into separate DataFrames (apr 14, may 14, jun 14, JUL 14, aug 14, sep 14). These DataFrames are then concatenated into a single DataFrame named merged_df.

The 'Date/Time' column of each DataFrame is converted to a DateTime format using the pd.to_datetime() function.

**Data Visualization - Histogram of Time:**
A histogram of the time of day when Uber rides occurred is created. The script extracts the time component from the 'Date/Time' column and generates a new column 'Time', which represents the time of day in seconds. The Seaborn library is used to create a histogram plot of the 'Time' column.

**Data Filtering - Morning and Evening DataFrames:**
The code filters the current_df DataFrame to create two new DataFrames - morning_df containing Uber rides that occurred during the morning (between 5 AM and 11 AM) and evening_df containing rides that occurred during the evening (between 3 PM and 10 PM).

**Data Visualization on Maps using Folium:**
The Folium library is employed to visualize the Uber ride data on interactive maps.

**Morning Map:** A map with a specific center location is generated, and circular markers are added for a subset of morning Uber ride coordinates. These markers indicate the pickup locations of morning rides.

**Evening Map:** Similarly, another map is created for evening rides, and red circular markers are used to highlight evening ride pickup locations.

**K-Means Clustering:**
K-Means clustering is applied to the Uber ride data coordinates to identify clusters of pickup locations.

A function named evaluate_KMeans(X) is defined to plot the inertia (within-cluster sum of squares) against the number of clusters, aiding in determining an optimal number of clusters.

A K-Means model is initialized with 6 clusters and fitted to the coordinates of morning rides. Cluster centroids are extracted.

Markers with red icons are added to the morning map to indicate the cluster centroids.

The same process is repeated for evening ride coordinates, using blue icons for the cluster centroids.

K-Means clustering is performed on the entire dataset (current_df) with 6 clusters, and centroids are extracted.

Blue markers represent the cluster centroids, and a green marker designates a new ride location on the map.

Finally, the cluster centroid index to which the new ride belongs is determined, and a red marker is added to the map for that centroid.


