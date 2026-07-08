# Lecture – Transformers, NLP, and Transfer Learning on AWS

## Key Exam-Relevant Ideas

- Modern NLP = **transformer architectures** with **self-attention**.
- Common transformer models: **BERT, RoBERTa, T5, GPT‑2/3, DistilBERT**.
- You **almost never train from scratch**; you **reuse and fine‑tune pre‑trained models**.
- On AWS, you commonly use **Hugging Face models with SageMaker** (via Hugging Face DLCs).

---

## Transformers and Self-Attention

- Transformers are the **current state-of-the-art** deep learning architecture for NLP.
- Core mechanism: **self-attention**:
  - Learns which tokens/words are important **relative to each other**.
  - Provides context for all tokens at once, allowing **parallel processing of sequence elements** (unlike RNNs that process strictly step-by-step).

Terms you might see:
- **BERT** – *Bidirectional Encoder Representations from Transformers*  
  - Transformer-based NLP model (encoder-focused).
- **GPT** – *Generative Pre‑Trained Transformer*  
  - Transformer-based generative model (decoder/decoder‑style); basis for ChatGPT.
- **DistilBERT** – A **smaller, compressed** version of BERT created via **knowledge distillation** (~40% smaller).
- Others mentioned: RoBERTa, T5, GPT‑2/3.

**Exam focus:** Recognize that these are **pre-trained transformer NLP models**, not something you design from scratch.

---

## Using Pre‑Trained NLP Models (Hugging Face + SageMaker)

- These models are massive (hundreds of billions+ parameters); **training from scratch is usually infeasible**.
- Approach: **transfer learning** with pre‑trained models.
- **Hugging Face model hub (“model zoo”):**
  - Thousands of pre‑trained NLP models (BERT, GPT‑2, etc.).
  - Integrated with **Amazon SageMaker** via **Hugging Face Deep Learning Containers (DLCs)**.
- Typical workflow:
  1. Select a pre‑trained model (e.g., BERT) from Hugging Face.
  2. Use SageMaker + Hugging Face DLC to deploy/train.
  3. Optionally fine‑tune on your own domain data.

---

## Transfer Learning Strategies for NLP Models

Let’s assume you import a **pre‑trained BERT** model (trained on BookCorpus + Wikipedia) and want to adapt it to your own text domain.

### 1. Use As‑Is

- When:
  - The pre‑training domain is **close enough** to your use case.
- What you do:
  - Deploy the model and directly use it for inference.
- Pros:
  - No extra training, lowest cost and complexity.

### 2. Fine‑Tuning (Continue Training the Whole Model)

- When:
  - You want **incremental improvements** for your specific domain/tasks.
  - You have **some** domain data, but not enough to fully train a huge model.
- How:
  - Prepare your training text:
    - **Tokenize** using the **same tokenizer** and vocabulary the model was originally trained with.
  - Unfreeze the model’s weights and **continue training** on your own data.
  - Use a **low learning rate** so you:
    - Preserve the knowledge from large pre-training.
    - Gently adapt to your new domain.

**Exam tip:** If the scenario says *“adapt a large pre-trained NLP model to a new but related domain without losing its existing knowledge”*, think **fine‑tuning with a low learning rate**.

### 3. Add New Trainable Layers on Top (Feature Extractor + New Head)

- When:
  - You want to **reuse the pre-trained model as a feature extractor**, but predict **new labels or outputs**.
- How:
  - Freeze the existing model weights.
  - Add new layers (“head”) on top for your specific task (e.g., classification layer).
  - Train only the new layers.
- Optionally:
  - After adding the new layers and training them, **unfreeze some or all layers** and fine‑tune the combined model (common pattern).

**Exam tip:** If the question mentions *“using pre-trained features and training only a small number of additional parameters”* → **freeze base model, add new layers** (optionally followed by fine‑tuning).

### 4. Train from Scratch

- When:
  - You have **very large amounts of your own data**.
  - You care primarily about the **architecture**, not the pre-trained weights.
  - You have **significant compute** (rare in practical exam scenarios).
- How:
  - Initialize model weights randomly.
  - Train entirely on your own dataset.

**Exam tip:** This is a **special case**. In most realistic AWS exam scenarios, **transfer learning is preferred** because of cost and data requirements.

---

## Choosing an Approach (Exam-Oriented Summary)

Given a large transformer NLP model (e.g., BERT/GPT) and your use case:

- **Pre-trained model domain ≈ your domain, minimal extra requirements**
  - → **Use the pre-trained model as‑is**.

- **Your domain is related; you have some extra data; you want better performance**
  - → **Fine‑tune** the full model with **low learning rate**.

- **You want to map pre-trained features to a different prediction/output**
  - → **Freeze base model, add new layers on top**, train those layers.
  - Optionally follow with **additional fine‑tuning**.

- **You have huge data and massive compute**
  - → Consider **training from scratch**, but this is atypical and expensive.

Also remember:
- Must use **consistent tokenization** with the original model.
- Transformer NLP + transfer learning is the **standard approach** due to model size and cost.
