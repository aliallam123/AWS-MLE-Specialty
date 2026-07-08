# Additional Feature Engineering Techniques – Key Points for AWS ML Specialty Exam

---

## Binning
- Converts **numerical features into categorical features** by grouping values into "bins" (ranges).
- Example: Ages 20-29 → bin "20s", 30-39 → bin "30s", etc.
- Used to:
  - Handle measurement imprecision.
  - Simplify models expecting categorical inputs.
- **Quantile binning:**  
  - Bins contain **equal numbers of data points** (balanced samples per bin).
- Note: Binning reduces granularity (information loss), use carefully.

---

## Feature Transformation
- Apply mathematical **functions to features** to improve model fit.
- Examples:
  - Logarithmic transform to linearize exponential trends.
  - Adding polynomial terms (e.g., squared and square root of features) to help models capture non-linear relationships.
- Common in practice to **include original and transformed features together**.

---

## Encoding Categorical Data
- **One-Hot Encoding:**  
  - Create binary (0/1) variables—one per category.  
  - Example: Digit "8" encoded as `[0,0,0,0,0,0,0,0,1,0]` in a 10-class problem.  
  - Essential for models like deep learning that require numerical inputs.  
- Ensures neurons/features treat categories distinctly without implying order or magnitude.

---

## Scaling and Normalization
- Most ML models perform better if features are on **similar scales**.
- Methods include:
  - **Min-Max Scaling:** Rescales features to a defined range, typically 0 to 1.
  - **Standardization (Z-score):** Centers features around 0 with unit variance.
- Important to **reverse scale transformations on model outputs** when interpreting results.
- Some models (e.g., decision trees) less sensitive to scaling, but neural networks require it.

---

## Shuffling Data
- Randomizing the order of training data avoids bias from data collection sequences.
- Helps prevent models from learning spurious patterns related to order.
- Often leads to better and more stable model performance.

---

# Exam Focus Summary
- Understand **binning** (including quantile binning) as a way to discretize numerical data.  
- Know common **feature transformations** (log, polynomial terms) to help model non-linear trends.  
- Be able to explain and apply **one-hot encoding** for categorical variables.  
- Recognize the importance of **scaling/normalizing features** for ML models, especially neural networks.  
- Remember to **shuffle training data** to eliminate order-related biases.

---
