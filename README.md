# Model Performance Report

## Summary of Model Performance

| Model          | Accuracy | Precision (Class 1) | Recall (Class 1) | F1-score (Class 1) |
|---------------|----------|--------------------|------------------|------------------|
| Naïve Bayes  | 0.97     | 1.00               | 0.91             | 0.95             |
| KNN           | 0.97     | 1.00               | 0.91             | 0.95             |
| Decision Tree | 1.00     | 1.00               | 1.00             | 1.00             |

---

## Confusion Matrix Analysis

The confusion matrix helps analyze true/false positives and negatives:

| Model          | TP (1→1) | FP (0→1) | FN (1→0) | TN (0→0) |
|---------------|-------------|-------------|-------------|-------------|
| Naïve Bayes  | 10          | 0           | 1           | 29          |
| KNN           | 10          | 0           | 1           | 29          |
| Decision Tree | 11          | 0           | 0           | 29          |

- **True Positive (TP)**: Correctly classified fast deliveries  
- **False Positive (FP)**: Incorrectly classified delayed as fast  
- **False Negative (FN)**: Incorrectly classified fast as delayed  
- **True Negative (TN)**: Correctly classified delayed deliveries  

---

## Detailed Model Insights

### Naïve Bayes Classifier

✅ **Strengths:**  
- High accuracy (97%)  
- Perfect precision for fast deliveries (1.00)  
- Good recall (0.91)  

⚠ **Weaknesses:**  
- One fast delivery was misclassified as delayed (FN = 1)  

---

### K-Nearest Neighbors (KNN)

✅ **Strengths:**  
- Performance is identical to Naïve Bayes (97% accuracy)  
- Perfect precision (1.00) for fast deliveries  

⚠ **Weaknesses:**  
- Like Naïve Bayes, one fast delivery was misclassified as delayed  

---

### Decision Tree

✅ **Strengths:**  
- Perfect accuracy (1.00)  
- No misclassifications (all predictions correct)  

⚠ **Potential Concern:**  
- The model might be overfitting since real-world scenarios rarely give 100% accuracy.  

---

## Actionable Insights & Recommendations

### 1. Best Model Choice:
- **Decision Tree performs the best** but might be overfitting.
- **If interpretability is needed**, Naïve Bayes or KNN is a better choice.

### 2. Check for Overfitting:
- Perform **cross-validation** to confirm the Decision Tree's generalization ability.

### 3. Further Tuning:
- **For Decision Tree**: Adjust `max_depth` and `min_samples_split` to avoid overfitting.
- **For KNN**: Try different values of **K (number of neighbors)**.

---

## How to Run the Models

1. Install required libraries:
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn
   ```

2. Load and preprocess the dataset.
3. Train the models using Scikit-learn.
4. Evaluate using accuracy, precision, recall, and F1-score.
5. Visualize results using confusion matrix and ROC curve.

---

## Conclusion

This report provides an overview of three classification models for predicting delivery times. The Decision Tree achieved perfect accuracy but may need tuning to avoid overfitting. Naïve Bayes and KNN offer slightly lower accuracy but remain reliable and interpretable options. Future improvements could include additional feature engineering and hyperparameter optimization.

---

