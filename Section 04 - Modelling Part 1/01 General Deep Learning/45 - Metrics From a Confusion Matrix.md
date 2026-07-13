# Metrics Derived From a Confusion Matrix

## Recall
- Formula: TP / (TP + FN)
- Also known as sensitivity, true positive rate, completeness.
- Use when false negatives are costly.
- Example domains: fraud detection.
- Example from matrix: TP = 5, FN = 10 => 5 / 15 = 0.3333.

## Precision
- Formula: TP / (TP + FP)
- Also called correct positive rate or percent of relevant results.
- Use when false positives are costly.
- Example domains: medical screening, drug testing.
- Example from matrix: TP = 5, FP = 20 => 5 / 25 = 0.20.

## Specificity
- Formula: TN / (TN + FP)
- Also known as true negative rate.
- Complements sensitivity.

## F1 Score
- Formula: 2TP / (2TP + FP + FN)
- Equivalent form: 2 * (Precision * Recall) / (Precision + Recall)
- Harmonic mean of precision and recall.
- Useful when both precision and recall matter.

## RMSE
- Root mean squared error.
- Measures pure accuracy for regression tasks.
- Computed as square root of mean of squared errors.
- Does not address precision or recall.

## ROC Curve
- Plots true positive rate (recall) versus false positive rate at different thresholds.
- Good ROC curves bend toward the upper left corner.
- A perfect classifier has a right angle curve with AUC = 1.0.
- AUC = probability that a randomly chosen positive ranks higher than a negative.
- AUC of 0.5 represents random performance.

## PR Curve (Precision Recall Curve)
- Plots precision versus recall.
- Area under curve should be as large as possible.
- Better for information retrieval problems with highly imbalanced data.
- Avoids tiny-number issues common in ROC for large document sets.
