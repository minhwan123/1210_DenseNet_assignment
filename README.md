🧬 DenseNet-Based Histology Image Classification

This repository contains an implementation of a DenseNet-121 classifier trained on a custom POC histology dataset as part of a Computer Vision assignment.

Student: MinHwan Noh

Student ID: 2022113600

Course: Computer Vision

Framework: PyTorch

Environment: Google Colab (GPU: NVIDIA T4 / CUDA)

🚀 Project Overview

The goal of this project is to classify four types of histological tissue images using a DenseNet-121 model pretrained on ImageNet and fine-tuned on the POC dataset.

Tissue Classes

Chorionic_villi

Decidual_tissue

Hemorrhage

Trophoblastic_tissue

This dataset contains real histological images organized into class-specific folders.

📁 Dataset Structure & Splitting

The dataset is stored in Google Drive at:

/content/drive/MyDrive/POC_Dataset


Folder structure:

POC_Dataset/
├── Training/
│   ├── Chorionic_villi/
│   ├── Decidual_tissue/
│   ├── Hemorrhage/
│   └── Trophoblastic_tissue/
└── Testing/
    ├── Chorionic_villi/
    ├── Decidual_tissue/
    ├── Hemorrhage/
    └── Trophoblastic_tissue/

Train / Validation / Test Split

The Training/ folder is loaded first.

Then split randomly into:

Train: 80%

Validation: 20%

The Testing/ folder is used only for final performance evaluation.

Splitting is implemented using:

random_split(full_train_dataset, [train_size, val_size])

🧠 Model Description

This project uses DenseNet-121 from torchvision.models:

Backbone: DenseNet-121

Weights: ImageNet pretrained

Modified classifier:
Last layer → nn.Linear(in_features, 4) for four classes

Image Preprocessing

Resize to 224×224

Convert to tensor

Normalize with ImageNet mean/std:

mean = [0.485, 0.456, 0.406]
std  = [0.229, 0.224, 0.225]

🎨 Data Augmentation (Training Only)

To improve generalization, the following augmentations are used:

Random horizontal flip

Random vertical flip

Random rotation (±15°)

Color jitter (brightness/contrast/saturation/hue)

Validation and test images are not augmented.

⚙️ Training Configuration

Optimizer: Adam

LR = 1e-4

Weight decay = 1e-4 (L2 regularization)

Loss: CrossEntropyLoss

Epochs: 30

Batch size: 32

Device: CUDA (T4 GPU) if available

Best model saving:
Saved automatically when validation accuracy improves
→ best_densenet.pth
