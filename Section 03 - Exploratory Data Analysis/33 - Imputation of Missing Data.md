# Imputation of Missing Data – Key Points for AWS ML Specialty Exam

---

## Why Imputation is Important
- Real-world datasets often have missing feature values.
- Handling missing data correctly improves model quality.
- Dropping rows with missing data can **bias the dataset** if missingness relates to important attributes.

---

## Simple Imputation Methods
### Mean Replacement (Numerical Features)
- Replace missing values with the **mean of the feature column**.
- Pros: Simple, fast, and keeps overall mean intact.
- Cons:
  - Sensitive to outliers (mean skewed by extreme values).
  - Ignores correlations with other features.
  - Only works on numerical data.
  
### Median Replacement (Numerical Features)
- Use median instead of mean when outliers skew distribution.
- More robust than mean but still simplistic.

### Mode Replacement (Categorical Features)
- Replace missing categorical data with the **most frequent category**.
- Analogous to mean replacement but for categories.

---

## Limitations of Simple Methods
- Naive and do not capture feature dependencies.
- Can produce unrealistic imputations (e.g., 10-year-old earning average adult salary).
- Poor choice for categorical or complex data.

---

## Advanced Imputation Methods
### K-Nearest Neighbors (KNN) Imputation
- Finds *K* most similar rows based on other features.
- Imputes missing value as average (numerical) or mode (categorical) from neighbors.
- Uses feature correlations but best suits numerical data.
- Difficult for categorical data without special distance metrics.

### Model-Based Imputation
- Train ML models (e.g., deep learning, regression) to predict missing values from other features.
- Works well for both numerical and categorical data.
- Requires more computational resources and tuning.
- Example: Neural networks used to impute categorical features.

### Multiple Imputation by Chained Equations (MICE)
- State-of-the-art iterative regression-based technique.
- Models each feature with missing data conditionally based on others.
- Creates multiple imputations improving accuracy.
- Recognized as a strong imputation method (may appear on exam).

---

## Other Important Points
- Sometimes **dropping missing rows is acceptable** if data volume is large and missingness is random.
- When dropping data, ensure **no bias is introduced** due to non-random missingness.
- **Best solution: acquire more complete, higher quality data** to minimize missing values.
- Imputation methods cover gaps when better data collection is not possible.

---

# Exam Focus Summary
- Understand **mean, median, and mode imputation** as simple baseline methods.
- Know limitations of simple imputations (ignore correlations, poor for categorical).
- Be familiar with **KNN imputation** for numerical data using feature similarity.
- Recognize **model-based imputation (e.g., deep learning, regression)** as advanced solutions.
- Know about **MICE** as a strong imputation technique.
- Understand the risk of **bias when dropping missing data**.
- Remember best practice is to strive for **more and better data**.

---
