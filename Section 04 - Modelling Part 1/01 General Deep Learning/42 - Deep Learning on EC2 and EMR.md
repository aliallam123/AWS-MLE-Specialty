# Lecture – Deep Learning on AWS Compute (GPU & Specialized Instances)

## Exam-Relevant Focus

Know:
- Which **EC2/EMR instance families** are appropriate for **deep learning training vs inference**.
- That AWS has **GPU-based** and **custom silicon–based** options.
- High-level purpose, not chip-level details.

---

## GPU-Based Deep Learning Instances

AWS GPU instances (all based on **NVIDIA GPUs**):

- **P3**:
  - High-end training.
  - Uses **Tesla V100 GPUs** (up to 8 per instance).
  - Good for large-scale deep learning training.

- **P2**:
  - Older, more cost-effective than P3.
  - Uses **K80 GPUs** (up to 16 per instance).
  - Suitable for experimentation/smaller workloads.

- **G3**:
  - Uses **M60 GPUs**.
  - Historically more focused on graphics/visualization, but can be used for deep learning.

- **G5g**:
  - CPU: **Graviton2**.
  - GPU: **NVIDIA T4G Tensor Core GPUs**.
  - Designed for GPU workloads like game streaming, but also usable for deep learning.
  - Note: not available in EMR (EC2 only).

- **P4d**:
  - Uses **NVIDIA A100 GPUs**.
  - Can be clustered into **UltraClusters** for supercomputing-scale training (e.g., very large models, LLMs).
  - Very high-end and expensive; used for cutting-edge large-scale training jobs.

**Exam angle:** When asked about accelerating deep learning on EC2/EMR, think **P2/P3/P4d/G families with NVIDIA GPUs**.

---

## Custom AWS ML Silicon: Trainium and Inferentia

AWS has **custom chips** targeted at ML workloads:

### Trn1 / Trn1n – Training (Trainium)

- **Trn1**:
  - Powered by **AWS Trainium**.
  - Optimized for **training large neural networks / LLMs**.
  - Claims ~**50% cost savings** over comparable GPU instances for training large models.
  - High-speed networking via **Elastic Fabric Adapter (EFA)** (up to **800 Gbps** per node).

- **Trn1n**:
  - Variant with **even more network bandwidth** (~**1600 Gbps** per node).
  - For extremely large, distributed training jobs requiring fast cross-node communication.

**Use case:** Large-scale distributed training (e.g., GPT-class models) with emphasis on **training cost and throughput**.

### Inf2 – Inference (Inferentia2)

- **Inf2**:
  - Powered by **AWS Inferentia2**.
  - Optimized for **high-throughput, low-latency inference**.
  - Intended for production serving of **pre-trained** models (including large language models).

Conceptual narrative:
- Today: much compute spent on **training** LLMs.
- Future: more compute will be spent on **inference** as many users call pre-trained models.
- **Inf2** targets that future inference-heavy workload.

**Exam angle:**
- **Training** large DL/LLM models → **Trn1/Trn1n** or **GPU instances (P3/P4d)**.
- **Inference** at scale for trained DL/LLM models → **Inf2**.

---

## Other AWS Deep Learning Convenience Options

- **Deep Learning AMIs (DLAMIs)**:
  - Pre-built Amazon Machine Images with frameworks like **TensorFlow, PyTorch, MXNet** plus drivers, CUDA, etc.
  - Quick way to start deep learning on EC2 GPU instances.

- **Amazon EMR**:
  - Can be configured with **GPU instance types**.
  - Supports **MXNet, TensorFlow, PyTorch** for distributed deep learning on clusters.

- **Amazon SageMaker**:
  - Managed ML service.
  - Can launch training/inference jobs on many of these instance types (GPU, Trainium, Inferentia).
  - Handles provisioning and scaling of the underlying hardware.

---

## Quick Exam Recap

- **GPU-based** instances (P2/P3/P4d/G3/G5g) → general-purpose deep learning training (and some inference).
- **Trainium (Trn1/Trn1n)** → **training-optimized**, especially for large models with high networking needs.
- **Inferentia (Inf2)** → **inference-optimized** for deploying large models at scale.
- **Deep Learning AMIs** → easy way to get ready-to-use deep learning environments on EC2.
- **SageMaker** and **EMR** can leverage these instance types for managed training and inference.
