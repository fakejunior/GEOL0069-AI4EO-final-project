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
![image](https://github.com/user-attachments/assets/bb52d327-ca33-4bb5-a3f0-5e1a60efacef)


### Data Selection Criteria

The data was specifically chosen for the following reasons:
- **Minimal cloud cover**: The selected date (April 29, 2025) exhibited low cloud coverage, which is ideal for accurate classification and detection of land types.
- **High spatial resolution**: The 10m resolution allows for detailed detection of small water bodies, urban areas, and other land types, making it suitable for land use classification tasks.
![image](https://github.com/user-attachments/assets/61927fc3-d1ab-4180-b4cb-238dad10f4fd)

The final dataset includes **Sentinel-2A Level 2A data**, providing atmospherically corrected reflectance values, which is essential for accurate analysis in environmental monitoring.

## Method and Results

This project utilizes high-resolution Sentinel-2 imagery and combines **KMeans clustering** with explainable artificial intelligence (XAI) techniques to classify land types in Southeast London and the English Channel. The use of band stacking and spectral indices (NDVI, NDWI) enhances the separation between different land cover types such as water bodies, urban areas, vegetation, and other surfaces.
![1748261007910](https://github.com/user-attachments/assets/d56fe60f-63c5-454e-8bfc-3c7fbb436faa)

### 1. Clustering Results Visualization

After band stacking and feature extraction, feature standardization is applied. The KMeans algorithm then automatically assigns each pixel to one of four clusters. The results section includes visualizations of the original RGB image, spatial distribution of clusters, and masks of each cluster overlaid on the original image. Pixel count per cluster is also presented in a bar plot, providing a clear overview of the proportion and spatial distribution of each land type in the study area.
![image](https://github.com/user-attachments/assets/007bc430-451f-42c8-9b55-126e0cf186b6)
![image](https://github.com/user-attachments/assets/deef2ade-0a57-4d79-aec5-e169baccffa6)

### 2. XAI Analysis

To better interpret the physical meaning of each cluster, XAI techniques are applied to analyze the cluster centers. Radar charts and bar plots are used to show the mean values of each feature (the four bands, NDVI, and NDWI) for every cluster, giving insight into the spectral characteristics of each class. For example, urban and water classes can be clearly distinguished in NDWI and NDVI, with water-related clusters typically showing negative NDWI, while vegetation clusters have much higher NDVI values than others.
![image](https://github.com/user-attachments/assets/40f9f2cc-d1e5-47f9-9b46-0b816d478ef8)
![image](https://github.com/user-attachments/assets/6a0cab8b-6af9-4609-9e94-bc64c59d26e6)

This explainability analysis helps to relate clusters to actual land cover types and offers a quantitative, data-driven reference for future automatic land classification tasks.

## Getting Started

This project was created using **Google Colab**, a cloud-based platform for modifying and sharing code. To get this project up and running, follow these steps:

1. Download the **ML Detection of Land Types.ipynb** file from this repository to get started.
2. Download the required datasets. See below for how to acquire the datasets.
3. Modify the file paths in the Colab notebook to match the location where the dataset is saved.
4. If using the same datasets as the original notebook, no other changes are necessary.
5. If using a different dataset, modify the filenames where they are used in the notebook. Simply copy the corresponding filename from your dataset and replace the one in the notebook.
6. Run the cells in the notebook sequentially. Further instructions can be found within the notebook.
[![Check out my YouTube video](https://img.youtube.com/vi/ytd1h5Hr31Q/0.jpg)](https://www.youtube.com/watch?v=ytd1h5Hr31Q)

## An Assessment of the Environmental Cost of the Research Project
In this study, the A100 GPU provided by Google Colab was used for computation, primarily running the **KMeans clustering algorithm**. The time complexity of the **KMeans clustering** algorithm is O(n * k * d), where n is the number of samples, k is the number of clusters, and d is the feature dimension for each sample. Although the algorithm is efficient, it still requires computational resources, particularly when dealing with large image datasets. The computation took approximately 7 minutes, which is reasonable given the data volume and computational demands.

While the **KMeans clustering** algorithm itself is not highly computationally intensive, the consumption of computational resources becomes noticeable when processing high-resolution satellite imagery. Using **Google Colab** for computation helps save local hardware resources, but cloud computing services come with their own energy consumption in data centers. The energy consumption varies depending on the server configuration and computational tasks. For each experiment, the energy consumption is relatively small, but when cloud computing is continuously used over the long term or for large-scale data analysis, the overall energy consumption and carbon footprint become significant.

Moreover, while cloud computing platforms help reduce the burden on local hardware, they still carry an environmental cost, particularly with large-scale computations. To ensure sustainability and reduce the carbon footprint, future efforts could focus on more efficient data processing methods to minimize unnecessary computational resource usage. This can be achieved by optimizing algorithms or reducing redundant computations to lower overall energy consumption. By adopting such approaches, it is possible to maintain research quality while minimizing the environmental impact.

## References
1. Sentinel-2 Data for Environmental Monitoring
Copernicus Sentinel-2. (2020). Sentinel-2 User Guide. European Space Agency.
Retrieved from: https://sentinels.copernicus.eu/web/sentinel/user-guides/sentinel-2-msi
2. Recent Advances in KMeans Clustering
Zhang, Y., & Liu, S. (2020). A review of the K-means clustering algorithm and its applications. International Journal of Computer Science and Network Security, 20(10), 49-56.
Retrieved from: https://www.ijcsns.com
3. Gaussian Mixture Models (GMM) for Remote Sensing
Lasserre, C., & Thomas, G. (2019). Gaussian Mixture Models in Remote Sensing: Applications to Earth Observation Data. Remote Sensing, 11(4), 392.
DOI: 10.3390/rs11040392
4. Using NDVI and NDWI for Water Body Detection
Li, Y., Wang, J., & Zhang, L. (2021). Improved classification for water body detection using NDVI and NDWI indices from Sentinel-2 imagery. Journal of Applied Remote Sensing, 15(2), 023501.
DOI: 10.1117/1.JRS.15.023501
5. XAI in Remote Sensing: Interpretable Models
Ribeiro, M. T., Singh, S., & Guestrin, C. (2020). "Why Should I Trust You? Explaining the Predictions of Any Classifier". In Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining, 1135-1144.
DOI: 10.1145/2939672.2939778
6. Copernicus Data Access and Usage
European Space Agency (ESA). (2021). Copernicus Open Access Hub: Data Discovery and Access for Earth Observation.
Retrieved from: https://scihub.copernicus.eu/dhus
7. Land Use and Land Cover Classification Using Remote Sensing
Ahmed, F., & El-Dahshan, E. A. (2021). A review of machine learning techniques for land use and land cover classification using remote sensing. Remote Sensing Applications: Society and Environment, 22, 100429.
DOI: 10.1016/j.rsase.2020.100429
8. Advances in Satellite Remote Sensing for Environmental Monitoring
Schmidt, M., & Guzmán, A. (2021). Recent advancements in satellite remote sensing for environmental monitoring. Environmental Research Letters, 16(11), 114004.
DOI: 10.1088/1748-9326/ac14da
