# DenseNet-Based Histology Image Classification

This repository contains my implementation of a **DenseNet-121 classifier** trained on a custom **POC histology dataset** as part of the **Computer Vision coursework**.

- **Student:** MinHwan Noh  
- **Student ID:** 2022113600  
- **Course:** Computer Vision Assignment  
- **Framework:** PyTorch  
- **Environment:** Google Colab (GPU: NVIDIA L4)

---

## 🚀 Project Overview
The goal of this assignment is to classify four types of histological tissue images using a **DenseNet-121** model pretrained on ImageNet.

### **Classification Targets**
- `Chorionic_villi`
- `Decidual_tissue`
- `Hemorrhage`
- `Trophoblastic_tissue`

The model is trained on the **POC_Dataset** and evaluated using accuracy metrics and a confusion matrix.

---

## 📁 Repository Structure
├── densenet_assignment.py # Full training + evaluation + visualization code
├── accuracy_curve.png # Test & train accuracy over epochs
├── loss_curve.png # Training loss curve
├── confusion_matrix.png # Final confusion matrix (test set)
└── README.md


---

## 🧠 Model Description
- **Model:** DenseNet-121  
- **Weights:** ImageNet pretrained  
- **Image Size:** 224 × 224  
- **Normalization:** ImageNet mean/std  
- **Loss:** CrossEntropyLoss  
- **Optimizer:** Adam (lr = 1e-4)

The final classifier layer is replaced with a fully connected layer matching the number of tissue classes.




