Tomato Leaf Disease Classification
📊 Dataset Description

The PlantVillage dataset consists of leaf images from multiple crop species, including Tomato, Potato, and Pepper. For this project, only Tomato leaf classes were considered.

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

Other crop categories in the dataset were excluded from the analysis.

🔍 Exploratory Data Analysis (EDA) Overview

The EDA was carried out to understand the characteristics and quality of the dataset before model training. The following analyses were performed:

1️⃣ Class Balance Analysis

Computed the number of images per tomato class.

Visualized class distribution using bar charts.

Identified moderate class imbalance, which may introduce bias during training.

2️⃣ Sample Image Visualization

Displayed representative images from each class.

Observed clear intra-class consistency and inter-class variation.

Images are visually clean with minimal background noise.

3️⃣ Image Resolution and Aspect Ratio Analysis

Verified all images have a uniform resolution of 256 × 256 pixels.

Aspect ratio analysis confirmed all images are square (ratio ≈ 1.0).

Ensures resizing can be safely applied without geometric distortion.

4️⃣ Color Distribution Analysis

Analyzed RGB channel distributions from representative images.

Observed dominance of the green channel, consistent with natural leaf pigmentation.

Dataset is color-rich rather than grayscale.

5️⃣ Data Augmentation Probe

Augmentation	Observation	Verdict
Horizontal Flip	Preserves disease patterns	Safe
Random Crop (mild)	Retains most disease regions	Mostly Safe
Color Jitter	Simulates lighting variation	Safe
Aggressive Rotation	Unrealistic leaf orientation	Avoided

This analysis guided safe augmentation choices during model training.

🏋️‍♂️ Model Training & Evaluation

Three deep learning architectures were evaluated for classifying tomato leaf diseases:

ResNet50

VGG16

EfficientNetB0

Evaluation Metrics:

Accuracy

Precision (macro)

Recall (macro)

F1-score (macro)

AUC (macro)

Training & Testing Time

Comparison Table:

Model	Accuracy	Precision	Recall	F1-score	AUC	Training Time	Testing Time
ResNet50	99.44%	99.37%	99.35%	99.36%	1.000	~42.5 min	17.22 sec
VGG16	95.47%	95.01%	95.16%	94.85%	0.9992	~90 min	28.70 sec
EfficientNetB0	99.60%	99.63%	99.53%	99.58%	1.000	~29 min	9.29 sec

Observations:

ResNet50 and EfficientNetB0 achieve excellent accuracy (>99%).

EfficientNetB0 converges faster with the shortest training and testing times, making it highly efficient.

VGG16 performs moderately well but is slower and less accurate.

All models exhibit strong discriminative ability with AUC values near 1.0.

Conclusion:
EfficientNetB0 provides the best trade-off between accuracy and computational efficiency, followed closely by ResNet50. VGG16, while capable, is less suitable for real-time or large-scale deployment.

🛠️ Tools and Libraries Used

Python

NumPy, Pandas – Data manipulation

Matplotlib, Seaborn – Visualization

PIL (Python Imaging Library) – Image processing

Torch, Torchvision – Deep learning and data augmentation                                                                  @Md. Rejaul Hoq
