GeoAI_DelhiAirshed

Satellite Image Classification – IIT Gandhinagar Selection Task

Project Overview

This project presents an end-to-end AI-based pipeline for automated land cover classification over the Delhi Airshed using Sentinel-2 Surface Reflectance imagery (10 m resolution, January 2025).
It was developed for the Earth Observation and Computer Vision selection task at IIT Gandhinagar, under an ISRO-sponsored theme on automated crop mapping.

The workflow combines spatial reasoning, satellite image processing, and deep learning to identify cropland and built-up areas.

Pipeline Summary

Q1 – Spatial Reasoning & Data Download

Visualized Delhi-NCR and Delhi-Airshed shapefiles using matplotlib and geemap.

Downloaded Sentinel-2 SR imagery (RGB, < 10 % cloud cover, January 2025) using Google Earth Engine.

Exported 1280 m × 1280 m tiles, named by center coordinates.

Verified total tile count and created a satellite overlay map.

Q2 – Label Construction & Dataset Preparation

Extracted 128 × 128 patches from ESA WorldCover 2021 (land_cover.tif).

Assigned labels using mode-based class logic and ESA → standard label mapping.

Addressed No-Data and mixed-class dominance.

Performed a 60/40 train–test split and visualized class distribution.

Q3 – Model Training & Evaluation

Trained a ResNet-18 CNN for supervised crop/built-up classification.

Computed both custom and torchmetrics F1 scores.

Visualized the confusion matrix and qualitative predictions.

Saved 5 correct and 5 incorrect classification examples.

### Model Weights
The trained model file (`resnet18_best.pth`, ~45 MB) exceeds GitHub’s 25 MB limit.  
You can download it from Google Drive here: (https://drive.google.com/file/d/1N9zb6o2wwAEk_1OGRkMCGA3mTCICln_O/view?usp=drive_link)


How to Run
# 1. Clone the repository
git clone https://github.com/diyabodiwala/GeoAI_DelhiAirshed.git
cd GeoAI_DelhiAirshed

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch notebook
jupyter notebook selection_task.ipynb

Dataset Access

Sentinel-2 tiles (January 2025, RGB, 10 m resolution) are available here:
Google Drive – SentinelTiles

Author

Diya Bodiwala

GeoAI_DelhiAirshed – IIT Gandhinagar Selection Task (Earth Observation & Computer Vision)

Status

Completed Q1 – Spatial Reasoning 

Completed Q2 – Label Construction 

Completed Q3 – Model Training & Evaluation 

All outputs reproducible and verified 
