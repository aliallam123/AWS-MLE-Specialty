# Ensemble Learning: Bagging and Boosting
Machine Learning Engineer Specialty Exam Notes

## Ensemble Learning Overview
- Ensemble methods combine multiple models to improve predictive performance.
- Models vote or average their outputs to produce a final prediction.
- Example: Random Forest is an ensemble of decision trees.

## Bagging (Bootstrap Aggregating)
- Creates multiple training sets via random sampling with replacement.
- Trains multiple models independently and in parallel.
- Final prediction is based on majority vote or averaging.
- Strengths:
  - Reduces variance.
  - Helps prevent overfitting.
  - Highly parallelizable.
- Common example: Random Forest.

## Boosting
- Sequential technique where each model depends on previous models.
- Assigns weights to training samples; misclassified samples get higher weights.
- Each new model focuses on correcting errors of the previous model.
- Strengths:
  - High accuracy.
  - Performs well in many competitions.
- Popular algorithm: XGBoost (commonly used in AWS SageMaker).

## Choosing Between Bagging and Boosting
- Use Boosting when:
  - Accuracy is the top priority.
- Use Bagging when:
  - Overfitting is a concern.
  - Parallel training is desired.
  - You want variance reduction.

## Key Points for Exam
- Bagging uses sampling with replacement; models train independently.
- Boosting reweights observations after each iteration; models train sequentially.
- XGBoost is a boosting method and widely used in industry and AWS ecosystem.
- Bagging reduces variance; boosting reduces bias.
``
