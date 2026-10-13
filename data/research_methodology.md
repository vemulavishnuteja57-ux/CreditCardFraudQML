# Quantum-Enhanced Credit Card Fraud Detection System

## 1. Dataset

The project uses the original credit card fraud dataset containing 284,807 transactions and 30 input features. The target variable is `Class`, where 0 represents legitimate transactions and 1 represents fraudulent transactions.

The dataset contains 492 fraudulent transactions, making fraud detection a highly imbalanced classification problem.

## 2. Data Preprocessing

The dataset was split into training and testing subsets using stratified sampling. StandardScaler was applied using training data to standardize the input features.

For the quantum experiments, Principal Component Analysis (PCA) reduced the 30 input features to four principal components. A smaller sample was selected from the training portion to make quantum circuit simulation computationally manageable.

## 3. Classical Machine Learning Models

Four classical models were developed:

- Logistic Regression
- Random Forest
- XGBoost
- Deep Neural Network (DNN)

These models provide baseline results for evaluating the fraud detection task.

## 4. Hybrid Quantum-Classical Models

Two quantum machine learning approaches were implemented using Qiskit and local circuit simulation.

### 4.1 Quantum Support Vector Machine (QSVM)

QSVM uses a quantum feature map to encode the four PCA components and a fidelity-based quantum kernel to calculate similarities between samples. The resulting kernel is used by a support vector classifier.

### 4.2 Variational Quantum Classifier (VQC)

VQC uses a parameterized quantum circuit and a classical optimization procedure. The circuit parameters are optimized using SPSA to classify transactions into legitimate and fraudulent categories.

## 5. Evaluation Metrics

The models were evaluated using accuracy, fraud precision, fraud recall, fraud F1-score, ROC-AUC, and Average Precision where available.

Fraud recall measures the proportion of actual fraudulent transactions detected. Fraud precision measures the proportion of predicted fraud cases that are genuinely fraudulent. Average Precision is particularly relevant for imbalanced classification.

## 6. Current Experimental Limitations

The classical models were evaluated on a test set containing 56,962 transactions, including 98 fraudulent transactions.

The quantum models were evaluated on a smaller test set of 60 transactions, including 20 fraudulent transactions, selected from a deliberately fraud-enriched sample.

Consequently, the current results do not represent a direct, controlled comparison between classical and quantum models. The quantum test set has a substantially different class distribution, and its small size limits the reliability of performance estimates.

The quantum experiments were performed using local simulation rather than actual quantum hardware. The results therefore do not establish quantum advantage or demonstrate production-level real-time performance.

## 7. Future Work

Future work should include a consistent evaluation protocol, more representative fraud test data, repeated experiments, threshold tuning, training and inference time measurements, and further investigation of fraud detection performance under severe class imbalance.