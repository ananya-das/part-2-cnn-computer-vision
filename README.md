# part-2-cnn-computer-vision
Bitsom Ananya Das assignment for: part-2-cnn-computer-vision

## Problem Statement

The goal of this project is to build a Convolutional Neural Network (CNN)
that can classify product surface images into one of four categories:

- normal
- scratch
- dent
- stain

## Dataset Link: https://drive.google.com/drive/folders/17xoSIAe-24-18iJiN3zKPqJl-RNDqIeW

## Task 1: Problem Identification:
This is an Image Classification problem.

Reason:
- Each image belongs to one category only.
- The goal is to predict a single label for the entire image.
- We are not locating objects or segmenting pixels.

## Task 2: Dataset Exploration
Dataset exploration was performed to better understand the data.

Steps Performed:
1. Class Identification: The dataset folders were scanned to identify all available classes.

2. Image Count Per Class: The number of images inside each class folder was counted to analyze dataset distribution and imbalance.

3. Sample Visualization: Sample images from each class were displayed using Matplotlib.

4. Image Dimension Analysis: Image sizes were inspected to understand whether resizing was needed.

5. Dataset Imbalance Check: Bar plots were created to visualize the number of samples in each class.

## Task 3: Task 3: Image Preprocessing
Some of the pre-processing steps applied: 

1. Image Resizing: All images were resized to 128 × 128
This ensures consistent input dimensions for the CNN.

2. Pixel Normalization: Pixel values were scaled from: 0–255 → 0–1
This improves model convergence and stability.

3. Data Splitting: The dataset was divided into: Training set and Validation set using TensorFlow ImageDataGenerator.

4. Data Augmentation: Data augmentation techniques were applied:
Rotation
Zoom
Horizontal flipping

This improves model generalization and reduces overfitting.

## Task 4: CNN Model Creation
A Convolutional Neural Network (CNN) was built using TensorFlow/Keras.

### Model Architecture
The CNN contains:
- Convolution Layers: Used to extract image features such as: edges, textures, scratches, dents
- Activation Function (ReLU): ReLU introduces non-linearity and improves learning efficiency.
- Pooling Layers: MaxPooling layers reduce feature map dimensions while preserving important information.
- Flatten Layer: Converts 2D feature maps into a 1D vector.
- Dense Layers: Used for classification learning.
- Output Layer: Contains 4 neurons corresponding to the four defect classes.
- Softmax activation was used for multi-class classification.

## Task 5: Model Training and Evaluation
The CNN model was trained using the training dataset and validated using the validation dataset.

Training Details: 
  Optimizer: Adam
  Loss Function: Categorical Crossentropy
  Epochs: 15
### Evaluation Metrics: 
The following metrics were analyzed:

1. Training Accuracy and Loss: Accuracy and loss curves were generated to monitor model learning.
Saved in: results/accuracy_loss_curves.png

3. Validation Performance: Validation accuracy and validation loss were evaluated during training.

4. Confusion Matrix: A confusion matrix was generated to analyze classification performance for each class.
Saved in: results/confusion_matrix.png

5. Sample Predictions: Predictions on validation images were visualized.
Saved in:
sample_predictions/prediction_outputs.png

## Task 6: CNN Concept Explanation

### What is Convolution?

Convolution is an operation where small filters slide over the image
to detect patterns like edges, scratches, textures, and shapes.

### Why is Pooling Used?

Pooling reduces image size while keeping important information.
This helps reduce computation and overfitting.

### Why is ReLU Used?

ReLU activation helps the network learn non-linear patterns efficiently.

:contentReference[oaicite:0]{index=0}

### Why are CNNs Better for Images?

CNNs preserve spatial relationships in images and automatically learn
important visual features.

## Task 7:Business Use Case Mapping

## Business Use Case

This CNN-based defect detection system can be used in manufacturing quality inspection.

Applications:
- Detect scratches on metal surfaces
- Detect dents in automotive components
- Detect stains on packaging materials
- Automate visual inspection systems

Benefits:
- Faster inspection
- Reduced manual effort
- Improved product quality
- Reduced manufacturing defects
