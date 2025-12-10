# DenseNet-121 Histopathology Image Classification  
Computer Vision Assignment — MinHwan Noh (Student ID: 2022113600)

This project implements a DenseNet-121 model to classify four types of histopathology tissue images from the **POC_Dataset**.


Classes:
- Chorionic_villi  
- Decidual_tissue  
- Hemorrhage  
- Trophoblastic_tissue  

## 🧠 Model
- Pretrained **DenseNet-121 (ImageNet)**
- Final classifier modified for 4 classes  
- Input size: 224×224  
- Loss: CrossEntropyLoss  
- Optimizer: Adam (lr=1e-4)

## 🚀 Training & Evaluation
- 20% of training data used as validation  
- Best model saved as `best_densenet.pth`  
- Final evaluation on Testing set (accuracy + classification report)

