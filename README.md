# Deep Neural Networks for Crop Disease Detection and Interpretability (XAI)

## 📘 Subject  
**Computer Vision in Disease Visualization (CVDV)**

## 👨‍💻 Project Members  
- **Vatsal Mishra (229311186)**  
- **Kumar Ankit (229311200)**  
- **Ayan Mishra (229311193)**  
- **Mudit Srivastava (229311288)**

---

## 📚 1. Dataset Overview

The dataset contains images of four major crop species and their diseases. Each species includes multiple disease categories along with a healthy class.  
Total classes: **14**  
Total images: **13,024**

### 🌽 A. Corn
- **Common Rust** – 1,192  
- **Gray Leaf Spot** – 513  
- **Northern Leaf Blight** – 985  
- **Healthy** – 1,162  
**Total:** 3,852 images  
**Source:** PlantVillage  

### 🥔 B. Potato
- **Early Blight** – 1,000  
- **Late Blight** – 1,000  
- **Healthy** – 152  
**Total:** 2,152 images  
**Source:** PlantVillage  

### 🌾 C. Rice
- **Brown Spot** – 613  
- **Leaf Blast** – 977  
- **Neck Blast** – 1,000  
- **Healthy** – 1,488  
**Total:** 4,078 images  
**Sources:** Dhan-Shomadhan, Kaggle Rice Leafs  

### 🌱 D. Wheat
- **Brown Rust** – 902  
- **Yellow Rust** – 924  
- **Healthy** – 1,116  
**Total:** 2,942 images  
**Source:** Kaggle  

---

## 🧠 2. Methodology  

![Methodology](Images/PRMeth.png)

This project uses deep CNN-based classification combined with Explainable AI (XAI) to detect plant diseases and visualize model reasoning.

The pipeline consists of:
1. Input processing  
2. Image preprocessing  
3. Feature extraction  
4. Model training  
5. Evaluation  
6. Explainability using XAI  

---

## 🖼️ A. Input Image Processing

Since the dataset was not pre-split, we manually divided it into:

- **Training:** 70%  
- **Testing:** 20%  
- **Validation:** 10%  

### Batch Size  
**32**

---

## 🧹 B. Image Preprocessing  

To standardize and improve model generalization:

- Resize: **299 × 299 × 3**  
- Pixel scaling: **0 to 1**  
- **Data Augmentation:**  
  - Color Jitter  
  - Random Horizontal/Vertical Flip  
  - Random Height/Width shift  
  - Random Rotation  
  - Random Zoom  

These transformations introduce diversity and reduce overfitting.

---

## 🏗️ C. Feature Extraction (Transfer Learning)

We used **transfer learning** with three pretrained CNN models:

- **InceptionV3**  
- **VGG19**  
- **Xception**

These models help capture texture, shape, and color patterns important for plant disease recognition.

### Training Parameters
- **Batch Size:** 32  
- **Iterations:** 30,000  
- **Learning Rate:** 1e-4  
- **Epochs:** ~105  
- **Optimizer:** Adam  
- **Loss Function:** Categorical Cross-Entropy  
- **Early Stopping:** Enabled  

All models were trained using the same hyperparameter settings for fair comparison.

---

## 📊 D. Model Evaluation

We used the following performance metrics:

- **Accuracy**  
- **Precision (P)**  
- **Recall (R)**  
- **Weighted F1-Score**  
- **Misclassification Rate**

The **weighted F1-score** is emphasized due to class imbalance.

---

## 🔍 E. Explainable AI (XAI)

![XAI](Images/XAI_ORIGINAL1.png)  
![XAI Heatmap](Images/XAI.png)

We applied **Grad-CAM (Gradient-weighted Class Activation Mapping)** to visualize what regions of the image the model focuses on while predicting.

### Key Observations
- The model successfully highlights disease-affected regions.
- Model attention aligns with biologically relevant leaf areas.
- Confirms the model is learning true disease patterns, not noise.

---

## ✅ Conclusion

This project integrates **Deep Neural Networks** with **Explainable AI** to build a transparent and reliable crop disease detection system.

Key achievements:
- High-accuracy classification  
- Strong model generalization  
- Visual interpretability using Grad-CAM  
- Works across 4 major plant species  

---

## 📂 Folder Structure (Optional)

├── Images/
│ ├── PRMeth.png
│ ├── XAI.png
│ └── XAI_ORIGINAL1.png
├── src/
├── models/
├── notebooks/
└── README.md
