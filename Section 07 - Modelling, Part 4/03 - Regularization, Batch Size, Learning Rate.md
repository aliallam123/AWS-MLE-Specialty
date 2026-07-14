# Regularization, Batch Size, Learning Rate (MLS-C01 Exam Notes)

## Effect of Dropout on Overfitting
- Dropout improves model generalization by randomly disabling neurons during training.
- After adding dropout, validation accuracy improved from 99.07 percent to 99.23 percent.
- Training accuracy became slightly lower than validation accuracy, indicating reduced overfitting.
- Dropout increases training time because fewer active neurons are available per training step.
- Key exam idea: dropout is a regularization technique that prevents the network from memorizing training data and improves performance on unseen data.

## Effect of Batch Size
- Small batch sizes (e.g., 32) give more stable convergence and better generalization.
- Large batch sizes (e.g., 1000) can:
  - Increase training speed.
  - Produce worse validation accuracy (e.g., 99.06 percent).
  - Lead to getting stuck in local minima.
  - Produce inconsistent results between runs.
- Key exam idea: large batches reduce gradient noise and can cause convergence to poor local minima; small batches allow exploration and better generalization.

## Effect of Learning Rate
- Default Adam learning rate is 0.001.
- Increasing learning rate to 0.01 resulted in:
  - Poor validation accuracy (~98 percent).
  - Poor training accuracy (~95 percent).
  - Failure to converge correctly due to overshooting minima.
- Interaction with batch size:
  - Small batch size pairs best with small learning rate.
  - Large learning rates with small batches destabilize training.
- Key exam idea: learning rate is one of the most important hyperparameters; too large causes divergence or unstable training.

## Hyperparameter Tuning Concepts
- Hyperparameters such as batch size, learning rate, and dropout rate significantly affect model performance.
- Tuning hyperparameters is central to deep learning success.
- Hyperparameter tuning is not deterministic; multiple runs may yield different results.
- Key exam idea: understand the conceptual impact of each hyperparameter and how to correct underfitting or overfitting using them.

## Generalization vs Overfitting Summary
- No regularization → higher training accuracy than validation → overfitting.
- Adding dropout → improves validation accuracy and generalization.
- Too-large batch size → risk of local minima and inconsistent results.
- Too-large learning rate → overshooting and poor convergence.

