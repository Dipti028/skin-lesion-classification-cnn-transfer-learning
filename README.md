# Skin Lesion Classification using Custom CNN & Transfer Learning (EfficientNetB0)

---

## 📖 Table of Contents
- [General Information](#-general-information)
- [Dataset](#-dataset)
- [Model Evolution](#-model-evolution)
- [Technologies](#-technologies)
- [Key Techniques](#-key-techniques)
- [Key Findings](#-key-findings)
- [Limitations](#-limitations)
---

## 🧠 General Information  

Skin lesions, particularly **melanoma**, are among the deadliest forms of skin cancer, contributing to nearly **75% of related deaths**. Early and accurate detection is crucial for improving patient outcomes.

This project builds a **multiclass deep learning model** to classify melanoma and **8 other skin lesion types** using dermoscopic images.

The solution combines:
- A **custom CNN** for baseline learning  
- **Transfer Learning (EfficientNetB0)** for improved feature extraction  

---

## 📊 Dataset  

- **Source:** ISIC (International Skin Imaging Collaboration)
- **Link:** https://www.kaggle.com/datasets/nodoubttome/skin-cancer9-classesisic  
- **Images:** 2239 training + 118 test  
- **Classes:** 9 skin conditions  

**Categories include:**
- Actinic Keratosis  
- Basal Cell Carcinoma  
- Dermatofibroma  
- Melanoma  
- Nevus  
- Pigmented Benign Keratosis  
- Seborrheic Keratosis  
- Squamous Cell Carcinoma  
- Vascular Lesion  

---

## ⚙️ Model Evolution  

| Phase | Model                          | Val Acc | Test Acc | Key Insight |
|------|--------------------------------|--------|---------|------------|
| 1 | Baseline CNN | 57% | — | Severe Overfitting (gap 29%) |
| 2 | CNN + Augmentation | 54% | — | Underfitting |
| 3 | CNN + Balanced Data | 71% | 45% | Better generalization |
| 4 | EfficientNetB0 (Frozen) | 62% | — | Underfitting |
| 5 | EfficientNetB0 (Fine-tuned) | 74% | — | Slight overfitting |
| 6 | EfficientNetB0 + Callbacks | 78% | — | Stabilized training |
| 7 | EfficientNetB0 + Class Weights | **79%** | **51%** | Best Trade-Off ✅ |

---

## ⚙️ Technologies  

- Python 3.10  
- TensorFlow / Keras  
- EfficientNetB0 (Transfer Learning)  
- Augmentor (Class Balancing)  
- Scikit-learn (Evaluation)  
- Matplotlib / Seaborn (Visualization)  
- Kaggle GPU (Tesla T4 x2)  

---

## 🧠 Key Techniques  

- CNN with **Dropout & Batch Normalization**  
- **Data Augmentation** (Flip, Rotation, Zoom)  
- **Transfer Learning** (EfficientNetB0 pretrained on ImageNet)  
- **Fine-tuning** (top layers unfrozen)  
- **Callbacks** (EarlyStopping, ReduceLROnPlateau, ModelCheckpoint)  
- **Class Weights** for imbalance handling  

---

## 🔍 Key Findings  

- Transfer learning significantly improved performance over baseline CNN  
- Class imbalance was the primary challenge  
- High AUC scores indicate good class separability  
- Melanoma classification remains difficult and needs improvement  

---

## ⚠️ Limitations  

- Small test dataset (118 images)  
- Lower recall for melanoma (clinically critical)  
- No external validation dataset  

---

## 👩‍💻 Author  

**Dipti**  
🔗 GitHub: https://github.com/Dipti028  
