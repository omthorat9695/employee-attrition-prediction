# Employee Attrition Prediction Models

Predicting employee attrition on the IBM HR Analytics dataset using Logistic Regression, Decision Tree, Random Forest and XGBoost,
plus an optional regression task (Job Satisfaction).

## Project Structure
```
├── README.md
├── requirements.txt
├── data/WA_Fn-UseC_-HR-Employee-Attrition.csv
├── notebooks/Employee_Attrition_Prediction.ipynb
├── reports/Evaluation_Report.docx
├── reports/Business_Interpretation_Report.docx
├── figures/   (charts used in the reports)
└── results/   (metric tables as CSV)
```

## Methods
- Preprocessing: dropped constant/ID columns, scaled numeric features, one-hot encoded categorical features, stratified 80/20 split
- Imbalance handling: class weights / scale_pos_weight
- Evaluation: Accuracy, Precision, Recall, F1, ROC-AUC
- Improvement: 5-fold stratified cross-validation, GridSearchCV tuning, feature importance, SHAP

## Results (test set, tuned models)
| Model               |   Accuracy |   Precision |   Recall |    F1 |   ROC-AUC |
|:--------------------|-----------:|------------:|---------:|------:|----------:|
| Logistic Regression |      0.772 |       0.381 |    0.681 | 0.489 |     0.812 |
| Decision Tree       |      0.765 |       0.362 |    0.617 | 0.457 |     0.711 |
| Random Forest       |      0.833 |       0.462 |    0.255 | 0.329 |     0.8   |
| XGBoost             |      0.864 |       0.733 |    0.234 | 0.355 |     0.809 |

**Best model:** Logistic Regression (ROC-AUC 0.812, Recall 0.681, F1 0.489)

**Top drivers of attrition:** MonthlyIncome, OverTime, Age, TotalWorkingYears, YearsAtCompany, DailyRate

## How to Run
1. Open `notebooks/Employee_Attrition_Prediction.ipynb` in Google Colab.
2. Upload `WA_Fn-UseC_-HR-Employee-Attrition.csv` when prompted.
3. Run all cells; reports, figures and results are generated in the `outputs/` folder.

## Reports
- `reports/Evaluation_Report.docx` - methodology, metrics, tuning, feature importance
- `reports/Business_Interpretation_Report.docx` - findings and recommendations for HR
