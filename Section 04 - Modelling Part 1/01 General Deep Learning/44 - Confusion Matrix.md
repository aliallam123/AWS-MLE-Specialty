# Confusion Matrices – AWS Machine Learning Engineer Specialty Notes

## Purpose of a Confusion Matrix
- Accuracy alone can be misleading, especially in cases of class imbalance (e.g. rare disease prediction).
- A confusion matrix provides deeper insight into model performance by showing counts of true positives, false positives, true negatives, and false negatives.
- Useful for evaluating the impact of different error types depending on the business context.

## Binary Confusion Matrix Structure
- Predicted values usually on rows; actual values on columns (but formats vary; always check labels).
- Components:
  - True Positive (TP): predicted yes, actual yes
  - False Positive (FP): predicted yes, actual no
  - False Negative (FN): predicted no, actual yes
  - True Negative (TN): predicted no, actual no
- High-performing models have most values along the diagonal (TP and TN).

## Example (Binary Classification)
Using a cat vs. not‑cat classifier:
- True Positives: 50  
- False Positives: 5  
- False Negatives: 10  
- True Negatives: 100

## Multi‑Class Confusion Matrices
- Same concept but extended to more than two classes.
- Diagonal still represents correct predictions.
- Off‑diagonal cells represent misclassifications between classes.
- Often presented as a heat map where color intensity reflects count magnitude.

## Heat Map Interpretation
- Darker colors indicate higher counts.
- Expect a strong diagonal if the model performs well.
- Useful for identifying which classes are commonly confused.

## Legacy AWS Confusion Matrix Format (May Still Appear on Exam)
- Originated from a now‑deprecated AWS ML service but may still be referenced.
- Elements:
  - Heat map showing correct and incorrect predictions across classes.
  - Diagonal corresponds to correct predictions.
  - F1 scores shown per class.
  - Total column: true class frequencies.
  - Total row: predicted class frequencies.
- Key skill: interpret layout correctly regardless of orientation or labeling.

## Exam Tips
- Always confirm label orientation before interpreting a confusion matrix.
- Know how to derive precision, recall, F1 from TP, FP, FN.
- Understand when accuracy fails and why confusion matrices matter.
- Recognize multi‑class heat‑map versions of confusion matrices.
- Be prepared to interpret AWS‑style confusion matrix outputs even from deprecated services.
