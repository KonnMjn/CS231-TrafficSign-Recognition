# 🚦 CS231 - Traffic Sign Recognition

This project focuses on classifying Vietnamese traffic signs using computer vision.

---

## 📌 Table of Contents

- [Project Structure](#project-structure)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [How to Run](#how-to-run)
- [Notes](#notes)
- [License](#license)
- [Credits](#credits)

---
## 📁 Project Structure

```
CS231-TrafficSign-Recognition/ 
├── main.ipynb # Main program notebook
├── requirements.txt # List of required Python packages
├── .gitignore # Files and folders to ignore in version control
├── Project Report.pdf/ # PDF report of the project
├── Project Presentation.pptx/ # Slides used for presentation
├── Additional-Data/ # Manually added and relabeled images + updated annotations
│ ├── train/
│ │ ├── *.jpg
│ │ └── final_annotations.coco.json
│ ├── valid/
│ │ ├── *.jpg
│ │ └── final_annotations.coco.json
│ └── test/
│ │ ├── *.jpg
│ │ └── final_annotations.coco.json
├── BienBaoLe/ # Unseen data for model to predict
│   ├── *.jpg
│   └── _annotations.coco.json
```
---

## 📦 Dataset

We used the publicly available [Vietnam Traffic Sign Detection Dataset from Kaggle](https://www.kaggle.com/datasets/lvnduy/street-traffic-signs-in-vietnam-coco/data) as the base dataset.

However, the original annotations were **incomplete** for our use case, so we manually:

- Labeled additional images using [Roboflow](https://roboflow.com/)
- Modified COCO annotation files for `train`, `valid`, and `test` sets
- Stored the additional data in the `Additional-Data/` directory

> ✅ You should use the annotation files in `Additional-Data/` instead of those from the original Kaggle dataset.

---
## 🧠 Methodology

The project follows a traditional computer vision pipeline with classical machine learning for traffic sign classification. The key steps include:

### 1. Data Preparation

- Original dataset: [Vietnam Traffic Sign Detection (Kaggle)](https://www.kaggle.com/datasets/lvnduy/street-traffic-signs-in-vietnam-coco/data)
- Additional images were labeled using Roboflow and stored in `Additional-Data/`.
- All annotations are in COCO format (`.json`), loaded and parsed using `pycocotools`.

### 2. Preprocessing and Feature Extraction

- Images are resized to a fixed size (e.g., 128×128) and converted to grayscale.
- Features are extracted using:
  - **Histogram of Oriented Gradients (HOG)**: to capture the shape and edge information of signs.
  - Optionally, raw pixel intensities are flattened as fallback features.

### 3. Dataset Split

- Training, validation, and test sets are defined via directory structure and matching annotation files:
  - `train/final_annotations.coco.json`
  - `valid/final_annotations.coco.json`
  - `test/final_annotations.coco.json`

### 4. Model Training

Two classical ML models are trained and evaluated:

- **Random Forest Classifier**
- **Support Vector Machine (SVM)** with default kernel (linear/RBF)

The models are trained on extracted HOG features, then evaluated on validation and test sets.

### 5. Evaluation

- Accuracy is computed for both validation and test sets.
- Confusion matrices and prediction results are visualized using matplotlib.
- The model with best performance is used to test on unknown samples (`BienBaoLe/`).

### 6. Inference on Unknown Signs

- A small set of "unseen" traffic signs is used to simulate real-world generalization.
- Predictions and confidence scores are visualized.

--- 

## 🚀 How to Run

1. Clone this repo:
```bash
git clone https://github.com/KonnMjn/CS231-TrafficSign-Recognition.git
cd CS231-TrafficSign-Recognition
```
2. Download the original dataset from Kaggle and place it under a folder like Vietnam-Traffic-Sign-Detection/

3. Copy and merge images from Additional-Data/ to the corresponding folders. Using the *.json files from the Additional-Data/ instead of those from the original dataset.

4. Open and run main.ipynb.
---

## 📌 Notes
This repo includes only manually added data and annotations.

Original dataset must be downloaded from Kaggle.

Make sure to update paths in main.ipynb if using different folder structures.

--- 

## 📄 License
This project is for educational purposes. The dataset is attributed to the original Kaggle author and Roboflow annotations were created by the project team.

---

## 👨‍🏫 Credits

Phạm Đông Hưng – 22520521

Phan Công Minh - 22520884

Instructor: TS. Mai Tiến Dũng

---
