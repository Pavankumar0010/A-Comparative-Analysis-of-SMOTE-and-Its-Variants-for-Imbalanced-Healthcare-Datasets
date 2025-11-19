# A Comparative Analysis of SMOTE and Its Variants for Imbalanced Healthcare Datasets

## 📌 Project Overview
Healthcare datasets commonly suffer from class imbalance, where patients with adverse outcomes form a very small minority. This imbalance often causes machine learning models to favor the majority class, resulting in poor detection of high-risk patients.  

This project presents a comprehensive comparative analysis of **14 SMOTE-based oversampling methods** applied to the **Heart Failure Prediction Dataset**, tested on **10 different classifiers**.  
The objective is to identify which SMOTE variant + classifier combination achieves the best minority-class detection performance.

Our experiments show that **SMOTE + CatBoost** provides the best overall results, offering a strong balance between accuracy, precision, recall, F1-score, ROC-AUC, and PR-AUC.

---

## 📂 Dataset Used
**Heart Failure Prediction Dataset**  
- 12 clinical features  
- Target: Heart failure risk (0 = No, 1 = Yes)  
- Significant class imbalance before oversampling  

---

## ⚙️ Oversampling Methods (14 Variants)
This study evaluates the following **fourteen** SMOTE-based oversampling methods:

1. **SMOTE (Original)**
2. **Borderline-SMOTE 1**
3. **Borderline-SMOTE 2**
4. **ADASYN**
5. **KMeans-SMOTE**
6. **Safe-Level SMOTE**
7. **SVM-SMOTE**
8. **Geometric SMOTE**
9. **Distance-SMOTE**
10. **Cluster-SMOTE**
11. **Polynomial-SMOTE**
12. **Random-SMOTE**
13. **SMOTE + Tomek Links**
14. **SMOTE + ENN (Edited Nearest Neighbors)**

Each method generates synthetic minority samples differently, allowing a full comparison across algorithms.

---

## 🤖 Classifiers Used (10 Models)
Each oversampling technique was paired with these **ten** machine learning models:

- Logistic Regression  
- Decision Tree  
- Random Forest  
- Naïve Bayes  
- K-Nearest Neighbors  
- Support Vector Machine  
- Gradient Boosting  
- XGBoost  
- LightGBM  
- CatBoost  

Each classifier was trained:
1. **Without oversampling (baseline)**  
2. **With all 14 SMOTE variants**

---

## 🧪 Methodology Summary
The analysis follows a structured evaluation pipeline:

1. **Data preprocessing**  
   - Feature encoding  
   - Standardization  
   - Train-test split  

2. **Baseline model performance**  
   - All 10 classifiers tested *without* SMOTE  
   - Performance was poor for the minority class

3. **Oversampling with 14 SMOTE variants**  
   - Applied only on the training set  
   - Synthetic data generated differently for each method  

4. **Model training with each SMOTE variant**  
   - 10 classifiers × 14 SMOTE variants  
   - Total: **140 models trained**

5. **Evaluation metrics**  
   - Accuracy  
   - Precision  
   - Recall  
   - F1-score  
   - ROC-AUC  
   - PR-AUC  

6. **Visualization**  
   - Heatmap comparing all classifier–SMOTE combinations  
   - Before/after class imbalance plots  
   - ROC & PR curves of best model  
   - Confusion matrix  
   - Feature importance (CatBoost)

---

## 📊 Key Results

### 🔹 **Before Oversampling**
- Accuracy was moderate.
- **Recall on minority class was extremely low**, meaning the models failed to detect heart-failure cases.
- Confirms that **oversampling is required**.

### 🔹 **After Applying All SMOTE Variants**
- All models showed significant improvement.
- Borderline-SMOTE variants and Distance-SMOTE performed better for ensemble models.
- ADASYN increased recall but often reduced precision.

### 🏆 **Best Overall Model**
### ⭐ **SMOTE + CatBoost**

| Metric | Score |
|--------|-------|
| Accuracy | **0.88** |
| Precision | **0.80** |
| Recall | **0.86** |
| F1 Score | **0.88** |
| ROC-AUC | **0.93** |
| PR-AUC | **0.92** |

Why it is best:
- Best balance between sensitivity & specificity  
- High recall = detects more true heart-failure patients  
- Stable performance across folds  
- Works well with minor class synthetic distributions  

---

## 📉 Visualizations Provided
This repository contains the following visual outputs:

- Class distribution before SMOTE  
- Class distribution after SMOTE  
- Heatmap of 14 SMOTE methods × 10 classifiers  
- ROC curve of best model (SMOTE + CatBoost)  
- PR curve  
- Confusion matrix  
- Feature importance plot  

These support a complete understanding of model behavior.
