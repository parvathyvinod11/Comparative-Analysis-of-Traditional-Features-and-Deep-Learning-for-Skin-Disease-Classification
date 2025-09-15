**Comparative Analysis of Traditional Features and Deep Learning for Skin Disease Classification**


📌 **Project Overview**

This project explores skin disease classification using the ISIC-2019 dataset, comparing:

Traditional handcrafted feature extraction methods (HOG, LBP, Edge detection)

Deep learning approaches (ResNet50, VGG16, MobileNet)

The goal is to analyze accuracy, robustness, interpretability, and trade-offs between these techniques in medical image classification.


📂 **Dataset**

We used the ISIC-2019 dataset, containing 25,331 dermoscopic images across 8 clinically relevant categories:

Actinic Keratosis

Basal Cell Carcinoma

Benign Keratosis

Dermatofibroma

Melanocytic Nevus

Melanoma

Squamous Cell Carcinoma

Vascular Lesions

📎 **Dataset link**: ISIC 2019 – Kaggle


🛠️** Methodology**


🔹** Traditional Feature Extraction**

Preprocessing: Grayscale conversion, resizing (128×128), normalization

Techniques:

Histogram of Oriented Gradients (HOG)

Local Binary Patterns (LBP)

Edge Features (Canny-based)

Classifiers: Logistic Regression, KNN, Decision Tree, Random Forest

Evaluation Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC, Cohen’s Kappa, robustness under noise & perturbations

🔹 **Deep Learning Approach**

Base Models: Pretrained ResNet50, VGG16, MobileNet (transfer learning)

Preprocessing: Resize (224×224), normalization, augmentation (rotation, flips, zoom, contrast, Gaussian noise)

Architecture:

Frozen CNN backbone (ResNet50)

Global Average Pooling

Dense + Dropout layers

Softmax output (8 classes)

Training: Adam optimizer, Categorical Cross-Entropy, Early Stopping, ModelCheckpoint

Evaluation: Confusion Matrix, ROC–AUC, Cohen’s Kappa, Precision-Recall curves, Top-K accuracy, saliency maps

📊 **Results**
**
Traditional Methods**

Best Accuracy: 55% (HOG + Random Forest)

Best Fairness: HOG + KNN (Macro-F1 ≈ 0.22)

Robustness: HOG + Decision Tree most stable under noise

**Deep Learning (ResNet50)**

Test Accuracy: 66%

ROC–AUC: Micro = 0.94 | Macro = 0.88

Best Class Performance: Melanocytic Nevus (F1 = 0.82)

Challenges: Poor performance on minority classes (Dermatofibroma, Vascular Lesions)

📌** Key Insights**

✅ Traditional methods → Lightweight, interpretable, resource-friendly, but limited with complex lesion patterns.

✅ Deep learning methods → Higher accuracy & generalization, but require GPUs and large datasets.

✅ Hybrid approaches → Combining handcrafted + deep features improves robustness & interpretability.
