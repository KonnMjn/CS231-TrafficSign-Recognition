# 🚦 CS231 - Traffic Sign Recognition

This project focuses on classifying Vietnamese traffic signs using computer vision.

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
│ ├── dev/
│ │ ├── *.jpg
│ │ └── final_annotations.coco.json
│ └── test/
│ │ ├── *.jpg
│ │ └── final_annotations.coco.json
├── BienBaoLe/ # Unseen data for model to predict
│   ├── *.jpg
│   └── _annotations.coco.json
```

## 📌 Table of Contents

- [Dataset](#dataset)
- [Methodology](#methodology)
- [Installation](#installation)
- [How to Run](#how-to-run)
- [Credits](#credits)

---

## 📦 Dataset

We used the publicly available [Vietnam Traffic Sign Detection Dataset from Kaggle](https://www.kaggle.com/datasets/lvnduy/street-traffic-signs-in-vietnam-coco/data) as the base dataset.

However, the original annotations were **incomplete** for our use case, so we manually:

- Labeled additional images using [Roboflow](https://roboflow.com/)
- Modified COCO annotation files for `train`, `dev`, and `test` sets
- Stored the additional data in the `Additional-Data/` directory

> ✅ You should use the annotation files in `Additional-Data/` instead of those from the original Kaggle dataset.

---

## 🚀 How to Run

1. Clone this repo:
```bash
git clone https://github.com/KonnMjn/CS231-TrafficSign-Recognition.git
cd CS231-TrafficSign-Recognition
2. Download the original dataset from Kaggle and place it under a folder like Vietnam-Traffic-Sign-Detection/

3. Copy and merge images from Additional-Data/ to the corresponding folders. Using the *.json files from the Additional-Data/ instead of those from the original dataset.

4. Open and run main.ipynb.
```
