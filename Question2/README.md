# Assignment - Question 2

This repository contains the solution for **Question 2** of the assignment.  
The task is divided into two main parts:  

1. **Object Detection with YOLOv8**  
   - Detect cones in images stored in Google Drive  
   - Compute center points of detected cones  
   - Draw connecting lines between cones to represent layout  
   - Save processed images with annotations  

2. **GPS Coordinate Extraction and Mapping**  
   - Extract GPS metadata from images using `exifread`  
   - Convert EXIF GPS data into decimal coordinates  
   - Plot cone positions and paths on an interactive `folium` map  
   - Compare cone layouts with different time intervals (2s vs 10s wait times)  

---

## 📂 Repository Structure

```
├── Question2.ipynb # Jupyter notebook with full solution for Question 2
├── cones/ # (Optional) Place datasets here if not using Google Drive
├── README.md # Project documentation


```

## ⚙️ Requirements

The project requires **Python 3.8+** with the following dependencies:

- ultralytics (YOLOv8)  
- opencv-python  
- matplotlib  
- pillow  
- exifread  
- folium  
- Basemap  

---

## 📥 Installation

If running inside **Google Colab or Jupyter Notebook**, install dependencies directly in the first cell:

```python
!pip install ultralytics opencv-python matplotlib pillow yolo
!pip install exifread folium Basemap

If running locally, install with pip:

pip install ultralytics opencv-python matplotlib pillow exifread folium Basemap



📊 Dataset Setup

This notebook is designed to load datasets stored in Google Drive for a production-like workflow.

1)Upload your datasets to Google Drive in the following structure:
/MyDrive/Questions_RND/Question2/cones/
│
├── folder_1/          # Images for YOLOv8 cone detection
├── folder_2/          # Images with GPS data
│   ├── 2s/            # Images taken with 2 second interval
│   └── 10s/           # Images taken with 10 second interval
└── Model/
    └── Cone.pt

2)Mount Google Drive in Colab:
from google.colab import drive
drive.mount('/content/drive')


3)Update paths in the notebook to match your Drive structure if needed.
▶️ Running the Notebook

Open Question2.ipynb in Google Colab or Jupyter.

Run the first cell to install dependencies.

Mount Google Drive to access datasets and model.

Run each section step by step:

YOLOv8 Detection → Detect cones, connect their centers, save processed images.

GPS Mapping → Extract EXIF GPS data, map cone positions for 2s and 10s intervals

📈 Outputs

Processed Images:
Images with detected cones and red lines connecting their centers. Saved in the specified output folder in Google Drive.

Interactive Folium Map:
Map showing cone positions for both 2s and 10s datasets, with color-coded paths:

Blue = 2s wait time

Red = 10s wait tim
