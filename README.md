# Geometric Shape Recognition: Feature Engineering vs. Deep Learning

![Author](https://img.shields.io/badge/Author-Adil%20CHOUKAIRE-blue)
![Python](https://img.shields.io/badge/Python-3.7+-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-Supported-F7931E)
![OpenCV](https://img.shields.io/badge/OpenCV-Supported-5C3EE8)

A machine learning pipeline comparing **traditional computer vision feature extraction** with **modern Convolutional Neural Networks (CNNs)** for the classification of **hand-drawn geometric shapes**.

---

# 📁 Project Structure

```bash
Geometric-Shape-Recognition/
├── data/
│   ├── train/
│   ├── val/
│   └── test/
├── notebooks/
│   ├── CNN.ipynb
│   └── Decision_tree.ipynb
├── requirements.txt
└── README.md
```

## 🚀 Installation & Usage

### Clone the repository

```bash
git clone https://github.com/your-username/Geometric-Shape-Recognition-Python-ML.git
cd Geometric-Shape-Recognition-Python-ML
```

### Install dependencies

```bash
pip install -r requirements.txt
```

## 🛠️ Scripts & Notebooks Description

### `notebooks/CNN.ipynb`

The **deep learning approach** leveraging **TensorFlow and Keras** to automate feature extraction.

#### Model Architecture
- Implements a **Sequential model**
- Two **Conv2D layers** (ReLU activation)
- **MaxPooling2D**
- **Dropout** for regularization

#### Data Processing
- Processes **grayscale 64×64 images**
- Uses **ImageDataGenerator** for efficient data loading and preprocessing

#### Evaluation
- Utilizes a **custom cost matrix** to compute a **weighted accuracy metric**

#### Performance
- Achieved **99.42% weighted accuracy** on the test set after **15 epochs**

---

### `notebooks/Decision_tree.ipynb`

The **traditional machine learning approach** relying on **manual feature engineering** and **ensemble learning**.

#### Data Augmentation
Includes a custom **OpenCV pipeline** to artificially expand the dataset with:

- Random rotations
- Scaling
- Translations
- Flips
- Noise injection

#### Feature Extraction
Uses **OpenCV** to compute geometric descriptors:

- Area
- Perimeter
- Circularity
- Aspect ratio
- Solidity
- Number of vertices

#### Model
- Trains a **RandomForestClassifier** (100 estimators) from **scikit-learn**

#### Performance
- Achieved **~75% accuracy**, highlighting the limitations of **manual geometric feature extraction** on noisy hand-drawn data.

---

## 🎯 Objective

The objective of this project is to **evaluate and compare two paradigms in computer vision**:

- Manual mathematical **feature engineering**
- Automated **hierarchical feature learning using deep learning**

By classifying **12,000 images into eight geometric categories**, the project demonstrates the **significant performance advantage of deep learning** for unstructured hand-drawn image data.

---

## ⚠️ Notes

- The dataset used for this project is hosted on **Kaggle: Geometric Shapes Mathematics**.

- Running `CNN.ipynb` may require **hardware acceleration** for reasonable training times:
  - NVIDIA GPU
  - Google Colab (**T4 / V100 recommended**)

- Both notebooks implement a **custom penalty/cost matrix** to evaluate predictions.  
  This ensures that confusing **similar shapes** (e.g., square vs rectangle) is penalized differently than confusing **very different shapes** (e.g., circle vs triangle).
