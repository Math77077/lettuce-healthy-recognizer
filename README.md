# Lettuce Disease Detection with YOLO11 and RT-DETR

[![Language: Pt-BR](https://img.shields.io/badge/Language-pt--BR-blue.svg)](README.pt-BR.md)

This repository features a Deep Learning-based computer vision pipeline designed to identify and classify health conditions in lettuce crops. The project compares the performance of the latest **YOLO11** architecture against the Real-Time Detection Transformer (**RT-DETR**) to provide a robust solution for precision agriculture.

## 📌 Project Overview

Early identification of leaf diseases is vital for crop management. This project implements an automated pipeline for:
- **Dataset Acquisition:** Integration with Roboflow API for seamless data loading.
- **Data Engineering:** Automated rebalancing of training and testing sets (80/20 split) to ensure model generalization.
- **Model Training:** Comparative training and validation between **YOLO11l** and **RT-DETR-l**.
- **Inference & Validation:** Real-time processing of high-resolution images and videos from local vegetable gardens.

## 🛠️ Technology Stack

- **Framework:** [Ultralytics](https://github.com/ultralytics/ultralytics) (YOLO11 & RT-DETR)
- **Dataset Management:** Roboflow API
- **Language:** Python 3.12+
- **Deep Learning:** PyTorch with CUDA acceleration (NVIDIA RTX 4050 tested)
- **Computer Vision & Utils:** OpenCV, Matplotlib, PyYAML, Pillow

## 📂 Repository Structure


```text
├── 01_lettuce_disease_detection.ipynb   # Main pipeline notebook
├── requirements.txt                     # Python dependencies
├── .gitignore                           # Git ignore rules
├── README.md                            # Main documentation (English)
└── README.pt-BR.md                      # Documentation in Portuguese
```

## 📊 Dataset Details

The dataset (`disease-lettuce-h69zb`) contains images classified into several categories, including:
- Healthy
- Septoria Blight
- Downy Mildew
- Bacterial
- Lettuce Mosaic Virus
- Lettuce Anthracnose

Images are pre-processed to a resolution of **640x640** for training and up to **1280x1280** for high-precision video inference.

## 🚀 Performance & Training Setup

| Model | Task | Image Size | Batch Size | Target Device |
| :--- | :--- | :--- | :--- | :--- |
| **YOLO11l** | Detection | 640 | 8 | RTX 4050 |
| **RT-DETR-l** | Detection | 640 | 8 | RTX 4050 |

### Key Results
The models are validated on real-world test sets and local garden video footage, demonstrating high FPS during inference while maintaining high mAP (mean Average Precision) across multiple disease classes.

## ⚙️ Installation & Usage

### 1. Clone the Repository
```bash
git clone [https://github.com/Math77077/lettuce-healthy-recognizer.git](https://github.com/Math77077/lettuce-healthy-recognizer.git)
cd lettuce-healthy-recognizer

```

### 2. Install Dependencies

```bash
pip install -r requirements.txt

```

### 3. Run the Pipeline

Open `01_lettuce_disease_detection.ipynb` in Jupyter Lab or VS Code and execute the cells sequentially to download the dataset, rebalance splits, train the models, and run qualitative evaluations.

### 4. Quick Video Inference Example

```python
from ultralytics import YOLO

# Load trained checkpoint
model = YOLO('treinamento_lettuce_results/YOLO11/weights/best.pt')

# Run prediction on video
results = model.predict(source='videos/sample.mp4', save=True, imgsz=1280, conf=0.25)

```

## 📊 Qualitative Evaluation

The pipeline includes visual inspection scripts comparing **Ground Truth** bounding boxes against **Model Predictions** side-by-side to analyze detector behavior under varying lighting conditions.

---

### 🤝 Contribution & Maintenance

Maintained as part of an Artificial Intelligence research group focused on agricultural technology and precision farming.


---

