# Plant Disease Classification with AlexNet

An image classification project that uses **AlexNet** to classify plant leaf images into four disease and health categories.

The project compares a baseline AlexNet architecture with a modified version that applies additional normalization and regularization techniques.

## Classes

The model classifies images into four categories:

- `Gray_Leaf_Spot`
- `Common_Rust`
- `Blight`
- `Healthy`

The dataset contains **4,188 images** distributed across the four classes:

| Class | Images |
|---|---:|
| Gray_Leaf_Spot | 574 |
| Common_Rust | 1,306 |
| Blight | 1,146 |
| Healthy | 1,162 |

## Workflow

1. Explore the image dataset
2. Analyze class distribution
3. Split images into training, validation, and test sets
4. Prepare image transformations
5. Train a baseline AlexNet
6. Train a modified AlexNet
7. Compare training and validation loss
8. Evaluate both models on the test set

The dataset is split using a 70:15:15 train-validation-test ratio.

## Baseline AlexNet

The baseline model implements an AlexNet-style convolutional neural network with:

- Convolutional layers
- ReLU activation
- Max pooling
- Fully connected layers
- Dropout in the classifier

## Modified AlexNet

The modified architecture adds:

- Batch Normalization after convolution layers
- Additional Dropout
- Smaller learning rate (`0.00005`)
- Weight decay (`1e-4`) for L2 regularization

These modifications are intended to improve training stability and reduce the risk of overfitting.

## Results

The models are evaluated using macro-averaged:

- Accuracy
- Precision
- Recall
- F1 Score

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Baseline AlexNet | **91.27%** | 89.35% | **89.72%** | **89.52%** |
| Modified AlexNet | 90.79% | **91.06%** | 87.47% | 88.54% |

The baseline model achieved higher accuracy, recall, and F1 score, while the modified model achieved higher precision.

## Future Improvements

- Apply stronger data augmentation
- Tune learning rate and regularization parameters
- Address class imbalance
- Evaluate additional CNN architectures
- Add a confusion matrix and per-class performance analysis
