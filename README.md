## 🚗 Car Insurance Claim Prediction – Project Summary

This project explores a real-world inspired dataset of car insurance customers to identify factors that influence the likelihood of filing an insurance claim. The analysis was structured into three main parts: **Exploratory Data Analysis (EDA)**, **Data Preparation**, and **Modeling & Evaluation**.  

### 🔎 Exploratory Data Analysis
The EDA revealed clear risk patterns: younger customers and those with little driving experience were more likely to file claims, while higher credit scores and stable income levels were associated with lower risk. Vehicle-related factors, such as owning the car outright and having a newer model, also reduced claim probability. Interestingly, driving history features (speeding violations, DUIs, past accidents) showed counterintuitive patterns, reflecting the synthetic nature of the dataset.
<img width="684" height="464" alt="image" src="https://github.com/user-attachments/assets/2357b660-48ba-4fab-83b6-fde400b05d8d" />
<img width="736" height="464" alt="image" src="https://github.com/user-attachments/assets/8f4889bd-2eb7-41c0-b609-1019b710839a" />

<img width="684" height="464" alt="image" src="https://github.com/user-attachments/assets/c05c7380-9802-4f74-8e85-0eac280f8433" />
<img width="631" height="541" alt="image" src="https://github.com/user-attachments/assets/85002b7e-9698-44fb-b33f-b945e99c3c23" />

<img width="684" height="464" alt="image" src="https://github.com/user-attachments/assets/e084624c-2a38-4945-9c53-c40879c45e9e" />
<img width="631" height="541" alt="image" src="https://github.com/user-attachments/assets/19676b1b-700c-4848-8d72-afccbbd4fd82" />

<img width="684" height="464" alt="image" src="https://github.com/user-attachments/assets/e18c45c4-7644-47ea-982b-36d417da39d3" />

### ⚙️ Data Preparation
Missing values in `credit_score` and `annual_mileage` were imputed with median values. Irrelevant features (`id`, `postal_code`, `children`, `married`) were removed. Two modeling datasets were prepared:  
- **Tree-based models**: ordinal categories mapped to integers.  
- **Logistic Regression**: one-hot encoding applied to ordinal features to avoid linearity assumptions.  

### 🤖 Modeling & Evaluation
Two baseline models were developed and evaluated on an 80/20 stratified train-test split:  
- **Logistic Regression**: Achieved **83.3% accuracy** and an **ROC AUC of 0.884**, with balanced precision (74%) and recall (72%).  
- **Random Forest**: Achieved **80.6% accuracy** and an **ROC AUC of 0.857**, highlighting `credit_score`, `driving_experience`, and `annual_mileage` as the most important predictors.  

Confusion matrix, ROC/PR curves, and business-oriented interpretation were included for both models. Logistic Regression outperformed Random Forest in this case, but the latter provided valuable insights through feature importance. 
<img width="996" height="596" alt="image" src="https://github.com/user-attachments/assets/e99b3cf9-e67b-4e05-863d-11620f63e9d5" />


### 📌 Key Takeaways
This project demonstrates the end-to-end process of:  
- Cleaning and preparing categorical/continuous features for different models.  
- Conducting thorough exploratory analysis to derive business insights.  
- Training and evaluating multiple models with clear performance metrics.   

The results underline that a simpler model (Logistic Regression) can sometimes outperform more complex tree-based methods, while ensemble models remain useful for interpretability and feature ranking.

## 🚀 Future Improvements
While the project demonstrates a full end-to-end workflow, there are several areas that could be extended or improved:

- **Hyperparameter Tuning**  
  Perform grid search or randomized search on Random Forest (e.g., `max_depth`, `min_samples_split`, `n_estimators`) to optimize performance.  

- **Gradient Boosting Models**  
  Test models such as XGBoost, LightGBM, or CatBoost, which often outperform Random Forest on structured data.  

- **Cross-Validation**  
  Implement k-fold cross-validation to ensure model stability and reduce dependence on a single train/test split.   

- **Business Threshold Optimization**  
  Explore different classification thresholds to adjust the balance between recall (capturing risky customers) and precision (avoiding false positives), depending on business goals.  

- **Cost-Sensitive Evaluation**  
  Introduce a cost-benefit analysis (e.g., monetary loss of false negatives vs. cost of false positives) to align evaluation with real insurance scenarios.  

