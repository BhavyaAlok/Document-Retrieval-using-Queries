# DOCUMENT RETRIEVAL AND ANNOTATION PIPELINE

## DESCRIPTION

This project provides a way to manage and verify document datasets.  
It uses a notebook to bridge the gap between image storage and metadata generation.  
It is built for large document collections where visual quality checks are needed before training models.  
It automates file name extraction and pairs them with annotation structures.

## KEY FEATURES

### Visual Inspection

The tool uses matplotlib to show 10 random document images.  
This allows for a quick manual check of image quality and layout.

### Metadata Structuring

It creates a JSON object for every file.  
Each object includes the filename, an annotation placeholder, and a corruption block for tracking quality issues.

### Automated Export

The script creates a results directory and fills it with individual JSON files.  
It processes the whole directory automatically.

## TECHNICAL REQUIREMENTS

Python 3.x  
matplotlib  
os, json, random  

## USAGE

Set your image directory path in the script.  
Run the visualization cell to see random samples.  
Run the export cell to save JSON files in the results folder.

## OUTPUT SCHEMA

Each JSON file includes:

file_name: name of the image  
annotations: list of prediction data  
corruption: includes type and severity  

## NOTES

The script uses Windows path formatting.  
Adjust paths if you use Linux or macOS.

---

## PYTHON CODE

### Visual inspection cell

```python
import os
import random
import matplotlib.pyplot as plt
from PIL import Image

IMAGE_DIR = r"C:\path\to\your\images"

files = [f for f in os.listdir(IMAGE_DIR) if f.lower().endswith(('.png', '.jpg', '.jpeg'))]
sample_files = random.sample(files, min(10, len(files)))

plt.figure(figsize=(15, 8))

for i, file in enumerate(sample_files):
    img_path = os.path.join(IMAGE_DIR, file)
    img = Image.open(img_path)
    plt.subplot(2, 5, i + 1)
    plt.imshow(img)
    plt.title(file)
    plt.axis("off")

plt.tight_layout()
plt.show()
