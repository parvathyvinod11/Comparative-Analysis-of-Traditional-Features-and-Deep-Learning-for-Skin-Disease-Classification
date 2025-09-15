**Comparative Analysis of Traditional Features and Deep Learning for Skin Disease Classification**


📌 **Project Overview**

This project explores skin disease classification using the ISIC-2019 dataset, comparing:

1. Traditional handcrafted feature extraction methods (HOG, LBP, Edge detection)

2. Deep learning approaches (ResNet50, VGG16, MobileNet)

3. The goal is to analyze accuracy, robustness, interpretability, and trade-offs between these techniques in medical image classification.


📂 **Dataset**


We used the ISIC-2019 dataset, containing 25,331 dermoscopic images across 8 clinically relevant categories:

1. Actinic Keratosis

2. Basal Cell Carcinoma

3. Benign Keratosis

4. Dermatofibroma

5. Melanocytic Nevus

6. Melanoma

7. Squamous Cell Carcinoma

8. Vascular Lesions

📎 **Dataset link**: https://www.kaggle.com/datasets/mdefajalam/isic-2019-skin-disease/data


🛠  **Methodology**


🔹 Traditional Feature Extraction 

Preprocessing: Grayscale conversion, resizing (128×128), normalization

Techniques:

a) Histogram of Oriented Gradients (HOG)

b) Local Binary Patterns (LBP)

c) Edge Features (Canny-based)

d) Classifiers: Logistic Regression, KNN, Decision Tree, Random Forest

e) Evaluation Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC, Cohen’s Kappa, robustness under noise & perturbations

🔹 Deep Learning Approach

a) Base Models: Pretrained ResNet50, VGG16, MobileNet (transfer learning)

b) Preprocessing: Resize (224×224), normalization, augmentation (rotation, flips, zoom, contrast, Gaussian noise)

c) Architecture:

Frozen CNN backbone (ResNet50)

Global Average Pooling

Dense + Dropout layers

Softmax output (8 classes)

d) Training: Adam optimizer, Categorical Cross-Entropy, Early Stopping, ModelCheckpoint

e) Evaluation: Confusion Matrix, ROC–AUC, Cohen’s Kappa, Precision-Recall curves, Top-K accuracy, saliency maps

📊  **Results**

Traditional Methods

Best Accuracy: 55% (HOG + Random Forest)

Best Fairness: HOG + KNN (Macro-F1 ≈ 0.22)

Robustness: HOG + Decision Tree most stable under noise

**Deep Learning (ResNet50)**

Test Accuracy: 66%

ROC–AUC: Micro = 0.94 | Macro = 0.88

Best Class Performance: Melanocytic Nevus (F1 = 0.82)

Challenges: Poor performance on minority classes (Dermatofibroma, Vascular Lesions)

📌  **Key Insights**

✅ Traditional methods → Lightweight, interpretable, resource-friendly, but limited with complex lesion patterns.

✅ Deep learning methods → Higher accuracy & generalization, but require GPUs and large datasets.

✅ Hybrid approaches → Combining handcrafted + deep features improves robustness & interpretability.
