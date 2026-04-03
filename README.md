
# 🌿 Tomato Leaf Disease Classification

## 📊 Dataset Description

This project focuses on classifying tomato leaf diseases using the PlantVillage Dataset.
Although the dataset contains multiple crops (Tomato, Potato, Pepper), only **Tomato leaf classes** were used in this study.

### 🍅 Tomato Classes Used

* Tomato_healthy
* Tomato_Bacterial_spot
* Tomato_Early_blight
* Tomato_Late_blight
* Tomato_Leaf_Mold
* Tomato_Septoria_leaf_spot
* Tomato_Spider_mites_Two_spotted_spider_mite
* Tomato__Target_Spot
* Tomato__Tomato_mosaic_virus
* Tomato__Tomato_YellowLeaf__Curl_Virus

All non-tomato categories were excluded to ensure domain-specific learning.

---

## 🔍 Exploratory Data Analysis (EDA)

EDA was performed to understand dataset characteristics before training.

### 1️⃣ Class Distribution

* Computed number of images per class
* Visualized distribution using bar charts
* Observed **moderate class imbalance**

---

### 2️⃣ Sample Visualization

* Displayed representative images per class
* Observed:

  * clear intra-class consistency
  * strong inter-class variation
* Images are clean with minimal background noise

---

### 3️⃣ Image Resolution & Aspect Ratio

* All images: **256 × 256 pixels**
* Aspect ratio ≈ **1.0 (square)**
  👉 Safe for resizing without distortion

---

### 4️⃣ Color Distribution

* RGB channel analysis performed
* Strong dominance of **green channel** (leaf pigmentation)
* Dataset is **color-rich**, not grayscale

---

### 5️⃣ Data Augmentation Strategy

| Augmentation        | Observation                  | Decision  |
| ------------------- | ---------------------------- | --------- |
| Horizontal Flip     | Preserves disease patterns   | ✅ Used    |
| Mild Random Crop    | Retains lesions              | ✅ Used    |
| Color Jitter        | Simulates lighting           | ✅ Used    |
| Aggressive Rotation | Unrealistic leaf orientation | ❌ Avoided |

---

## 🏗️ Models Implemented

### 🔹 Task 2 — Pre-trained Models

* ResNet50
* VGG16
* EfficientNetB0

---

### 🔹 Task 3 — Custom CNN

* Built from scratch
* Multiple convolution + pooling layers
* Batch Normalization + ReLU
* Dropout for regularization
* Class imbalance handled using weighted loss

---

### 🔹 Task 4 — Attention-Based CNN

* Custom CNN enhanced with **CBAM (Convolutional Block Attention Module)**
* Improves:

  * spatial attention
  * channel attention
* Helps model focus on disease-relevant regions

---

### 🔹 Task 5 — Explainability & Generalization

* Applied **Grad-CAM** for interpretability
* Evaluated model robustness on a **second tomato dataset**

---

## 📈 Evaluation Metrics

* Accuracy
* Precision (Macro)
* Recall (Macro)
* F1-score (Macro)
* AUC (Macro)
* Training Time
* Testing Time

---

## 📊 Model Performance Comparison

| Model               | Accuracy   | Precision | Recall | F1-score | AUC    | Training Time | Testing Time |
| ------------------- | ---------- | --------- | ------ | -------- | ------ | ------------- | ------------ |
| ResNet50            | 99.44%     | 99.37%    | 99.35% | 99.36%   | 1.000  | ~42.5 min     | 17.22 sec    |
| VGG16               | 95.47%     | 95.01%    | 95.16% | 94.85%   | 0.9992 | ~90 min       | 28.70 sec    |
| EfficientNetB0      | **99.60%** | 99.63%    | 99.53% | 99.58%   | 1.000  | ~29 min       | 9.29 sec     |
| Custom CNN          | 71.56%     | 74.10%    | 69.78% | 66.21%   | 0.9696 | ~21.6 min     | ~11 sec      |
| AttentionCNN + CBAM | 98.96%     | 98.70%    | 99.00% | 98.85%   | 0.9998 | ~37 min       | ~15 sec      |

---

## 🔍 Grad-CAM Analysis (Task 5)

Grad-CAM was used to visualize model attention:

* ✔️ Correct predictions → focus on **leaf & disease regions**
* ❌ Incorrect predictions → **misaligned or scattered attention**

👉 Insight:

> Model decisions depend strongly on spatial feature localization.

---

## 🌍 Generalizability Testing

Model retrained on a second tomato dataset:

| Dataset        | Accuracy | F1-score | AUC    |
| -------------- | -------- | -------- | ------ |
| PlantVillage   | 98.96%   | 0.9885   | 0.9998 |
| Second Dataset | 97.47%   | 0.9746   | 0.9993 |

### 🔍 Observation

* Small drop (~1.5%)
* Indicates **strong generalization capability**
* Minor domain shift due to:

  * background variation
  * lighting differences
  * dataset characteristics

---

## 🧠 Key Insights

* Pretrained models achieve highest accuracy
* Custom CNN provides baseline understanding
* Attention (CBAM) significantly improves performance
* Grad-CAM confirms meaningful feature learning
* Model generalizes well across datasets

---

## 🛠️ Tools & Libraries

* Python
* NumPy, Pandas
* Matplotlib, Seaborn
* PIL
* PyTorch, Torchvision

---

## 🏁 Conclusion

This project demonstrates that combining **deep learning with attention mechanisms and explainability techniques** leads to:

* High classification accuracy
* Improved interpretability
* Strong cross-dataset generalization

The AttentionCNN + CBAM model provides a powerful balance between performance and explainability, making it suitable for real-world plant disease detection systems.



@Md. Rejaul Hoq


