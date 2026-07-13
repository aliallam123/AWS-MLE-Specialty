# Confusion Matrix Metrics for the AWS Machine Learning Specialty Exam

## Confusion Matrix Structure
- True Positive (TP): Predict Positive, Actual Positive
- True Negative (TN): Predict Negative, Actual Negative
- False Positive (FP): Predict Positive, Actual Negative
- False Negative (FN): Predict Negative, Actual Positive
- Always confirm the layout of the confusion matrix before computing metrics.

## Recall
- Formula: TP / (TP + FN)
- Also called: Sensitivity, True Positive Rate, Completeness
- Use when false negatives are costly
  - Example: Fraud detection (missing fraud is unacceptable)
- Example Calculation:
  - TP = 5, FN = 10
  - Recall = 5 / (5 + 10) = 1/3 = 33.33 percent

## Precision
- Formula: TP / (TP + FP)
- Also called: Correct Positive Rate, Percent of Relevant Results
- Use when false positives are costly
  - Example: Medical or drug testing (a false positive has serious consequences)
- Example Calculation:
  - TP = 5, FP = 20
  - Precision = 5 / 25 = 20 percent

## Specificity
- Formula: TN / (TN + FP)
- Also called: True Negative Rate

## F1 Score
- Formula: 2TP / (2TP + FP + FN)
- Equivalent: 2 * (Precision * Recall) / (Precision + Recall)
- Harmonic mean of precision and recall
- Use when wanting a combined measure of precision and recall
- Note: Often better to directly choose precision or recall depending on the use case, but required knowledge for the exam.

## RMSE (Root Mean Squared Error)
- Used for regression problems
- Straight measure of accuracy: square errors, average them, then take the square root
- Does not consider precision or recall

## ROC Curve (Receiver Operating Characteristic)
- Plots True Positive Rate (Recall) vs False Positive Rate across thresholds
- Ideal curve bends toward upper-left corner
- Diagonal line indicates random performance
- AUC (Area Under Curve):
  - AUC = 0.5 means no better than random
  - AUC = 1.0 means perfect classifier
  - Represents probability that a classifier ranks a random positive higher than a random negative

## Precision Recall (PR) Curve
- Plots Precision vs Recall
- Higher area under the curve is better
- More suitable for information retrieval and highly imbalanced datasets
- Useful when relevant items are rare compared to total items
