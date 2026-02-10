# L1 vs L2 Regularization — Exam Notes

## What Regularization Does
Regularization adds a penalty term to model weights during training to reduce overfitting.

---

## L1 Regularization (Lasso)
**Penalty:** Sum of absolute values of weights (|w|)

### Effects
- Performs **feature selection**
- Can shrink weights **exactly to zero**
- Produces **sparse models**
- Helps handle **curse of dimensionality**
- Less computationally efficient, but leads to smaller/faster final models

### When to Use L1
- Many features may be irrelevant
- Want automatic feature elimination

---

## L2 Regularization (Ridge)
**Penalty:** Sum of squared weights (w²)

### Effects
- **Does NOT remove features** — no weights become zero
- Shrinks weights smoothly
- Produces **dense models**
- Computationally efficient

### When to Use L2
- All features likely matter
- Want smooth weight reduction, not removal

---

## Key Differences

| Aspect | L1 | L2 |
|-------|----|----|
| Penalty | \|w\| | w² |
| Removes features? | **Yes** | No |
| Model type | Sparse | Dense |
| Computation | Less efficient | More efficient |
| Best for | Feature selection | Keeping all features |

---

## Core Takeaway
- **L1 = feature selection (sparse model)**  
- **L2 = weight shrinking (dense model)**  
