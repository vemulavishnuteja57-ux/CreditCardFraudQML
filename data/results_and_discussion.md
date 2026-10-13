# Results and Discussion

## 1. Experimental Results

Four classical machine learning models and two hybrid quantum-classical models were evaluated for credit card fraud detection.

The classical models were Logistic Regression, Random Forest, XGBoost, and Deep Neural Network (DNN). The quantum approaches were Quantum Support Vector Machine (QSVM) and Variational Quantum Classifier (VQC).

### 1.1 Classical Model Results

The classification reports produced the following fraud-class results:

| Model | Fraud Precision | Fraud Recall | Fraud F1-score |
|---|---:|---:|---:|
| Logistic Regression | 0.061 | 0.9184 | 0.1144 |
| Random Forest | 0.91 | 0.79 | 0.84 |
| XGBoost | 0.90 | 0.80 | 0.84 |
| DNN | 0.06 | 0.90 | 0.11 |

Logistic Regression and DNN achieved high fraud recall but low fraud precision, indicating that many legitimate transactions were incorrectly flagged as fraudulent. Random Forest and XGBoost provided a better balance between fraud precision and recall in the reported classification results.

The recorded ROC-AUC values were 0.9721 for Logistic Regression, 0.9573 for Random Forest, 0.9601 for XGBoost, and 0.9787 for DNN.

### 1.2 Quantum Model Results

The quantum models were evaluated on a test sample of 60 transactions, including 20 fraudulent transactions.

| Metric | QSVM | VQC |
|---|---:|---:|
| Accuracy | 0.7333 | 0.5000 |
| Fraud Precision | 0.64 | 0.34 |
| Fraud Recall | 0.45 | 0.55 |
| Fraud F1-score | 0.53 | 0.42 |
| ROC-AUC | 0.6725 | 0.6225 |
| Average Precision | 0.5500 | 0.4849 |

On this particular sample, QSVM achieved higher accuracy, fraud precision, fraud F1-score, ROC-AUC, and Average Precision. VQC detected a larger proportion of the fraud cases but also incorrectly flagged more legitimate transactions.

These results describe the current experiment and do not establish that QSVM is universally superior to VQC.

## 2. Discussion

Fraud detection involves a trade-off between detecting fraudulent transactions and minimizing false alerts. Fraud recall is important because missed fraudulent transactions can result in financial losses. Fraud precision is also important because excessive false alerts can inconvenience legitimate customers and increase investigation costs.

The classical results indicate that Random Forest and XGBoost achieved a stronger precision-recall balance than Logistic Regression and DNN in the reported classification results. The quantum results show that QSVM performed better overall than VQC on the selected quantum test sample, while VQC achieved higher fraud recall.

## 3. Limitations

The classical models were evaluated on 56,962 test transactions, including 98 fraud cases. The quantum models were evaluated on only 60 transactions, including 20 fraud cases, selected from a fraud-enriched sample.

The different test-set sizes and class distributions prevent a fair direct comparison of the reported metrics. In addition, the quantum models were run using local simulation. The experiments do not demonstrate quantum advantage, production-level real-time performance, or superiority over classical methods.

Some classical metrics were recovered from rounded classification reports, and not all metrics are currently available at full precision.

## 4. Conclusion

The project implemented four classical machine learning models and two hybrid quantum-classical approaches for credit card fraud detection. The experiments demonstrated how classical preprocessing, PCA, quantum feature maps, quantum kernels, and variational quantum circuits can be combined in a fraud classification workflow.

The current results provide an initial experimental comparison. Further work should use a consistent evaluation protocol, a representative held-out test set, repeated runs, and training and inference time measurements before making claims about the practical benefits of quantum machine learning.