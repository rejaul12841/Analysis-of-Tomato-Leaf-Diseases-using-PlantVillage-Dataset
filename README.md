📊 Dataset Description

The PlantVillage dataset consists of leaf images from multiple crop species, including Tomato, Potato, and Pepper.
For this task, only Tomato leaf classes were considered.

Tomato Classes Used:

Tomato_healthy

Tomato_Bacterial_spot

Tomato_Early_blight

Tomato_Late_blight

Tomato_Leaf_Mold

Tomato_Septoria_leaf_spot

Tomato_Spider_mites_Two_spotted_spider_mite

Tomato_Target_Spot

Tomato_Tomato_mosaic_virus

Tomato_Tomato_YellowLeaf_Curl_Virus

Although other crop categories exist in the dataset, they were excluded from the analysis.

🔍 Exploratory Data Analysis Overview

The EDA was carried out to understand the characteristics and quality of the dataset before model training.
The following analyses were performed:

1️⃣ Class Balance Analysis

Computed the number of images per tomato class.

Visualized class distribution using bar charts.

Identified moderate class imbalance, which may introduce bias during training.

2️⃣ Sample Image Visualization

Displayed sample images from each tomato disease class.

Observed clear intra-class consistency and inter-class variation.

Images are visually clean with minimal background noise.

3️⃣ Image Resolution and Aspect Ratio Analysis

Verified that all images have a uniform resolution of 256 × 256 pixels.

Aspect ratio analysis confirmed all images are square (ratio ≈ 1.0).

This ensures resizing can be safely applied without geometric distortion.

4️⃣ Color Distribution Analysis

Analyzed RGB color distributions from representative sample images.

Observed dominance of the green channel, consistent with natural leaf pigmentation.

Confirmed that the dataset is color-rich rather than grayscale.

5️⃣ Data Augmentation Probe

A small augmentation study was conducted to determine safe and harmful transformations:

Augmentation	Observation	Verdict
Horizontal Flip	Preserves disease patterns	Safe
Random Crop (mild)	Retains most disease regions	Mostly Safe
Color Jitter	Simulates lighting variation	Safe
Aggressive Rotation	Unrealistic leaf orientation	Avoided

This analysis helps justify the augmentation choices used in later tasks.

🛠️ Tools and Libraries Used

Python

NumPy

Pandas

Matplotlib

Seaborn

PIL (Python Imaging Library)

Torchvision (for augmentation probe)
