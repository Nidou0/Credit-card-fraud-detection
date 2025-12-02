End-to-end credit card fraud detection project that takes you from raw, massively imbalanced transaction data all the way to tuned, production-ready machine learning models.

This repo walks through the full pipeline:

🧠 Problem framing & data understanding – fraud vs. non-fraud as a rare-event classification problem on an anonymized credit card transactions dataset (V1–V28 PCA features, Time, Amount) with extreme class imbalance.

🔍 Exploratory data analysis (EDA) – class distribution, feature stats, correlation heatmaps, and distribution plots to see how fraud differs from normal behaviour.

🧪 Data preprocessing & imbalance handling – robust scaling for key features, careful train–test splitting, and SMOTE to synthesize minority (fraud) cases without leaking test information.

🤖 Model building & tuning – three supervised models implemented and compared:

Decision Tree as an interpretable baseline

Random Forest for strong, stable performance

XGBoost for aggressive fraud catching on tabular data
All tuned with GridSearchCV to squeeze out better performance on the minority class.

📊 Evaluation focused on what actually matters – confusion matrices, precision, recall, F1-score, ROC-AUC and class-specific metrics, with a clear focus on not missing fraud while controlling false alarms.

In the final comparison, Random Forest delivers the most balanced performance (solid F1 on fraud), XGBoost pushes recall to catch more fraudulent transactions at the cost of precision, and the Decision Tree remains useful for quick interpretation and rule extraction.
