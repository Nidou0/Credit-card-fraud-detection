This repository contains an end-to-end credit card fraud detection project built on a highly imbalanced real-world transactions dataset. The main objective is to develop, compare, and interpret machine learning models that can accurately identify fraudulent transactions while minimizing false alarms on legitimate ones.

The workflow covers the full data mining pipeline:

Problem Definition & Data Understanding

Frames fraud detection as a supervised classification problem (fraud vs. non-fraud).

Uses an anonymized credit card transactions dataset with numerical features (V1–V28 from PCA), Time, and Amount.

Highlights the severe class imbalance (fraudulent cases are a tiny minority), which makes naive accuracy misleading.

Exploratory Data Analysis (EDA)

Examines class distribution and descriptive statistics for key features.

Visualizes correlations and feature distributions to understand relationships and potential separation between fraud and non-fraud classes.

Identifies skewness, outliers, and any features that may require scaling or transformation.

Data Preprocessing & Feature Engineering

Performs cleaning and preparation of the raw dataset (handling missing values, removing obvious inconsistencies if any).

Applies outlier-robust scaling (e.g., StandardScaler/RobustScaler) to normalize Amount and other relevant features.

Handles class imbalance using techniques such as SMOTE (Synthetic Minority Over-sampling Technique) on the training set to balance fraud and non-fraud examples.

Optionally tests feature selection / dimensionality reduction to retain informative predictors and reduce noise.

Model Development & Training
The project benchmarks three main classification algorithms:

Decision Tree Classifier

Baseline interpretable model.

Simple tree structure helps visualize decision rules and feature splits, but tends to overfit and underperform on minority class.

Random Forest Classifier

Ensemble of decision trees with bootstrap aggregation, improving robustness and generalization.

Tuned via GridSearchCV over key hyperparameters (number of trees, max depth, minimum samples per split/leaf, etc.).

XGBoost Classifier

Gradient boosting ensemble designed for tabular data.

Hyperparameter tuning (learning rate, max depth, number of estimators, subsampling, etc.) to optimize performance on imbalanced data.

Emphasis on maximizing recall for the fraud class, accepting some trade-off in precision.

Model Evaluation & Comparison

Uses a train–test split (and cross-validation for tuning) to ensure fair performance estimates.

Evaluation metrics include:

Precision, Recall, F1-score (with focus on fraud class performance)

Accuracy (reported but interpreted carefully due to imbalance)

Confusion matrices to inspect true/false positives and negatives

ROC curves and AUC scores to compare discriminative power across models.

Key results:

Random Forest delivers the best balanced performance with an F1-score around 0.84 on the fraud class, making it a strong candidate for practical deployment.

XGBoost achieves the highest recall, capturing more fraudulent transactions but with lower precision (more false positives).

Decision Tree is the most interpretable but has weaker overall performance, useful mainly as a baseline and for insight into feature splits.

Insights, Limitations & Future Work

Discusses the trade-off between catching as many fraud cases as possible (high recall) and not overwhelming analysts or customers with false alarms (precision).

Highlights the impact of SMOTE and hyperparameter tuning on improving minority-class performance.

Suggests future extensions such as cost-sensitive learning, more advanced imbalance handling, temporal validation (to respect transaction time order), and deployment-oriented evaluation (e.g., profit/cost curves).
