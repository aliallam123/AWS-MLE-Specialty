# SageMaker Resource Management Notes for MLS-C01

## Choosing Instance Types
- Deep learning training workloads benefit from GPU instances such as P3 or g4dn.
- Inference is less demanding and can often use cheaper compute optimized instances such as C5.
- Non deep learning algorithms typically use general purpose instances such as M5.
- GPU instances are expensive; use them only when justified.
- A single multi GPU instance can sometimes be more cost efficient than many CPU instances.

## Managed Spot Training
- Spot instances can reduce training cost by up to 90 percent.
- Spot interruptions can occur at any time, so you must use S3 checkpoints to resume training.
- Spot usage may increase total training time due to waiting for instance availability.
- Spot is beneficial for large, expensive training jobs where cost savings outweigh time and complexity.
