# Breast Cancer Classification using Machine Learning & PCA

## Project Overview
This project focuses on detecting breast cancer tumors as benign (0) or malignant (1) using machine learning classification models. The pipeline includes end-to-end data cleaning, imputation, outlier handling, feature scaling, PCA-based dimensionality reduction, model training, evaluation, and model comparison with practical clinical considerations.

## Dataset Summary
- Total Rows (raw): 699  
- After cleaning & deduplication: 459  
- Total Features: 9 numeric + 1 target  

### Key Features
- Clump Thickness  
- Uniformity of Cell Size  
- Uniformity of Cell Shape  
- Marginal Adhesion  
- Single Epithelial Cell Size  
- Bare Nuclei  
- Bland Chromatin  
- Normal Nucleoli  
- Mitoses  
- Class → Target (Binary)
  - Benign: 0
  - Malignant: 1

## Data Cleaning & Preprocessing
- Removed ID column  
- Removed 240 duplicate entries  
- Replaced invalid tokens (`#, ?, *, etc.`)  
- Converted object columns to numeric  
- Imputed missing values using median strategy to avoid bias  
- Used StandardScaler for feature normalization  
- Verified no negative values after cleaning  

## Dimensionality Reduction — PCA
PCA applied to reduce noise and improve model stability.

- Original features: 9  
- Selected components: 6  
- Variance retained: **91.14%**

### PCA Feature Contributions
| Component | Major contributing original features |
|----------|---------------------------------------|
| PC0 | Cell Size, Cell Shape, Normal Nucleoli |
| PC1 | Mitoses |
| PC2 | Clump Thickness |
| PC3 | Bare Nuclei |
| PC4 | Bland Chromatin, Epithelial Cell Size |
| PC5 | Normal Nucleoli |

## Models Trained & Evaluated
- Logistic Regression  
- KNN  
- Naive Bayes  
- Decision Tree (with tuning)  
- Random Forest (with tuning)

## Model Performance & Real-world Considerations
While multiple models performed well, the Random Forest classifier achieved **100% accuracy on test data**. However, in real-world clinical applications, such perfect accuracy commonly indicates **overfitting** due to dataset limitations.

Therefore, the model selection prioritizes:
- stability  
- generalization  
- interpretability  
- explainable medical decision support  

### Final Recommended Model  
✔ **Logistic Regression (~98% accuracy)**  
- Highly interpretable  
- Clinically explainable  
- Better generalization stability  
- Lower risk of overfitting  

### Comparison Table

| Model | Test Accuracy | Notes |
|------|--------------|------|
| Logistic Regression | 97–98% | Best for clinical interpretability |
| KNN | 98–99% | Strong performance with proximity-based classification |
| Naive Bayes | 94–96% | Fast but less accurate |
| Decision Tree | 97–98% | Good interpretability |
| Random Forest | 100% | Likely overfitted — not used in final deployment |

---

## Train-Test Split
- Train: 80%
- Test: 20%
- Random State: 5  

## Tools & Libraries Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn
- Jupyter Notebook

  ---
  
## Key Insights & Learnings
- Strong correlation between cell uniformity & malignancy probability  
- PCA helped reduce feature redundancy while preserving variance  
- Interpretable models are crucial in healthcare  
- Model confidence & ROC-AUC analysis more meaningful than accuracy alone  
- Transparency > brute accuracy for clinical trustworthiness  

---

## Repository Structure
cancer.csv  
cancer_classification.ipynb  
README.md

---

## Conclusion
Although some models achieved perfect accuracy on test data, interpretability and generalization were prioritized.
Logistic Regression was chosen as the best balanced model for practical classification due to robustness, transparency, and near-optimal accuracy.

---

## Author
**Sumit Pant**  
📧 Email: sumitpant2004@gmail.com  
🐙 GitHub: https://github.com/sumitpant13  
🔗 LinkedIn: https://linkedin.com/in/sumitpant13
