# Lecture – Regularization in Neural Networks (Overfitting Control)

## Core Concept: Overfitting & Regularization

- **Overfitting**: Model performs **very well on training data** but **poorly on validation/test data**.
  - The model learns **noise or spurious patterns** instead of generalizable structure.
  - Symptom: **Training accuracy >> Validation/Test accuracy**.
- **Regularization**: Any technique used to **reduce overfitting** and improve **generalization**.

### Datasets Terminology

Typical deep learning setup uses three datasets:

- **Training set**: Used to update weights.
- **Validation (evaluation) set**: Used during training to monitor performance and tune hyperparameters.
- **Test set**: Used **after training** to evaluate final model performance.

Exam angle: If training accuracy increases but **validation/test accuracy plateaus or drops**, think **overfitting** and **regularization**.

---

## Regularization Technique 1: Simplify the Model

- Overfitting often occurs because the model is **too complex**:
  - Too many layers (too deep)
  - Too many neurons per layer (too wide)
- Simplifying:
  - Use **fewer layers**.
  - Use **fewer neurons** per layer.
- If a **simpler model** achieves similar test/validation accuracy without overfitting:
  - Prefer the simpler architecture.

**Exam cue:** If a scenario mentions an overfitting deep network, one straightforward remedy is to **reduce network complexity**.

---

## Regularization Technique 2: Dropout

**Dropout**:
- At each training step (epoch/mini-batch), **randomly “drop” (disable) a subset of neurons** in a layer.
- Forces the network to:
  - **Distribute learning** across many neurons.
  - Avoid relying too heavily on specific neurons that memorize patterns.
- Commonly used in deep networks (e.g., CNNs); dropout rates like **50%** are not unusual.

Effects:
- Reduces overfitting by:
  - Preventing individual neurons from over-specializing to particular training examples.
- At inference time:
  - **All neurons are active** (no dropout) with adjusted scaling in frameworks.

**Exam cue:** When asked how to reduce overfitting in a deep network (especially CNNs), **add or increase dropout** is a standard answer.

---

## Regularization Technique 3: Early Stopping

**Early stopping** monitors validation performance **during training**:

Typical pattern:
- **Training accuracy** keeps increasing with more epochs.
- **Validation accuracy**:
  - Improves up to some epoch (e.g., epoch 5),
  - Then **stagnates or worsens** (oscillates or drops).

This indicates:
- The model is beginning to **overfit** to the training set.

Early stopping:
- Automatically **stops training** when validation performance stops improving for some patience period.
- Prevents unnecessary extra epochs that increase overfitting.

**Exam cue:**
- Scenario: “Training accuracy keeps increasing, but validation accuracy stops improving after N epochs.”
  - Recommended action: **Use early stopping** (stop at or near the best validation epoch).

---

## Quick Exam Summary

To address **overfitting** in neural networks:

- **Simplify the model**:
  - Fewer layers / fewer neurons.
- **Dropout**:
  - Randomly disable a fraction of neurons during training to improve generalization.
- **Early stopping**:
  - Monitor validation metrics and stop training when they no longer improve.

Diagnosis:

- Training accuracy ↑, validation accuracy ↔ or ↓ → model is **overfitting** → apply regularization.
