# Quantum-Enhanced Credit Card Fraud Detection: A Hybrid Quantum-Classical Study

## 1. Abstract
Credit card fraud detection is a challenging machine learning problem because fraudulent transactions represent only a small fraction of all transactions. This study explores a hybrid quantum-classical approach by comparing classical machine learning and deep learning models with quantum machine learning classifiers. The classical models include Logistic Regression, Random Forest, XGBoost, and a Deep Neural Network (DNN), while the quantum models include a Quantum Support Vector Classifier (QSVM) and a Variational Quantum Classifier (VQC).

The experiments use the Credit Card Fraud Detection dataset. The classical models are evaluated on the original stratified test set, while the quantum models are evaluated on a smaller, fraud-enriched sample to make quantum simulation computationally manageable. Performance is assessed using fraud precision, recall, F1-score, ROC-AUC, and Average Precision where available.

Among the classical models, the DNN achieved a ROC-AUC of approximately 0.9787, while Logistic Regression achieved approximately 0.9721. On the quantum test set, QSVM achieved a ROC-AUC of 0.6725, and VQC achieved 0.6225. Because the classical and quantum models were evaluated on different test sets, their results cannot be interpreted as a direct, fair performance comparison. The experiments demonstrate the implementation of classical and quantum classifiers for fraud detection, but do not establish a quantum advantage or production-ready real-time performance.

Future work will focus on evaluating the models on comparable test sets, improving fraud detection metrics, and investigating the scalability and practical applicability of quantum machine learning.

## 2. Introduction
Credit card payments have become an essential part of modern financial systems. As transaction volumes increase, detecting fraudulent activities accurately and efficiently becomes an important challenge. Fraudulent transactions are relatively rare compared with legitimate transactions, creating a highly imbalanced classification problem. This imbalance can make it difficult for machine learning models to identify fraudulent transactions while minimizing false alarms.

Machine learning techniques provide methods for identifying suspicious transaction patterns from historical data. Classical approaches such as Logistic Regression, Random Forest, and XGBoost can learn patterns from transaction features. Deep learning models, including Deep Neural Networks (DNNs), can also be used to identify complex relationships in the data.

Quantum machine learning is an emerging research area that combines concepts from quantum computing and machine learning. Quantum classifiers, including Quantum Support Vector Classifiers (QSVMs) and Variational Quantum Classifiers (VQCs), use parameterized quantum circuits or quantum kernels to process encoded features. These methods are being investigated for their potential applications in classification problems, although their practical benefits depend on the dataset, implementation, computational cost, and evaluation methodology.

This project investigates classical and quantum machine learning models for credit card fraud detection. It implements four classical models and two quantum models, evaluates their classification performance, and discusses the limitations of comparing models trained and tested on datasets of different sizes and class distributions. The goal is to conduct an experimental comparison rather than assume that quantum methods provide better performance.

## 3. Problem Statement and Objectives

### 3.1 Problem Statement

Credit card fraud detection is challenging because fraudulent transactions form a very small proportion of the total transaction volume. A useful detection system must identify fraudulent transactions while controlling false positives, since incorrectly flagging legitimate transactions can inconvenience customers and require additional investigation.

This research investigates the application of classical machine learning, deep learning, and quantum machine learning classifiers to credit card fraud detection. It examines their observed performance using the available experimental results and considers the limitations of evaluating classical models on the original test set and quantum models on a smaller, fraud-enriched test set.

### 3.2 Objectives

The main objectives of this project are:

1. To preprocess transaction data and address feature dimensionality using scaling and Principal Component Analysis (PCA).
2. To implement and evaluate Logistic Regression, Random Forest, XGBoost, and a Deep Neural Network.
3. To implement a Quantum Support Vector Classifier (QSVM) using a quantum kernel.
4. To implement a Variational Quantum Classifier (VQC) using a parameterized quantum circuit.
5. To evaluate the models using metrics such as fraud precision, recall, F1-score, ROC-AUC, and Average Precision where available.
6. To document the experimental results and limitations of comparing models evaluated on different test sets.
7. To identify future improvements for fair evaluation, scalability, and potential real-time fraud detection applications.

### 3.3 Research Scope

This project is an experimental study using classical machine learning and quantum circuit simulation. It does not establish a quantum advantage, and the current implementation has not demonstrated deployment in a live payment-processing environment.

## 4. Literature Review

### 4.1 Classical Machine Learning for Credit Card Fraud Detection

Classical machine learning is widely investigated for detecting fraudulent financial transactions. Algorithms such as Logistic Regression, Support Vector Machines, Random Forest, and gradient-boosting methods learn patterns from labeled transaction data. However, credit card fraud datasets often contain far fewer fraudulent transactions than legitimate ones. Consequently, accuracy alone may not adequately describe a model's ability to detect fraud. Precision, recall, F1-score, ROC-AUC, and Average Precision provide additional information about classification performance.

Recent comparative research has evaluated several supervised and unsupervised learning algorithms for fraud detection, including Random Forest and XGBoost. Such studies emphasize the importance of consistent evaluation procedures and metrics suitable for imbalanced datasets [1].

### 4.2 Quantum Kernel Methods

Quantum kernel methods investigate whether quantum circuits can represent classical input data in feature spaces that are useful for machine learning. In a quantum-kernel approach, a feature map encodes input data into quantum states, and similarities between these states are used to construct a kernel matrix. This matrix can then be used by a support vector classifier.

The Qiskit Machine Learning documentation describes how fidelity-based quantum kernels can be integrated with support vector classification. It also provides implementation examples for building quantum feature maps and evaluating classification performance [2].

In this project, a Quantum Support Vector Classifier (QSVM) is implemented using a four-feature representation derived from Principal Component Analysis (PCA). The features are scaled for quantum encoding, and a quantum kernel is used for classification. This experiment investigates the practical implementation of a quantum-kernel classifier on a reduced dataset.

### 4.3 Variational Quantum Classifiers

Variational Quantum Classifiers (VQCs) use parameterized quantum circuits together with a classical optimization procedure. Classical input features are encoded into a quantum circuit, trainable circuit parameters are adjusted during optimization, and measurement outcomes are used to produce classification predictions.

Atban, Küçükkara, and Bayılmış (2025) investigated VQC-based credit card fraud detection combined with feature-selection techniques and data-balancing methods. Their study evaluated different feature-selection approaches, including particle swarm optimization, ant colony optimization, atom search optimization, and a conventional feature-selection method [3].

This research illustrates that VQC performance depends on more than the quantum circuit alone. Feature selection, data preprocessing, class balancing, and evaluation design can all influence reported results. Results from different studies should therefore be interpreted in the context of their datasets and experimental settings.

### 4.4 Research Gap and Motivation

The reviewed work shows that both classical machine learning and quantum machine learning are being investigated for fraud detection. However, reported performance cannot be compared reliably when studies use different datasets, preprocessing techniques, class distributions, evaluation metrics, or test sets.

This project implements four classical models—Logistic Regression, Random Forest, XGBoost, and a Deep Neural Network—and two quantum models, QSVM and VQC. Its contribution is an experimental implementation and documentation of these approaches using a common source dataset, together with an explicit discussion of the limitations of the current evaluation.

The classical models were evaluated on a large stratified test set, whereas the quantum models were evaluated on a much smaller, fraud-enriched test set. Therefore, this study does not claim a direct performance advantage for either model family. A future experiment using comparable held-out data and a consistent evaluation protocol would provide a stronger basis for comparison.

### References

[1] IEEE Xplore. (2026). *Supervised and Unsupervised approach of Machine Learning: A Comparative Study for Credit Card Fraud Detection Across Diverse Datasets.* [https://ieeexplore.ieee.org/abstract/document/11656590/](https://ieeexplore.ieee.org/abstract/document/11656590/)

[2] Qiskit Machine Learning. *Quantum Kernel Machine Learning: Tutorial.* [https://qiskit-community.github.io/qiskit-machine-learning/tutorials/03_quantum_kernel.html](https://qiskit-community.github.io/qiskit-machine-learning/tutorials/03_quantum_kernel.html)

[3] Atban, F., Küçükkara, M. Y., & Bayılmış, C. (2025). *Enhancing variational quantum classifier performance with meta-heuristic feature selection for credit card fraud detection.* The European Physical Journal Special Topics, 234, 3705–3718. [https://doi.org/10.1140/epjs/s11734-025-01703-y](https://doi.org/10.1140/epjs/s11734-025-01703-y)


## 5. Dataset Description

### 5.1 Dataset Overview

This project uses the Credit Card Fraud Detection dataset, which contains European cardholder transactions made over a two-day period in September 2013. The dataset contains 284,807 transactions, of which 492 are labeled as fraudulent. Fraudulent transactions account for approximately 0.172% of the total, making the dataset highly imbalanced.

Each transaction contains 30 input features and one target label. The input features include `Time`, `Amount`, and anonymized principal components `V1` through `V28`. The target column, `Class`, indicates whether a transaction is legitimate or fraudulent.

- `Class = 0`: Legitimate transaction
- `Class = 1`: Fraudulent transaction

### 5.2 Dataset Challenges

The small proportion of fraudulent transactions creates a class-imbalance problem. A model that predicts most transactions as legitimate may achieve high overall accuracy while failing to identify a substantial proportion of fraud cases. Therefore, fraud precision, recall, F1-score, ROC-AUC, and Average Precision are important evaluation metrics.

### 5.3 Data Preparation

For the classical experiments, the dataset was divided into training and testing sets using an 80:20 stratified split. Feature scaling was applied using statistics learned from the training data.

For the quantum experiments, the standardized features were reduced to four dimensions using Principal Component Analysis (PCA). A smaller training-derived sample containing 100 fraudulent and 200 legitimate transactions was then prepared to make quantum simulation computationally manageable. This sample was split into training and testing subsets, and its features were scaled to the range from 0 to π for quantum circuit encoding.

The quantum test set contained 60 transactions, including 20 fraudulent and 40 legitimate transactions. This differs substantially from the original dataset's fraud proportion and must be considered when interpreting the results.

### 5.4 Dataset Availability

The original dataset is available through Kaggle's Credit Card Fraud Detection dataset page:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset is excluded from the GitHub repository because the CSV file exceeds GitHub's standard 100 MB file-size limit. It remains available in the local project folder for running the notebook.

## 6. Proposed Methodology

### 6.1 Overall Workflow

The proposed workflow consists of data preparation, feature transformation, classical model training, quantum model training, and performance evaluation. Classical models use the original stratified train-test split, while quantum models use a reduced dataset to make circuit simulation more manageable.

### 6.2 Data Preprocessing

The dataset is loaded using Pandas and separated into input features and the target variable `Class`. The data is divided into training and testing sets using stratified sampling to preserve the class distribution.

Feature scaling is performed using a scaler fitted on the training data, which is then applied to the test data. Principal Component Analysis (PCA) reduces the feature representation to four components for the quantum experiments. The PCA transformation is fitted on the training data to avoid using test-set information during fitting.

### 6.3 Classical Machine Learning Models

Four classical models are implemented:

1. **Logistic Regression:** A supervised classification algorithm that estimates the probability of a transaction belonging to the fraud class.
2. **Random Forest:** An ensemble method that combines predictions from multiple decision trees.
3. **XGBoost:** A gradient-boosting method that builds an ensemble of trees sequentially to improve predictive performance.
4. **Deep Neural Network (DNN):** A neural network that learns nonlinear relationships between input features through trainable layers.

These models are evaluated on the original stratified test set containing 56,962 transactions, including 98 fraudulent transactions.

### 6.4 Quantum Support Vector Classifier (QSVM)

The QSVM uses a quantum feature map to encode four PCA-transformed features into a quantum circuit. A fidelity-based quantum kernel measures similarity between encoded data points. The resulting kernel is used by a support vector classifier to distinguish fraudulent and legitimate transactions.

The quantum feature map uses four qubits and two repetitions. The quantum experiment uses a reduced sample of 300 transactions, selected from the training data, with 100 fraudulent and 200 legitimate transactions. This reduces the computational cost of evaluating the quantum kernel.

### 6.5 Variational Quantum Classifier (VQC)

The VQC uses a parameterized quantum circuit and a classical optimizer to learn a classification function. Four PCA features are encoded using the same quantum feature map used in the QSVM experiment. A RealAmplitudes ansatz with four qubits and one repetition provides trainable circuit parameters.

The classifier is trained using the Simultaneous Perturbation Stochastic Approximation (SPSA) optimizer with a maximum of 20 iterations. The trained classifier is evaluated on the quantum test set.

### 6.6 Evaluation Metrics

The experiments use the following metrics where available:

- **Precision:** The proportion of predicted fraudulent transactions that are actually fraudulent.
- **Recall:** The proportion of actual fraudulent transactions detected by the model.
- **F1-score:** The harmonic mean of precision and recall.
- **ROC-AUC:** Measures the model's ability to rank positive and negative examples across classification thresholds.
- **Average Precision:** Summarizes the precision-recall curve.
- **Accuracy:** The proportion of all predictions classified correctly.

Because fraud is rare, accuracy is interpreted alongside fraud-specific metrics. The different test sets used in the classical and quantum experiments are explicitly considered when discussing the results.

## 7. Experimental Setup

### 7.1 Software and Libraries

The experiments were developed in Python using Jupyter Notebook within Visual Studio Code. The implementation uses the following libraries:

- Pandas and NumPy for data handling and numerical operations.
- Scikit-learn for preprocessing, PCA, classical classifiers, and evaluation metrics.
- XGBoost for gradient-boosted tree classification.
- TensorFlow/Keras for the Deep Neural Network.
- Qiskit and Qiskit Machine Learning for quantum circuit simulation, quantum kernels, and quantum classifiers.
- Matplotlib for generating result visualizations.

### 7.2 Classical Experiment Configuration

The classical experiments use an 80:20 stratified train-test split of the original dataset. The test set contains 56,962 transactions, including 98 fraudulent transactions. Feature scaling is fitted on the training data and applied to the test data.

The evaluated classical models are Logistic Regression, Random Forest, XGBoost, and a Deep Neural Network. Their performance is assessed using classification metrics and ROC-AUC.

### 7.3 Quantum Experiment Configuration

The quantum experiments use four PCA components and a reduced sample of 300 transactions: 100 fraudulent and 200 legitimate transactions selected from the training data. The reduced sample is divided into 240 training transactions and 60 testing transactions. The quantum test set contains 20 fraudulent and 40 legitimate transactions.

The four quantum input features are scaled to the range [0, π] for circuit encoding.

The QSVM uses a four-dimensional ZZFeatureMap with two repetitions and a fidelity-based quantum kernel. The VQC uses the same feature map, a four-qubit RealAmplitudes ansatz with one repetition, and the SPSA optimizer configured for a maximum of 20 iterations.

### 7.4 Simulation Environment

The quantum classifiers were evaluated using local quantum simulation rather than a demonstrated deployment on physical quantum hardware. The reported results therefore describe the behavior of the implemented models under the experimental setup, not the performance of a live payment-processing system.

### 7.5 Evaluation Considerations

The classical and quantum experiments use different test-set sizes and class distributions. Consequently, their metrics should not be interpreted as a direct, controlled comparison. A future evaluation should use a common held-out test set, consistent preprocessing, and the same evaluation metrics for all models.

## 8. Results and Discussion

### 8.1 Classical Model Results

Four classical models were evaluated on the original stratified test set containing 56,962 transactions, including 98 fraudulent transactions.

| Model | Fraud Precision | Fraud Recall | Fraud F1-score | ROC-AUC |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.061 | 0.9184 | 0.1144 | 0.9721 |
| Random Forest | 0.91 | 0.79 | 0.84 | 0.9573 |
| XGBoost | 0.90 | 0.80 | 0.84 | 0.9601 |
| Deep Neural Network | 0.06 | 0.90 | 0.11 | 0.9787 |

The Deep Neural Network achieved the highest recorded ROC-AUC of approximately 0.9787, followed by Logistic Regression at approximately 0.9721. These values indicate strong ranking performance on the classical test set, although ROC-AUC alone does not establish practical fraud detection effectiveness.

Random Forest and XGBoost achieved higher fraud precision and F1-scores than Logistic Regression and the DNN at their evaluated classification thresholds. Logistic Regression and the DNN detected a high proportion of fraudulent transactions but also produced many false-positive predictions, resulting in low fraud precision.

### 8.2 Quantum Model Results

The quantum models were evaluated on a smaller test set of 60 transactions, containing 20 fraudulent and 40 legitimate transactions.

| Metric | QSVM | VQC |
|---|---:|---:|
| Accuracy | 0.7333 | 0.5000 |
| Fraud Precision | 0.64 | 0.34 |
| Fraud Recall | 0.45 | 0.55 |
| Fraud F1-score | 0.53 | 0.42 |
| ROC-AUC | 0.6725 | 0.6225 |
| Average Precision | 0.5500 | 0.4849 |

The QSVM achieved an accuracy of approximately 73.33% and a fraud F1-score of 0.53. The VQC achieved an accuracy of 50% and a fraud recall of 0.55. In this experiment, the QSVM had higher precision, F1-score, ROC-AUC, and Average Precision, while the VQC detected a greater proportion of the fraudulent transactions in its test set.

These results describe the behavior of the two quantum models under the chosen experimental configuration. They do not establish that QSVM is generally superior to VQC.

### 8.3 Interpretation of Results

The classical and quantum results cannot be compared as a fair head-to-head benchmark because their test sets differ substantially in size and fraud proportion. The classical test set contains 98 fraudulent transactions among 56,962 transactions, whereas the quantum test set contains 20 fraudulent transactions among 60 transactions.

The quantum test set is fraud-enriched, so metrics such as precision, accuracy, and Average Precision may behave differently from metrics measured on the original transaction distribution. The results should therefore be interpreted within each experiment rather than used to claim that one model family outperforms another.

### 8.4 Overall Findings

The experiments demonstrate the implementation of four classical classifiers and two quantum classifiers for credit card fraud detection. Classical models achieved high ROC-AUC values on the original test set, while the quantum models produced measurable classification results on a reduced dataset.

The study also highlights the importance of consistent evaluation, appropriate metrics for imbalanced data, and careful interpretation of results from quantum simulations. No quantum advantage has been established by these experiments.

## 9. Limitations

This study has several limitations.

1. **Different test sets:** Classical models were evaluated on 56,962 transactions, whereas quantum models were evaluated on only 60 transactions. Their reported metrics are therefore not directly comparable.

2. **Fraud-enriched quantum sample:** The quantum experiment used a reduced sample containing 100 fraudulent and 200 legitimate transactions. This differs from the original dataset's highly imbalanced distribution and may affect the interpretation of precision and other metrics.

3. **Limited quantum feature representation:** The quantum classifiers used only four PCA components. These components may not preserve all information relevant to fraud detection.

4. **Simulation constraints:** The quantum models were evaluated using local simulation. Performance on a physical quantum computer was not established.

5. **Limited VQC optimization:** The VQC optimizer was configured for a maximum of 20 iterations. Additional experiments may be needed to investigate convergence and sensitivity to hyperparameters.

6. **No demonstrated real-time deployment:** The project evaluates models offline and does not demonstrate integration with a live payment-processing system, production latency, or operational reliability.

7. **Dataset scope:** The experiments use a single historical dataset. Results may not generalize to other banks, transaction populations, or changing fraud patterns.

These limitations mean that the current work should be treated as an experimental comparison of implemented approaches rather than evidence of production readiness or quantum advantage.

## 10. Conclusion

This project investigated classical machine learning, deep learning, and quantum machine learning techniques for credit card fraud detection. Logistic Regression, Random Forest, XGBoost, and a Deep Neural Network were implemented alongside a Quantum Support Vector Classifier and a Variational Quantum Classifier.

Among the classical models, the DNN achieved the highest recorded ROC-AUC of approximately 0.9787 on the original stratified test set. Random Forest and XGBoost achieved higher fraud precision and F1-scores than Logistic Regression and the DNN at the evaluated classification thresholds. On the reduced quantum test set, QSVM achieved an ROC-AUC of 0.6725, while VQC achieved 0.6225.

Because the classical and quantum models were evaluated on different test sets, these results do not provide a fair direct comparison between the two model families. The experiments demonstrate the practical implementation of quantum-kernel and variational classification approaches using a reduced feature representation, but they do not establish a quantum advantage.

Overall, the project provides a foundation for further investigation into hybrid quantum-classical fraud detection. More rigorous evaluation using comparable test sets, consistent metrics, and realistic transaction distributions is needed before drawing conclusions about practical benefits.

## 11. Future Work

Several improvements can extend this research.

1. **Fair model comparison:** Evaluate classical and quantum models on a common held-out test set with the same class distribution and evaluation metrics.

2. **Improved imbalance handling:** Investigate class weighting, carefully applied resampling techniques, and decision-threshold tuning to improve fraud detection while controlling false positives.

3. **Expanded feature analysis:** Evaluate the effect of different numbers of PCA components and alternative feature-selection methods.

4. **Quantum model optimization:** Experiment with quantum feature maps, circuit depth, ansatz design, optimizer settings, and multiple random seeds.

5. **Computational cost analysis:** Measure training time, inference time, and resource requirements for each model using a consistent experimental setup.

6. **Robust evaluation:** Report confusion matrices, precision-recall curves, confidence intervals where appropriate, and repeated-run results.

7. **Real-time system development:** If model performance and latency become suitable, investigate an architecture for streaming transaction processing, model serving, and fraud alerts.

8. **Quantum hardware investigation:** Explore execution on available quantum hardware and assess the effects of noise, circuit limitations, and hardware access constraints.

These steps would provide a stronger basis for evaluating the practical usefulness and scalability of quantum machine learning in fraud detection.

## 12. References

1. ULB Machine Learning Group and Worldline. *Credit Card Fraud Detection Dataset*. Kaggle. https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

2. Qiskit Machine Learning. *Quantum Kernel Machine Learning Tutorial*. https://qiskit-community.github.io/qiskit-machine-learning/tutorials/03_quantum_kernel.html

3. Atban, F., Küçükkara, M. Y., & Bayılmış, C. (2025). *Enhancing variational quantum classifier performance with meta-heuristic feature selection for credit card fraud detection*. The European Physical Journal Special Topics, 234, 3705–3718. https://doi.org/10.1140/epjs/s11734-025-01703-y

4. IEEE Xplore. *Supervised and Unsupervised approach of Machine Learning: A Comparative Study for Credit Card Fraud Detection Across Diverse Datasets*. https://ieeexplore.ieee.org/abstract/document/11656590/

**Note:** Verify the bibliographic details and relevance of each reference against the original publication before submitting the report. Add any additional papers used in your literature review.