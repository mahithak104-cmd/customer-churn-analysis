# Customer Churn Analysis

A Python-based customer analytics and machine learning project focused on identifying customer churn patterns, analyzing retention risks, and evaluating a baseline classification model.

## Project Overview

Customer churn is an important business problem because losing customers can reduce revenue and increase customer acquisition costs. This project explores customer behavior, credit utilization, transaction activity, and account tenure to identify patterns associated with churn.

The analysis combines exploratory data analysis (EDA), customer segmentation, statistical visualization, and logistic regression to understand potential churn indicators and evaluate the challenges of predicting churn in an imbalanced dataset.

## Objectives

- Analyze the overall customer churn distribution.
- Investigate churn patterns across customer tenure segments.
- Examine the relationship between credit utilization and churn.
- Evaluate churn rates across transaction activity levels and demographic groups.
- Explore correlations between key customer variables.
- Build and evaluate a baseline logistic regression model.
- Identify actionable opportunities for customer retention.

## Tools and Technologies

- **Python** — data analysis and preprocessing
- **Pandas & NumPy** — data manipulation and numerical analysis
- **Matplotlib & Seaborn** — data visualization
- **Scikit-learn** — machine learning and model evaluation
- **Jupyter Notebook** — interactive analysis and experimentation

## Exploratory Data Analysis

### 1. Overall Churn Distribution

The dataset shows that approximately 3.4% of customers churned, while 96.6% remained active.

This indicates a significant class imbalance, making it important to evaluate the model's ability to identify churners rather than relying on accuracy alone.

### Top 10 Features Affecting Churn 
(<img width="711" height="446" alt="Top 10 Features Affecting Churn " src="https://github.com/user-attachments/assets/e7a823f3-d78f-4fa7-90a8-71feba7c2495" />)

### 2. Churn by Customer Tenure

Customers with 6–12 months of tenure have the highest observed churn rate at approximately 12.7%.

| Tenure Segment | Churn Rate |
|---|---:|
| Less than 6 months | 1.9% |
| 6–12 months | 12.7% |
| 12–24 months | 4.3% |
| 24–48 months | 4.4% |
| 48+ months | 2.2% |

**Business insight:** The 6–12 month segment is a priority for further investigation. Targeted engagement, customer feedback, and retention initiatives could help determine why churn is elevated during this period.

<img width="868" height="478" alt="Churn Rate by Tenure Bucket" src="https://github.com/user-attachments/assets/1e2ccd0a-0836-4c30-8400-162d66048def" />

### 3. Churn by Credit Utilization

Customers with utilization ratios above 90% have an observed churn rate of approximately 12%, higher than the other utilization groups.

This pattern suggests that high utilization may be a useful indicator for further investigation. However, the relationship does not establish causation.

<img width="1046" height="483" alt="Churn Rate by Utilization Bucket" src="https://github.com/user-attachments/assets/7a888125-8d40-4988-a6fb-9b79ad1b39ff" />

### 4. Tenure and Utilization Segmentation

A heatmap was used to examine churn rates across combinations of tenure and utilization buckets.

The highest displayed churn rate is 50% for customers with 6–12 months of tenure and utilization above 90%.

Segment sizes should be examined before drawing conclusions, as small groups can produce volatile churn rates.

### Confusion Matrix- Logistic Regression
<img width="632" height="395" alt="Confusion Matrix - Logistic Regression" src="https://github.com/user-attachments/assets/189d19ad-ffe9-4761-99f3-c5bbb62e0176" />

### 5. Transaction Activity

The analysis indicates that customers in the low transaction activity category have a higher observed churn rate than customers in the higher activity categories.

This suggests that reduced engagement may be worth investigating as a potential early-warning indicator.

<img width="1050" height="499" alt="Churn Rate by Transaction Activity Level" src="https://github.com/user-attachments/assets/ee4d1b8c-8b8e-408d-b399-c5325f61907f" />

### 6. Utilization Distribution by Churn Status

Distribution plots and boxplots compare utilization ratios between churned and non-churned customers.

These visualizations help examine differences in central tendency, variability, and extreme values between the two groups.

<img width="632" height="459" alt="Distribution of Utilization Ratio by Churn Status" src="https://github.com/user-attachments/assets/5deb28ea-f48a-492a-b63e-75c086d79727" />

### 7. Correlation Analysis

A correlation heatmap was created to examine relationships among tenure, utilization, monthly transactions, and churn.

The displayed correlations with churn are relatively weak:

- Tenure: approximately -0.08
- Utilization ratio: approximately 0.08
- Monthly transactions: approximately -0.15

These values describe pairwise linear relationships and do not rule out more complex predictive patterns.

<img width="853" height="597" alt="Correlation Heatmap of Key Variables" src="https://github.com/user-attachments/assets/8e6f102d-6d44-40be-b6d7-c4a428e77721" />


## Machine Learning: Logistic Regression

Logistic regression was used as a baseline classification model to predict the binary churn outcome.

### Baseline Model Evaluation

The displayed confusion matrix contains the following results:

| Metric | Result |
|---|---:|
| True negatives | 291 |
| False positives | 0 |
| False negatives | 9 |
| True positives | 0 |
| Accuracy | 97.0% |
| Churn recall | 0.0% |

Although the baseline model achieves 97% accuracy on the displayed evaluation sample, it predicts every customer as a non-churner and fails to identify any churners.

This demonstrates why accuracy alone is insufficient for evaluating an imbalanced classification problem.

### Potential Improvements

- Apply stratified train-test splitting.
- Use a preprocessing pipeline with appropriate feature scaling.
- Evaluate class-weighted logistic regression.
- Compare alternative classification thresholds.
- Compare logistic regression with tree-based models.
- Evaluate precision, recall, F1-score, ROC-AUC, and precision-recall AUC.
- Tune the model using validation data and assess its performance on an untouched test set.

These improvements are proposed next steps; their effectiveness has not yet been established.

## Key Business Insights

1. **Retention priority:** Investigate customers in the 6–12 month tenure segment.
2. **Utilization monitoring:** Examine customers with utilization above 90% as a potentially higher-risk segment.
3. **Engagement analysis:** Investigate whether low transaction activity can help identify customers who may disengage.
4. **Segment validation:** Review sample sizes before prioritizing interventions based on subgroup churn rates.
5. **Model improvement:** Improve churn detection before using model predictions to guide retention decisions.

## Project Limitations

- The observed relationships are descriptive and do not establish causation.
- The dataset has a relatively low churn proportion, creating a class imbalance challenge.
- The baseline logistic regression fails to identify churners in the displayed confusion matrix.
- Segment-level churn rates may be sensitive to small sample sizes.
- Further model validation is needed before deploying predictions or recommending customer-level interventions.

## Conclusion

This project demonstrates exploratory customer analytics, churn segmentation, data visualization, and baseline machine learning evaluation.

The findings highlight tenure, utilization, and transaction activity as areas for further investigation. The baseline model also illustrates an important machine learning lesson: high accuracy does not necessarily translate into useful business predictions.

Future work will focus on improving minority-class detection, validating the findings, comparing classification models, and developing more actionable customer retention insights.

## Skills Demonstrated

Python, Pandas, NumPy, Exploratory Data Analysis, Data Cleaning, Data Visualization, Customer Segmentation, Correlation Analysis, Logistic Regression, Classification Evaluation, and Business Insight Generation.

## Author
Mahitha Kalinathabotla
[LinkedIn](https://www.linkedin.com/in/mahitha-kalinathabotla)
