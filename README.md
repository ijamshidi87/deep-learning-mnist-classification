# MNIST Handwritten Digit Classification

**Course**: Deep Learning — Homework 2  
**Instructor**: Professor Jun Bai  
**Author**: Iman Jamshidi  

## Overview

This project implements and compares four deep learning architectures — DNN, CNN, VGG, and ResNet — on the MNIST handwritten digit classification task using PyTorch. Each model was trained with three different learning rates (0.1, 0.01, 0.001) and evaluated using Accuracy, F1, and AUC metrics.

## Dataset

- **MNIST**: 70,000 grayscale images (28×28) of handwritten digits (0–9)
- **Split**: 50,000 train / 10,000 validation / 10,000 test
- **Preprocessing**: normalized to [-1, 1], shuffled each epoch

## Models & Results

| Model | Best Accuracy (%) | Best F1 | Best AUC |
|---|---|---|---|
| DNN | 97.16 | 0.970 | 0.999 |
| CNN | 99.05 | 0.987 | 0.9998 |
| **VGG** | **99.26** ✅ | **0.9927** | **0.9999** |
| ResNet | 80.71 | 0.992 | 0.9999 |

Best model: **VGG** with Adam optimizer (LR = 0.001)

## Key Findings

- Learning rate of 0.001 gave the best and most stable results across all models
- At LR = 0.1, CNN and VGG completely failed to converge (F1 ≈ 0.10)
- VGG achieved near-perfect ROC curves for all 10 digit classes (AUC ≈ 1.000)
- ResNet showed overfitting — high training accuracy but unstable validation curves
- Dropout and batch normalization were applied to all models to reduce overfitting

## Files

| File | Description |
|---|---|
| `train.ipynb` | Main training notebook — select model and learning rate |
| `dnn_model.py` | DNN architecture |
| `cnn_model.py` | CNN architecture |
| `vgg_model.py` | VGG architecture |
| `resnet_model.py` | ResNet architecture |
| `test_model.ipynb` | Evaluates all saved models (Accuracy, F1, AUC) |
| `visualize_features.ipynb` | ROC curve and feature map visualization for VGG |
| `VGG_best_model.pth` | Saved weights of the best model |
| `Iman_Jamshidi_HW2_Report.pdf` | Full written report |

## How to Run

### Train a model
1. Open `train.ipynb` in Google Colab
2. Upload the four model `.py` files when prompted
3. Set the model and learning rate:
```python
MODEL_NAME = "vgg"   # options: "dnn", "cnn", "vgg", "resnet"
LR = 1e-3            # options: 1e-1, 1e-2, 1e-3
```
4. Run all cells — results and weights are saved automatically

### Evaluate models
1. Open `test_model.ipynb` in Google Colab
2. Upload `best_model_dnn.pth`, `best_model_cnn.pth`, `best_model_vgg.pth`, `best_model_resnet.pth`
3. Run all cells to see Accuracy, F1, and AUC per model

### Visualize VGG features
1. Open `visualize_features.ipynb` in Google Colab
2. Upload `vgg_model.py` and `VGG_best_model.pth`
3. Run all cells to generate ROC curve and convolutional feature maps

## Requirements
```bash
pip install torch torchvision scikit-learn matplotlib numpy
```
