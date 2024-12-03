# dc_crime_.ipynb

## **Project Overview**
This project applies machine learning techniques to predict the safety of a specific location and time in Washington, DC, based on historical crime data. The dataset includes geographical coordinates, time-based features, and offense categories, enabling classification into "Safe" or "Dangerous" zones.

The following models were evaluated for their ability to predict safety:
- Logistic Regression
- Decision Tree
- Random Forest
- K-Nearest Neighbors (KNN)
- XGBoost

This README provides a comprehensive summary of each model, their performance, and the project findings.

---

## **Models and Performance**

### **1. Logistic Regression**
- **Purpose**: Provides a baseline with high interpretability and straightforward implementation.
- **Advantages**:
  - Easy to understand and interpret.
  - Efficient in training and inference.
  - Good for preliminary analysis or feature significance.
- **Disadvantages**:
  - Poor handling of imbalanced datasets.
  - Cannot model complex relationships in the data.

**Performance:**
- **Cross-Validation Accuracy**: 70.07%
- **AUC**: 68.60%
- **Best Use Case**: Real-time, interpretable predictions when simplicity is required.

---

### **2. Decision Tree**
- **Purpose**: Provides interpretable rules for safety predictions.
- **Advantages**:
  - Intuitive and interpretable "if-then" decision rules.
  - Captures non-linear relationships.
  - Better than Logistic Regression for imbalanced datasets.
- **Disadvantages**:
  - Prone to overfitting without proper tuning (e.g., depth limitation).
  - Sensitive to data changes, making it less stable than ensemble methods.

**Performance:**
- **Cross-Validation Accuracy**: 79.49%
- **AUC**: 73.96%
- **Best Use Case**: Interpretable models when feature importance matters.

---

### **3. Random Forest**
- **Purpose**: An ensemble method that reduces overfitting of decision trees while boosting accuracy.
- **Advantages**:
  - Robust and stable.
  - Handles imbalanced datasets effectively.
  - Suitable for noisy or missing data.
- **Disadvantages**:
  - Computationally expensive.
  - Less interpretable compared to single trees.

**Performance:**
- **Cross-Validation Accuracy**: 96.49%
- **AUC**: 74.31%
- **Best Use Case**: Stable predictions for safety-critical applications.

---

### **4. K-Nearest Neighbors (KNN)**
- **Purpose**: Leverages geographic proximity for predictions.
- **Advantages**:
  - No assumptions about data distribution.
  - Suitable for highly spatially correlated features.
- **Disadvantages**:
  - Inefficient for large datasets.
  - Struggles with imbalanced datasets and has lower recall for high-risk areas.

**Performance:**
- **Cross-Validation Accuracy**: 94.87%
- **AUC**: 68.67%
- **Best Use Case**: Useful for geographically localized datasets with small sizes.

---

### **5. XGBoost**
- **Purpose**: A state-of-the-art model optimized for structured data classification.
- **Advantages**:
  - Handles complex relationships and imbalanced data effectively.
  - High recall, making it suitable for high-risk predictions.
  - Scalable and efficient for large datasets.
- **Disadvantages**:
  - Higher computational cost.
  - Requires hyperparameter tuning for optimal performance.

**Performance:**
- **Cross-Validation Accuracy**: 86.19%
- **AUC**: 76.07%
- **Best Use Case**: Ideal for high-stakes applications where false negatives must be minimized.

---

## **Model Comparison**

| **Model**               | **Precision** | **Recall** | **F1-Score** | **AUC**   | **Cross-Validation Accuracy** |
|--------------------------|---------------|------------|--------------|-----------|--------------------------------|
| Logistic Regression      | 82.39%        | 61.68%     | 67.83%       | 68.60%    | 70.07%                         |
| Decision Tree            | 84.45%        | 67.42%     | 72.56%       | 73.96%    | 79.49%                         |
| Random Forest            | 83.49%        | 76.09%     | 78.88%       | 74.31%    | 96.49%                         |
| K-Nearest Neighbors      | 83.14%        | 67.54%     | 72.56%       | 68.67%    | 94.87%                         |
| XGBoost                  | 85.13%        | 60.40%     | 66.68%       | 76.07%    | 86.19%                         |

---

## **Recommendations**
1. **Primary Model**: **XGBoost**
   - Best suited for detecting dangerous zones with high accuracy and recall.
   - Recommended for high-stakes applications where misclassification costs are high.

2. **Secondary Model**: **Random Forest**
   - Provides stable and balanced predictions, suitable for general-purpose safety assessments.

3. **Baseline Model**: **Logistic Regression**
   - Use for quick, interpretable predictions or as a baseline for performance comparison.

---

## **How to Use**
1. **Input Features**: Supply day of the week, time, latitude, longitude, and whether it is a weekend.
2. **Prediction**:
   - The models predict the probability of the location being "Safe" or "Dangerous."
   - Adjust thresholds based on your risk tolerance.
3. **Evaluation**: Use confusion matrices and classification metrics to refine and validate models.

---

By using these models, decision-makers and public safety teams can assess the safety of specific locations in Washington, DC, and plan interventions more effectively. This project demonstrates the practical use of machine learning in enhancing public safety efforts.
