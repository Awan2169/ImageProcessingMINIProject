# 📌 CGI vs Photographic Image Classification using Image Processing

## 📖 Overview

This project focuses on distinguishing **Computer Generated Images (CGI)** from **Photographic Images (PI)** using **pure image processing techniques**.

Instead of relying on deep learning, the system extracts **handcrafted features** such as texture, noise, edges, and frequency characteristics, and compares:

* A **rule-based classifier**
* A **machine learning model trained on extracted features**

---

## 🎯 Objectives

* Extract meaningful **image processing features**
* Design a **rule-based classification system**
* Train **machine learning models** using the same features
* Compare performance between both approaches
* Demonstrate importance of **feature engineering**

---

## 🧠 Key Concept

Real-world images contain:

* Natural noise
* Irregular textures
* Soft edges

Whereas CGI images exhibit:

* Smooth textures
* Clean surfaces
* Sharp edges

---

## 📂 Dataset

* Source: Kaggle dataset (CGI vs Real Images)
* Labels:

  * `0 → Photographic Image`
  * `1 → CGI Image`

---

## ⚙️ Methodology

### 1. Preprocessing

* Convert image to grayscale
* Normalize pixel values
* Resize (if needed)

---

### 2. Feature Extraction

The following **7 features** are extracted:

#### 🔹 Texture Feature

* Local Binary Pattern (LBP Mean)

#### 🔹 Noise Feature

* Standard Deviation of intensity

#### 🔹 Edge Features

* Edge Density (Canny)
* Edge Strength (Sobel Gradient)

#### 🔹 Color Feature

* RGB Variance

#### 🔹 Statistical Feature

* Entropy

#### 🔹 Frequency Feature

* FFT Energy

---

### 3. Feature Vector

Each image is represented as:

```
[lbp_mean, noise_std, edge_density, edge_strength, color_var, entropy, fft_energy]
```

---

## 🔍 Approach 1: Rule-Based Classification

A decision system is designed using thresholds:

```
if noise > threshold1 and edge_density < threshold2:
    classify as Real Image
else:
    classify as CGI
```

### Improved Version:

Weighted scoring system:

```
score = 0
if noise high: score += 1
if texture high: score += 1
if edges soft: score += 1

if score >= 2:
    Real Image
else:
    CGI
```

---

## 🤖 Approach 2: Machine Learning

Models used:

* Support Vector Machine (SVM)
* Random Forest
* Logistic Regression

### Steps:

1. Split dataset (train/test)
2. Train model on extracted features
3. Evaluate performance

---

## 📊 Evaluation Metrics

* Accuracy
* Precision
* Recall
* Confusion Matrix

---

## 📈 Visualization

For better understanding, the following are displayed:

* Original image
* LBP texture map
* Edge map (Canny)
* Gradient map (Sobel)
* Histogram (color distribution)
* FFT spectrum

---

## 🆚 Comparison

| Method     | Accuracy | Advantage             | Limitation        |
| ---------- | -------- | --------------------- | ----------------- |
| Rule-Based | Medium   | Simple, interpretable | Less accurate     |
| ML Models  | High     | Better performance    | Requires training |

---

## 💡 Key Insights

* Texture and noise are the most important features
* Rule-based systems are interpretable but less robust
* ML models perform better when trained on good features

---

## 🚀 Future Improvements

* Add more texture descriptors (GLCM)
* Use frequency band analysis
* Hybrid rule + ML model
* Extend to deep learning comparison

---

## 🛠️ Tools & Libraries

* Python
* OpenCV
* NumPy
* Scikit-image
* Scikit-learn
* Matplotlib

---

## 🧾 Conclusion

This project demonstrates that **image processing alone can effectively distinguish CGI from real images**, and combining it with machine learning improves performance significantly.

---

## 🗣️ Viva Explanation (Short)

“This project uses handcrafted image processing features like texture, noise, and edge characteristics to classify images as CGI or real, and compares rule-based classification with machine learning models.”

---
