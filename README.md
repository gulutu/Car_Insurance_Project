# Car Insurance Claim Prediction

This project explores a real-world inspired dataset of car insurance customers to identify factors that influence the likelihood of filing an insurance claim. The workflow includes **Exploratory Data Analysis (EDA)**, **Data Preparation**, and **Modeling & Evaluation** using Logistic Regression and Random Forest. 

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat-square&logo=python&logoColor=white)


---

## Overview

The goal of the project is to identify which customer and vehicle characteristics contribute to claim risk, and to evaluate simple baseline models for predictive performance.  
The analysis includes:

- Exploratory data analysis  
- Feature cleaning and preparation  
- Model training and evaluation  
- Business-oriented interpretation of results  

---

## Exploratory Data Analysis (EDA)

The EDA identified several clear risk patterns:
- Younger customers and drivers with limited experience were more likely to file claims  
- Higher credit scores, higher income, and newer vehicles were associated with lower risk  
- Vehicle ownership contributed meaningfully to claim probability  
- Some driving-history variables (speeding violations, DUIs, past accidents) showed counterintuitive relationships, reflecting the synthetic nature of the dataset.

<p align="center">
<img width="650"  alt="image" src="https://github.com/user-attachments/assets/2357b660-48ba-4fab-83b6-fde400b05d8d" />
<img width="650" alt="image" src="https://github.com/user-attachments/assets/8f4889bd-2eb7-41c0-b609-1019b710839a" />

<img width="650"  alt="image" src="https://github.com/user-attachments/assets/c05c7380-9802-4f74-8e85-0eac280f8433" />
<img width="650"  alt="image" src="https://github.com/user-attachments/assets/85002b7e-9698-44fb-b33f-b945e99c3c23" />

<img width="650" alt="image" src="https://github.com/user-attachments/assets/e084624c-2a38-4945-9c53-c40879c45e9e" />
<img width="650"  alt="image" src="https://github.com/user-attachments/assets/19676b1b-700c-4848-8d72-afccbbd4fd82" />

<img width="650"  alt="image" src="https://github.com/user-attachments/assets/e18c45c4-7644-47ea-982b-36d417da39d3" />
</p>

---

### Data Preparation

Key preprocessing steps:

- **Imputation:** Median imputation for missing values in `credit_score` and `annual_mileage`
- **Feature selection:** Removed irrelevant variables (`id`, `postal_code`, `children`, `married`)
- **Encoding strategies:**  
  - Tree-based models: ordinal categories encoded as integers  
  - Logistic Regression: one-hot encoding to avoid linearity assumptions  

This ensures each model type receives data in a structure aligned with its assumptions.

---

## Modeling & Evaluation

Two baseline models were tested using an 80–20 stratified split:

### Logistic Regression
- Accuracy: **83.3 percent**  
- ROC AUC: **0.884**  
- Precision: 74 percent  
- Recall: 72 percent  

### Random Forest
- Accuracy: **80.6 percent**  
- ROC AUC: **0.857**  
- Key predictors: `credit_score`, `driving_experience`, `annual_mileage`

Logistic Regression showed the strongest generalization, while Random Forest provided valuable feature importance insights.

<p align="center">
<img width="900"  alt="image" src="https://github.com/user-attachments/assets/e99b3cf9-e67b-4e05-863d-11620f63e9d5" />
</p>

---

### Key Takeaways

This project demonstrates:

- A complete workflow from raw dataset to validated models  
- How EDA supports deeper understanding of customer risk patterns  
- How encoding and preprocessing differ by model type  
- That simpler models often perform strongly on structured data  
- The usefulness of ensemble models for feature ranking   

The results underline that a simpler model (Logistic Regression) can sometimes outperform more complex tree-based methods, while ensemble models remain useful for interpretability and feature ranking.

---

## Future Improvements
While the project demonstrates a full end-to-end workflow, there are several areas that could be extended or improved:

- Hyperparameter tuning for Random Forest  
- Testing gradient boosting models (XGBoost, LightGBM, CatBoost)  
- K-fold cross-validation for model stability  
- Business-driven threshold optimization (e.g., precision–recall trade-offs)  
- Cost-sensitive evaluation to quantify financial impact of misclassification
