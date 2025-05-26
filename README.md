# Detection and Classification of Four Land Types in Southeast London Using KMeans Clustering and XAI

## Problem Description

The goal of this study is to apply **KMeans clustering** on **Sentinel-2 imagery** to detect and classify **four land types** in the **southeastern part of London**. The four categories include **inland water bodies**, **marine water bodies**, **urban areas**, and **other land types**. 

The analysis focuses on the **southeastern part of London**, which has a high density of small lakes and rivers, making it suitable for detecting inland water bodies. Additionally, this region presents a challenge in distinguishing between water bodies and surrounding land. To enhance the differentiation, this study computes the **NDVI** and **NDWI** indices to better separate water bodies from land features.

The approach begins by preprocessing the **Sentinel-2 imagery** using bands **B2 (Blue)**, **B3 (Green)**, **B4 (Red)**, and **B8 (NIR)**. NDVI and NDWI are computed, and then **KMeans clustering** is applied to classify the pixels into four categories. The clustering results are visualized, and the **XAI (Explainable Artificial Intelligence)** method is used to analyze the importance of each feature in the clustering process.

This method provides a more interpretable understanding of the results by showing how different features contribute to each cluster. Radar charts are used to display the spectral profiles of the cluster centers and the pixel count distribution for each cluster, giving a better overview of the classification results.

## Data Acquisition

The data used in this study was obtained from the **Copernicus Open Access Hub** (https://browser.dataspace.copernicus.eu/), which provides free access to satellite data, including **Sentinel-2** imagery. The specific dataset selected for this analysis corresponds to **Sentinel-2A** imagery on **April 29, 2025** from **00:00 to 23:59 UTC**. This particular day was chosen because of relatively low cloud cover, allowing for clearer observations of the area.

The **Sentinel-2A** satellite provides high-resolution imagery with a spatial resolution of **10 meters**, which is ideal for detecting and classifying land types in urban and water-rich regions. The selected dataset includes the following bands:

- **B2 (Blue)**
- **B3 (Green)**
- **B4 (Red)**
- **B8 (Near-Infrared, NIR)**

These bands were chosen because they are commonly used for vegetation analysis (e.g., NDVI calculation), water body detection (e.g., NDWI calculation), and general land classification.

### Data Details

- **Satellite**: Sentinel-2A
- **Date**: April 29, 2025
- **Time Range**: 00:00 - 23:59 UTC
- **Bands Selected**: B2, B3, B4, B8
- **Spatial Resolution**: 10 meters

![image](https://github.com/user-attachments/assets/01f9666e-517d-4053-a80e-8c95a92907b5)

### Data Selection Criteria

The data was specifically chosen for the following reasons:
- **Minimal cloud cover**: The selected date (April 29, 2025) exhibited low cloud coverage, which is ideal for accurate classification and detection of land types.
- **High spatial resolution**: The 10m resolution allows for detailed detection of small water bodies, urban areas, and other land types, making it suitable for land use classification tasks.

The final dataset includes **Sentinel-2A Level 2A data**, providing atmospherically corrected reflectance values, which is essential for accurate analysis in environmental monitoring.
