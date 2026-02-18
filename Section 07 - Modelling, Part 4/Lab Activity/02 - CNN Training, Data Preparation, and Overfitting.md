# CNN Training, Data Preparation, and Overfitting (MLS-C01 Exam Notes)

## Data Loading and Preparation
- MNIST dataset is commonly used for image classification demonstrations.
- Typical preprocessing steps:
  - Reshape raw pixel vectors into 2828x1 tensors for CNNs.
  - Cast to float32.
  - Normalize pixel values from 0–255 to 0–1.
  - One-hot encode labels for multi-class classification.
- MLS-C01 relevance:
  - Understand the importance of scaling and normalization for deep learning.
  - Understand one-hot encoding for classification problems.

## CNN Architecture Concepts
- Basic CNN structure used:
  - Convolution layers extract spatial features.
  - MaxPooling reduces spatial dimensions and helps prevent overfitting.
  - Flatten converts feature maps into a dense feature vector.
  - Dense layers perform classification.
- Deep learning qualifies as "deep" because it contains multiple layers.
- MLS-C01 relevance:
  - Know when CNNs are appropriate (image data).
  - Understand the purpose of convolution, pooling, and dense layers.

## Model Compilation
- Loss function for multi-class classification: categorical cross entropy.
- Optimizers:
  - Adam generally works well, widely used.
  - RMSProp is also common.
- Metric used: accuracy (dataset is balanced).
- MLS-C01 relevance:
  - Know which loss functions apply to which tasks.
  - Know common optimizers and when accuracy is an appropriate metric.

## Signs of Overfitting
- Training accuracy increases while validation accuracy stops improving or decreases.
- Model performs better on training data than unseen data.
- MLS-C01 relevance:
  - Identify overfitting by comparing training vs validation metrics.
  - Recognize that high training accuracy with lower validation accuracy = overfitting.

## Regularization to Reduce Overfitting
- Dropout:
  - Randomly disables neurons during training.
  - Forces the model to distribute learning, improving generalization.
  - Common in CNNs between convolutional or dense layers.
- Other methods (implicit in exam scope even if not shown here):
  - Early stopping
  - Weight decay (L2 regularization)
  - Data augmentation
- MLS-C01 relevance:
  - Dropout is a key technique tested frequently in MLS-C01 for preventing overfitting.
  - Understand the conceptual purpose of regularization methods.

## Training Configuration
- Batch size and epoch count influence training dynamics.
- Longer training without regularization tends to increase overfitting risk.
- MLS-C01 relevance:
  - Know that increasing epochs increases likelihood of overfitting.
  - Know that batch size affects model stability and convergence behavior.

``
