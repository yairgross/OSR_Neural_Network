# Open Set Recognition (OSR) for Image Classification using MNIST

## Introduction
Open Set Recognition (OSR) in image classification involves recognizing known classes while identifying instances from previously unseen classes during test time. This project focuses on implementing OSR for the MNIST dataset by trainig a Nural Network.

## Data and Preprocessing
We preprocess the MNIST and Out-of-Distribution (OOD) datasets using various transformations, including normalization, data augmentation, and incorporating the CIFAR-10 dataset as OOD data.


## Models
Three classes of image classification models are defined:

**Autoencoder**: Implements an autoencoder architecture for image reconstruction.

**ML-autoencoder**: Extends the autoencoder by adding a classification head for multi-label classification.

**ML-autoencoder-OSR:** Designed specifically for Open Set Recognition, this model introduces parameters to handle uncertainty thresholds during classification.


## Training
The training phase involves training a multi-task autoencoder model for image reconstruction and multi-label classification on the MNIST dataset. We evaluate the model's performance on a validation set to compute mean entropy and reconstruction loss.


## Evaluation
Our approach to Open Set Recognition involves:

Using a multi-task autoencoder for reconstruction and classification tasks.

Estimating uncertainty by calculating the entropy of predictions.

Monitoring reconstruction loss.

Incorporating dropout layers and data augmentations for robustness.

### Baseline Results
We evaluate the trained model's performance on the MNIST test set by calculating accuracy and recording predicted vs. true labels.

Baseline accuracy for the base model: 95.93%

Baseline accuracy for the OSR model: 95.71%

### OOD Results
In Out-of-Distribution (OOD) results evaluation, we assess model performance on both MNIST and OOD datasets separately. We calculate binary classification accuracy for both categories and visualize a confusion matrix to analyze the model's performance.

MNIST accuracy: 95.71%

OOD accuracy: 90.80%


### OSR Results
The OSR evaluation tests the model on data outside its training scope, including unseen classes and substantially different data. We measure Total Accuracy to evaluate the model's ability to distinguish between known and unknown samples.

Total accuracy: 95.26%

### Final Results
In the final test, the model was evaluated using an OOD dataset which was not accessible in any phase of training and testing.

The final OSR Score: 97.71%
