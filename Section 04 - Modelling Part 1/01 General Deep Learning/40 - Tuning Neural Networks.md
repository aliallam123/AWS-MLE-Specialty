# Lecture – Tuning Neural Networks: Learning Rate & Batch Size

## Why This Matters for the Exam

These are **core hyperparameters** that strongly affect:
- **Convergence** (does the model train well or not?)
- **Training time**
- **Stability and reproducibility**

Expect scenario questions about:
- Models not converging
- Training taking too long
- Inconsistent results from run to run

---

## Gradient Descent Basics (Context)

- Neural networks are trained via **gradient descent** (or variants).
- We:
  - Start with random weights.
  - Over many **epochs** (full passes over training data), update weights to **minimize a cost/loss function**.
- Each update is a “step” in parameter space toward (ideally) a minimum of the loss function.

---

## Hyperparameter: Learning Rate

**Learning rate** controls **how big each update step** is during gradient descent.

Effects:
- **Too high learning rate:**
  - Steps are too large.
  - Can **overshoot** the optimum and fail to converge (or bounce around).
- **Too low learning rate:**
  - Steps are tiny.
  - Training can be **very slow**, may require many epochs to reach a good solution.

**Exam points:**
- If a model **fails to converge / loss oscillates** → learning rate likely **too high**.
- If training is **very slow but improving gradually** → learning rate may be **too low**.
- Learning rate is a **hyperparameter** that must be tuned empirically.

---

## Hyperparameter: Batch Size

**Batch size** = number of training samples used to compute each weight update.

Key behavior (important and counterintuitive):
- **Smaller batch sizes:**
  - Introduce more “noise” in gradient estimates.
  - This noise helps the optimizer **escape local minima** and poor basins.
  - Less likely to get stuck in a bad local minimum.
- **Larger batch sizes:**
  - Gradients are smoother but can **settle into local minima** and stay there.
  - Model can **converge to a suboptimal solution**.
  - Because data is shuffled each epoch, a borderline-too-large batch size can cause:
    - **Inconsistent results between runs** (sometimes stuck in a bad minimum, sometimes not).

**Exam points to memorize:**
- **Small batch size** → better chance to **escape local minima**.
- **Large batch size** → can **get stuck in wrong/local minima**.
- Large batch size + data shuffling → **run-to-run variability** in final performance.

---

## Quick Exam-Oriented Summary

- **Learning rate:**
  - Too high → overshoots minimum, poor or non-convergent training.
  - Too low → slow convergence, more epochs needed.

- **Batch size:**
  - Too large → risk of converging to **suboptimal local minima**, inconsistent results across runs.
  - Smaller → more robust to local minima, generally preferred for better generalization (at the cost of more noisy updates).

- Both are **hyperparameters**:
  - Not learned by the model.
  - Must be tuned; they can be as important as network architecture and feature engineering.

<img width="981" height="290" alt="image" src="https://github.com/user-attachments/assets/7906272c-ba8f-4442-84c8-ab45badbb9ef" />
