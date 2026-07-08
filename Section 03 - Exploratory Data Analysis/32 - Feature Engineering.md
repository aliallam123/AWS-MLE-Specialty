# Feature Engineering – Key Points for AWS ML Specialty Exam

---

## What is Feature Engineering?
- The process of **selecting, creating, transforming, and trimming features** (attributes) used to train ML models.
- Features are the input data attributes, e.g., age, height, income for predicting salary.
- Includes:
  - **Selecting relevant features** that impact the prediction.
  - **Handling missing data** effectively.
  - **Transforming features:** normalization, scaling, encoding.
  - **Creating new features** from existing ones via mathematical transformations (log, square, combine features).
- Essential for improving model quality and performance.
- Considered an **art and key skill** separating good ML practitioners from others; focus of the ML Specialty exam.

---

## Why is Feature Engineering Important?
- **Curse of Dimensionality:**
  - Adding too many features increases the dimensional space exponentially.
  - Data becomes sparse in high-dimensional space, making it harder to find optimal model solutions.
  - Models become more complex, harder to train, and prone to overfitting.
  - Reducing dimensions to relevant features improves training efficiency and model accuracy.
- Reduces computational resources needed for complex models like deep neural networks.

---

## How to Handle the Curse of Dimensionality
- **Feature selection:** Keep only features that add predictive value.
- **Feature transformation:** Scaling, normalization, encoding categorical variables.
- **Dimensionality reduction techniques:**  
  - **Principal Component Analysis (PCA):**  
    - Unsupervised method to reduce features into fewer artificial components preserving most variance/information.  
    - Produces new features that capture essence of original features.  
  - **K-Means Clustering:**  
    - Unsupervised technique that can also help reduce feature space by grouping similar instances.
- Use domain knowledge and iterative experimentation to identify impactful features.

---

## Summary for the Exam
- Feature Engineering is **critical** for successful ML model building.
- Understand **curse of dimensionality** and why fewer, quality features are better than many irrelevant ones.
- Be familiar with **feature transformations, missing data handling, and feature creation**.
- Know basics of **PCA** as a dimensionality reduction technique.
- Recognize that feature engineering requires domain knowledge and experimentation, not just applying algorithms blindly.

---
