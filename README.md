# Detection and Classification of Four Land Types in Southeast London Using KMeans Clustering and XAI

## Problem Description

The goal of this study is to apply **KMeans clustering** on **Sentinel-2 imagery** to detect and classify **four land types** in the **southeastern part of London**. The four categories include **inland water bodies**, **marine water bodies**, **urban areas**, and **other land types**. 

The analysis focuses on the **southeastern part of London**, which has a high density of small lakes and rivers, making it suitable for detecting inland water bodies. Additionally, this region presents a challenge in distinguishing between water bodies and surrounding land. To enhance the differentiation, this study computes the **NDVI** and **NDWI** indices to better separate water bodies from land features.

The approach begins by preprocessing the **Sentinel-2 imagery** using bands **B2 (Blue)**, **B3 (Green)**, **B4 (Red)**, and **B8 (NIR)**. NDVI and NDWI are computed, and then **KMeans clustering** is applied to classify the pixels into four categories. The clustering results are visualized, and the **XAI (Explainable Artificial Intelligence)** method is used to analyze the importance of each feature in the clustering process.

This method provides a more interpretable understanding of the results by showing how different features contribute to each cluster. Radar charts are used to display the spectral profiles of the cluster centers and the pixel count distribution for each cluster, giving a better overview of the classification results.
