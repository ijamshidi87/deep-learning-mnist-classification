Name: Iman Jamshidi
Homework 2
-------------------------------------------------------------
1. Overview

This project trains and evaluates four deep learning models (DNN, CNN, VGG, and ResNet) on the MNIST handwritten digits dataset.
All models are implemented in PyTorch and trained with three different learning rates (0.1, 0.01, 0.001).
Each model outputs validation and test performance (accuracy, F1, and AUC) along with training plots and screenshots.
----------------------------------------------------------------------------------------
Important Note

For every model and experiment, both .py and .ipynb versions are provided.
The .py files are the Python scripts, and the .ipynb files are the Google Colab notebooks used to run the same code interactively.
All .ipynb and .py files and all results for every model and for all different learning rates are included in the extra_files folder.
-----------------------------------------------------------------------------------------------------------
2. File Name               Description
--------------------------------------------------------------
train.ipynb               Main training script for all models.
                          You can select which model to train
                          and the learning rate.
 
dnn_model.py              Defines the DNN architecture.

cnn_model.py              Defines the CNN architecture.
 
vgg_model.py              Defines the VGG architecture.

resnet_model.py           Defines the ResNet architecture.

test_evaluation.ipynb     Loads each saved model and evaluates
                          it on the MNIST test dataset (Accuracy,
                          F1, and AUC).

visualize_features.ipynb   Loads the best-performing model (VGG)
                          and generates the ROC–AUC curve and
                          feature map visualizations.

VGG_best_model.pth        Saved weight file of the best-performing
                          model (VGG with learning rate = 0.001).
----------------------------------------------------------------------
3. How to Train a Model

Open Google Colab and upload the file train.ipynb.

Run the notebook cells in order.
When the cell asks to upload files, upload the following four model files:
dnn_model.py
cnn_model.py
vgg_model.py
resnet_model.py

After uploading, select which model you want to train by editing the line:

MODEL_NAME = "cnn"      # options: "dnn", "cnn", "vgg", "resnet"

You can also change the learning rate by modifying:


LR = 1e-3               # choose 1e-1, 1e-2, or 1e-3

Then run the training cell.

After training completes, a results folder (for example results_cnn/) will be created automatically.
This folder includes:

best_model.pth (saved weights)

training plots for loss, accuracy, F1, and AUC

and a .zip file containing all results.
-------------------------------------------------------------------------------
4. How to Evaluate Models
Open Google Colab and upload the notebook test_evaluation.ipynb.

Run the notebook cells one by one.
When the second cell asks you to upload files, upload the best_model.pth files for each model:

best_model_dnn.pth
best_model_cnn.pth
best_model_vgg.pth
best_model_resnet.pth


After that, run the remaining cells.
Each cell will evaluate the corresponding model and show its Accuracy, F1, and AUC results in the output.
-------------------------------------------------------------------------------------
5. How to Visualize the Best Model

Open Google Colab and upload the notebook visualize_features.ipynb.

When the notebook asks to upload files, upload the following two files:

vgg_model.py        (from the code folder)
VGG_best_model.pth  (from the weights folder)


Make sure both files are in the same directory inside Colab.

Then run the notebook cells.
The notebook will generate and display:

vgg_feature_maps.png — visualization of the first and second convolutional layer features

vgg_roc_curve.png — ROC–AUC curve for several digit classes
-------------------------------------------------------------------------------------------------------------
Extra Files

An additional folder named extra_files is included in this submission.
This folder contains the output results (plots, logs, and training summaries) for each model and each learning rate, along with the Python code files used to generate them.

