# Hybrid Quantum-Classical Credit Card Fraud Detection

## Project Overview

This project explores classical machine learning and quantum machine learning techniques for credit card fraud detection. It compares four classical models with two quantum machine learning models.

## Models Used

### Classical Models
- Logistic Regression
- Random Forest
- XGBoost
- Deep Neural Network (DNN)

### Quantum Models
- Quantum Support Vector Classifier (QSVM)
- Variational Quantum Classifier (VQC)

## Dataset

The project uses the Credit Card Fraud Detection dataset containing 284,807 transactions, including 492 fraudulent transactions.

The target column is `Class`:
- `0` — Legitimate transaction
- `1` — Fraudulent transaction

## Methodology

1. Load and explore the dataset.
2. Split the data into training and testing sets.
3. Scale features and apply Principal Component Analysis (PCA).
4. Train and evaluate classical machine learning models.
5. Prepare a reduced dataset for quantum machine learning.
6. Train and evaluate QSVM and VQC.
7. Compare model performance using fraud precision, recall, F1-score, ROC-AUC, and Average Precision where available.

## Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- XGBoost
- TensorFlow/Keras
- Qiskit
- Qiskit Machine Learning
- Matplotlib
- Jupyter Notebook

## Results and Limitations

The classical and quantum models were evaluated using different test sets. The quantum models used a smaller, fraud-enriched sample to make quantum simulation computationally manageable.

Therefore, the current results do not establish a fair head-to-head comparison or demonstrate quantum advantage.

## Project Structure

```text
CreditCardFraudQML/
├── data/
│   └── creditcard.csv
├── notebooks/
│   ├── fraud_detection.ipynb
│   ├── qsvm_results.csv
│   ├── quantum_model_comparison.csv
│   └── model_results/
├── research_methodology.md
├── results_and_discussion.md
└── README.md
```

## Future Improvements

- Evaluate all models on a comparable test set.
- Improve fraud detection using class-imbalance handling and threshold tuning.
- Measure training and prediction times.
- Investigate quantum models using larger samples or quantum hardware when feasible.
