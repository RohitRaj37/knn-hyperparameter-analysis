#  KNN Hyperparameter Analysis: Bias-Variance Tradeoff Study

##  Overview

This project performs an **empirical analysis of the K-Nearest Neighbors (KNN) algorithm**, focusing on how the hyperparameter **K (number of neighbors)** impacts model performance, generalization, and the bias-variance tradeoff.

Unlike basic implementations, this project emphasizes **experimentation, visualization, and interpretation** of results.

---

##  Objective

* Analyze how varying **K** affects model accuracy
* Understand the **bias-variance tradeoff** in KNN
* Study the impact of **feature scaling** on distance-based models
* Compare different **distance metrics**

---

##  Dataset

* **Breast Cancer Wisconsin Dataset** (from `scikit-learn`)
* Binary classification problem:

  * `0` → Malignant
  * `1` → Benign

---

##  Methodology

### 1. Data Preprocessing

* Train-test split (80-20)
* Feature scaling using **StandardScaler**
* Scaling is critical because KNN relies on distance calculations

---

### 2. Model Training

* Used **KNeighborsClassifier** from `scikit-learn`
* Evaluated K values in range **1 to 30**
* Applied **5-fold cross-validation** for reliable performance estimation

---

### 3. Experiments Conducted

####  Accuracy vs K

* Measured training and validation accuracy across different K values
* Observed performance trends

####  Error vs K

* Computed error as:
  `Error = 1 - Accuracy`
* Helps visualize model performance more clearly

####  Distance Metric Comparison

* Compared:

  * Euclidean distance
  * Manhattan distance
* Evaluated their effect on model accuracy

####  Feature Scaling Impact

* Compared model performance:

  * With scaling
  * Without scaling
* Demonstrated the importance of normalization in KNN

---

##  Results & Observations

* **Small K (1–3):**

  * High training accuracy
  * Low validation accuracy
  *  Indicates **overfitting (high variance)**

* **Moderate K (5–10):**

  * Balanced training and validation accuracy
  *  Best generalization performance

* **Large K (>15):**

  * Lower accuracy overall
  *  Indicates **underfitting (high bias)**

* **Feature Scaling:**

  * Significantly improves model performance
  * Prevents features with large values from dominating distance calculations

* **Distance Metrics:**

  * Euclidean and Manhattan show slight variation
  * Choice of metric can impact performance depending on dataset

---

##  Key Insights

* KNN performance is highly sensitive to the choice of **K**
* There exists an **optimal K** that balances bias and variance
* **Feature scaling is essential** for distance-based algorithms
* Cross-validation provides more reliable evaluation than a single split

---

##  Final Model

* Selected optimal K based on highest cross-validation accuracy
* Evaluated on test set using:

  * Accuracy
  * Confusion Matrix
  * Classification Report

---

##  Project Structure

```
knn-hyperparameter-analysis/
├── knn_analysis.ipynb
├── README.md
└── requirements.txt
```

---

##  How to Run

1. Clone the repository:

   ```
    git clone <your-repo-link>
   ```

2. Install dependencies:

   ```
    pip install -r requirements.txt
   ```

3. Run the notebook:

   ```
    jupyter notebook knn_analysis.ipynb
   ```

---

## 📌 Conclusion

This project highlights that **model performance is not just about choosing an algorithm, but tuning it correctly**.
The choice of K, proper scaling, and evaluation strategy significantly impact the effectiveness of KNN.

---
