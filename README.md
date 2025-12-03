# Breast Cancer Classification — Machine Learning & PCA-based Diagnosis

## Project Overview
This project focuses on detecting breast cancer tumors as benign (0) or malignant (1) using supervised machine learning models. The workflow includes full data cleaning, preprocessing, PCA dimensionality reduction, model training, evaluation, and final clinically realistic model selection. The goal is not just maximum accuracy, but medically sound interpretability and reliability.

## Dataset Summary
- Original Dataset Size: 699 records  
- After cleaning & deduplication: 459 records  
- Features: 9 biological measurements + 1 target variable  
- Target:
  - 0 = Benign (Non-cancerous)
  - 1 = Malignant (Cancerous)

### Main Features
- Clump Thickness  
- Cell Size  
- Cell Shape  
- Marginal Adhesion  
- Single Epithelial Cell Size  
- Bare Nuclei  
- Bland Chromatin  
- Normal Nucleoli  
- Mitoses  

## Data Cleaning & Preparation
- Removed ID column  
- Replaced invalid string symbols (?, #, etc.)  
- Converted object values to numeric  
- Imputed missing values using median (unbiased)  
- Removed 240 duplicate rows  
- Standardized all features using StandardScaler  
- Confirmed no negative or anomalous values  

## Dimensionality Reduction (PCA)
PCA was used to reduce feature dimensionality while maintaining signal strength.

- Original dimensions: 9  
- Selected components: 6  
- Variance retained: **91.14%**

PCA helped identify strongest influencing biological factors in tumor classification.

## Machine Learning Models Applied
- Logistic Regression  
- K-Nearest Neighbors  
- Naive Bayes  
- Decision Tree  
- Random Forest  

All models were trained using 80–20 train–test split.

## Model Performance & Practical Clinical Consideration
Although the Random Forest classifier achieved **100% test accuracy**, such perfect performance on limited dataset size often indicates potential overfitting.

In real medical applications:
- High but realistic performance is preferred  
- Interpretability is essential  
- Explainable decision logic is critical  

### Final Model Decision
✔ Logistic Regression (~98% accuracy) selected as best model  
- Transparent reasoning  
- Smooth generalization  
- Clinically interpretable coefficients  

## Tools & Technologies Used
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

## Key Insights
- Uniformity in cell structure strongly correlates with malignancy  
- PCA successfully reduced noise while retaining essential variance  
- Interpretable models matter more than perfect accuracy  
- Blindly trusting a 100% accuracy model is scientifically unsafe  

## Repository Structure
cancer.csv  
cancer_classification.ipynb  
README.md  

## Conclusion
This project demonstrates a medically responsible ML workflow. While complex models achieved perfect classification.
The final recommended deployment model is Logistic Regression due to its interpretability, stability, and clinical reasoning suitability.

## Author
**Sumit Pant**  
Email: sumitpant2004@gmail.com  
GitHub: https://github.com/sumitpant13  
LinkedIn: https://linkedin.com/in/sumitpant13
