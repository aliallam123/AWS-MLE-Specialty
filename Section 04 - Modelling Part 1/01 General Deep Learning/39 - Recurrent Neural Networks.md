# Lecture – Recurrent Neural Networks (RNNs), LSTM, and GRU

## Exam Objectives Covered

Relevant exam areas:
- Choosing appropriate model types for sequence/time-series data.
- Understanding challenges and techniques in training deep learning models.
- Applying sequence models in common ML application domains (e.g., NLP, time series).

---

## What RNNs Are For

**Core idea:** RNNs are designed for **sequential data**, where **order matters**.

Typical use cases:
- **Time series**
  - Web logs (website hits over time)
  - Sensor/IoT logs
  - Stock prices and trading history
  - Vehicle trajectories (e.g., self-driving cars using past trajectory to predict next movement)
- **Language / Text**
  - Machine translation
  - Sentiment analysis
  - Generating captions for images and videos
- **Other sequences**
  - Music generation (sequence of musical notes)
  - Any ordered sequence of tokens/events of arbitrary length

**Key exam point:** When a scenario involves **dependent observations over time or in a sequence**, RNN-based architectures (or variants like LSTM/GRU) are appropriate.

---

## Conceptual View of a Recurrent Neuron (Memory Cell)

A recurrent neuron:
- Receives the **current input** at time step *t* (e.g., the current word, current time value).
- Receives the **previous output/state** from time step *t‑1*.
- Produces a new **output/state** at time step *t*.

Typical behavior:
- Uses a smooth activation function like **tanh**.
- The output at time *t* is fed back as input at time *t+1*.
- Over many time steps, the neuron maintains a **memory** of past behavior.

Important property:
- Earlier time steps still influence later ones, but their influence **decays** as more time steps are processed.
- **More recent inputs usually have more impact** on the current state than very old inputs.

---

## Unrolling RNNs Through Time

Instead of thinking of a loop, you can think of the same cell at multiple time steps:

- Time step 0: input `x₀` → output `h₀`
- Time step 1: input `x₁` and `h₀` → output `h₁`
- Time step 2: input `x₂` and `h₁` → output `h₂`
- …

This is called **unrolling in time**, and it makes clear that:
- Training an RNN is like training a **very deep network** where each time step is another “layer.”
- The sequence length contributes directly to the effective depth of the model during training.

---

## RNN Layers

Instead of a single recurrent neuron, you typically use a **layer** of recurrent neurons:

- A layer might have many recurrent units (e.g., 32, 64, 256, …).
- At each time step, the layer:
  - Receives the input for that time step.
  - Receives the previous hidden state (all units’ outputs from the previous time step).
  - Produces a new hidden state.

This allows the network to learn **more complex patterns** across time.

---

## RNN Input–Output Topologies

### 1. Sequence-to-Sequence

- **Input:** sequence
- **Output:** sequence
- Examples:
  - Forecasting future values in a time series from past values.
  - Machine translation (e.g., French sentence → English sentence).
- Often implemented with **encoder–decoder** architectures.

### 2. Sequence-to-Vector

- **Input:** sequence
- **Output:** single vector or label
- Examples:
  - Sentiment classification of a sentence.
  - Classifying a user session based on their sequence of actions.

### 3. Vector-to-Sequence

- **Input:** static vector
- **Output:** sequence
- Examples:
  - Image captioning: image embedding → sequence of words (caption).
  - Generating a sequence of actions from a fixed state representation.

### 4. Encoder–Decoder for Translation and Similar Tasks

- **Encoder (sequence → vector):**
  - Consumes a sequence (e.g., words in French).
  - Produces a fixed-size embedding representing the overall meaning.
- **Decoder (vector → sequence):**
  - Takes that embedding and generates a new sequence (e.g., words in English).
- Used in:
  - Machine translation
  - Summarization
  - Any “input sequence → output sequence” problem where lengths may differ.

**Exam tip:** Be able to match a described problem with the correct topology:
- Sequence sentiment → sequence-to-vector.
- Image captioning → vector-to-sequence.
- Translation → sequence-to-sequence with encoder–decoder.

---

## Training RNNs: Backpropagation Through Time

### Backpropagation Through Time (BPTT)

To train RNNs:
- You backpropagate gradients:
  - Through the **network layers**, and
  - Through **all time steps** the network was unrolled over.
- Each time step acts like another layer, so:
  - Long sequences → very deep effective network.
  - Training cost grows with sequence length.

Challenges:
- Computationally intensive.
- Prone to **vanishing** or **exploding** gradients.
- More sensitive than CNNs to:
  - Architecture choices (number of layers, units).
  - Hyperparameters (learning rate, sequence length, batch size, etc.).

### Truncated Backpropagation Through Time

To reduce cost:
- Use **truncated BPTT**:
  - Only backpropagate through a **limited window of time steps** (e.g., last N steps).
  - Cuts down computation and memory usage.
- Trade-off:
  - Less ability to capture very long-range dependencies,
  - But significantly lower training cost.

**Exam tip:** If a scenario mentions reducing computational cost or memory for long sequences, truncated BPTT is a relevant concept.

---

## Long Short-Term Memory (LSTM) Cells

Problem with basic RNNs:
- Early information’s influence decays quickly.
- Many tasks (especially in NLP) need **long-range dependencies**, where early inputs matter as much as later ones.

**LSTM (Long Short-Term Memory):**
- A specialized recurrent cell designed to maintain **long-term and short-term memory**.
- Uses gates to:
  - Decide what information to **keep**, **forget**, and **output**.
- Effect:
  - Helps preserve information across many time steps.
  - Mitigates vanishing gradient issues.

Conceptual exam understanding:
- Use **LSTM** when:
  - Long-range dependencies are important.
  - You can’t assume that recent inputs are always more important than earlier ones.
- Internals (exact gate equations) are generally **not required**; understand what problems LSTMs solve and when to use them.

---

## GRU (Gated Recurrent Unit) Cells

GRU is a **simplified alternative** to LSTM:

- Fewer gates and parameters.
- Typically:
  - Faster and cheaper to train.
  - Comparable performance to LSTM on many tasks.

When to use GRU:
- When you need a **good trade-off between model complexity and performance**.
- When training time or resource constraints are significant.

**Exam tip:** Know the high-level comparison:
- Basic RNN: simplest, struggles with long-range dependencies.
- LSTM: better for long dependencies, more complex.
- GRU: simpler than LSTM, often similar performance, faster to train.

---

## Practical Challenges and Exam-Style Considerations

Key practical points:
- RNNs can be:
  - Harder to train than CNNs.
  - Highly sensitive to topology and hyperparameters.
  - Resource-intensive, especially with long sequences.
- Risks:
  - Non-convergence or very slow convergence if you choose poor hyperparameters or architecture.

Best practices (conceptual):
- Prefer **proven architectures** and standard implementations (e.g., built-in LSTM/GRU layers in frameworks).
- For AWS-oriented design questions:
  - Consider cost and training time when choosing between basic RNN, LSTM, and GRU.
  - Use RNN variants where sequence/time dependencies are clearly present.

---

## Quick Exam Review

Before answering a question:

1. **Is the data a sequence where order or time matters?**
   - Yes → consider RNN/LSTM/GRU.

2. **What is the input vs. output?**
   - Sequence → sequence → sequence model or encoder–decoder.
   - Sequence → label/vector → sequence-to-vector (e.g., sentiment).
   - Vector → sequence → vector-to-sequence (e.g., captioning).

3. **Are long-range dependencies important?**
   - Yes → LSTM or GRU preferred over basic RNN.

4. **Is training cost or complexity an issue?**
   - Yes → GRU or truncated BPTT can help.

5. **Is the question about training difficulty or instability?**
   - Mention:
     - Backpropagation through time.
     - Sensitivity to topology/hyperparameters.
     - Potential for non-convergence with poor choices.
