# Deep Learning on EC2 (TensorFlow) – Exam‑Relevant Notes

## Focus of the Exam
- The MLS‑C01 exam tests practical machine learning experience, not coding ability.
- Emphasis is on identifying and addressing issues such as:
  - Overfitting
  - Local minima
  - Hyperparameter misconfiguration
- Expect conceptual questions about training behavior, not implementation details.

## Why This Lab Matters for the Exam
This lab is useful for notes because it reinforces concepts the exam *will* test, including:
- How deep learning training behaves on GPU instances.
- How to detect overfitting during training.
- How to tune hyperparameters (batch size, learning rate, number of epochs).
- Understanding when and why to choose GPU‑based compute for deep learning.
- Awareness of AWS constraints such as which instance families support GPU‑accelerated frameworks.

## Relevant AWS Concepts Demonstrated
### 1. Choosing the Correct AMI
- Deep Learning AMIs include preinstalled frameworks like TensorFlow.
- AWS may test your ability to select the appropriate AMI for a use case.

### 2. Selecting GPU Instance Types
- Not all GPU types are supported for all deep learning AMIs.
- Example considerations shown in the lab:
  - P3 supports TensorFlow on DLAMI.
  - P2 is **not** supported.
- Cost awareness is important; exam often touches on cost‑optimization.

### 3. Understanding GPU Limits on Accounts
- Some AWS accounts limit access to GPU instances.
- This is relevant for exam scenarios involving resource availability.

### 4. Notebook Environments
- You can use:
  - SageMaker Notebook Instances (managed)
  - EC2 with Jupyter (DIY)
- Exam may ask when to choose SageMaker vs EC2 based on management, scaling, or simplicity.

## Concepts Reinforced by the Lab
Even though the environment setup itself is not directly tested, the **training workflow** and **hyperparameter tuning** are central for the exam:
- Running a convolutional neural network.
- Observing model performance during training.
- Identifying overfitting by comparing training and validation curves.
- Applying fixes such as:
  - Regularization
  - Dropout
  - Reducing model complexity
  - Changing learning rate
  - Early stopping

These topics are core exam items.

## What NOT to Take Notes On
The following setup steps are **not tested on the exam**, so do not include them in your study notes:
- Using PuTTY on Windows.
- SSH tunneling details.
- Uploading notebooks manually.
- EC2 dashboard navigation steps.

## Summary
This lab is **worth taking notes on**, but only for the ML‑related concepts:
- Overfitting detection
- Hyperparameter tuning strategies
- GPU instance selection logic
- When to use EC2 vs SageMaker for deep learning workloads

Do **not** take notes on environment setup or PuTTY usage, as these are irrelevant to the exam.
