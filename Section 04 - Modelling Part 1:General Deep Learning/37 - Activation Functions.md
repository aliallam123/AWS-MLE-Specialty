```markdown
# Activation Functions – Key Points for AWS ML Specialty Exam

---

## What is an Activation Function?
- Function inside a neuron that computes the output based on inputs.
- Determines how information is passed to the next layer.
- Enables neural networks to learn complex mappings.
- Critical for non-linear transformations in deep learning.

---

## Common Activation Functions

### Linear Activation
- Outputs input as-is (identity function).
- **Not useful**: no learning or benefit from multiple layers (network equivalent to single layer).

### Binary Step Function
- Outputs 0 if input below threshold; outputs fixed positive value otherwise.
- Very limited (binary only), not differentiable (problematic for training).
- Rarely used today.

### Non-Linear Activation Functions (Preferred)

#### Sigmoid (Logistic)
- Output range: (0,1).
- Used for binary classification.
- Issues: vanishing gradients, slower convergence.

#### Hyperbolic Tangent (TanH)
- Output range: (-1, 1).
- Mean centered around zero, often preferred over sigmoid.
- Used in recurrent neural networks.
- Suffers from vanishing gradient problem at extremes.

#### Rectified Linear Unit (ReLU)
- Output = max(0, input).
- Fast, simple, computationally efficient.
- Enables deep networks by alleviating vanishing gradient.
- **Dying ReLU problem:** neurons stuck at zero outputs (inactive).

#### Leaky ReLU
- Like ReLU but allows small slope for negative inputs (e.g., 0.01 * x).
- Mitigates dying ReLU issue.

#### Parametric ReLU (PReLU)
- Like Leaky ReLU, but slope of negative part is learned during training.
- More flexible but computationally heavier.

#### Exponential Linear Unit (ELU)
- Smooth curve for negative values (exponential).
- Can improve convergence vs Leaky ReLU.

#### Swish (Developed by Google)
- Smooth non-linearity, performs well on very deep networks (40+ layers).
- Less common in AWS context but good to know.

#### Maxout
- Outputs the max of inputs.
- Powerful but doubles parameters (costly), less practical.

---

## Output Layer Activation for Classification

### Softmax
- Used for **multi-class single-label classification**.
- Converts raw outputs to probabilities summing to 1.
- Allows picking most probable class.
- Not suitable for multi-label (non-mutually exclusive) classification.

### Sigmoid (Output Layer)
- Used for **multi-label classification** (assign multiple classes).
- Outputs independent probabilities per class.

---

## How to Choose Activation Functions

| Use Case                         | Activation Function   |
|---------------------------------|----------------------|
| General hidden layers            | ReLU (default)       |
| Avoid dying ReLU                 | Leaky ReLU / PReLU   |
| Very deep networks (40+ layers) | Swish                |
| Recurrent neural networks        | TanH                 |
| Output multi-class single label | Softmax              |
| Output multi-label classification| Sigmoid              |

---

# Exam Focus Summary
- Activation functions **introduce non-linearity**, allowing learning complex patterns.
- **ReLU** and its variants are the most common hidden-layer activations.
- **Softmax** for multi-class classification output layer; **sigmoid** for multi-label.
- Understand **vanishing gradient problem** with sigmoid and tanh.
- Know issues like **dying ReLU** and solutions (Leaky ReLU, PReLU).
- Be familiar with the purpose and application context of the main activation functions listed.

---
```
