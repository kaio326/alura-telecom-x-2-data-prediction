# Telecom Churn Prediction

## Project Overview
This repository contains a complete end-to-end workflow for predicting customer churn in a telecommunications dataset. It includes data preprocessing, exploratory analysis, model training, evaluation, feature importance, and retention strategy recommendations.

## Repository Structure
```
.
├── LICENSE
├── README.md
├── Telecom_X_Prediction.ipynb    # Jupyter notebook with full analysis and code
└── telecomx_cleaned.csv          # Cleaned telecom customer dataset
```

## Dataset
- **telecomx_cleaned.csv**:  
  - ~7,267 customer records  
  - Features: demographics, service usage, contract details, billing and payment  
  - Target: `Churn` (Boolean)

## Analysis Steps

1. **Exploratory Data Analysis (EDA)**
   - Summary statistics and class balance  
   - Visualizations: distributions, boxplots, scatter plots  
   - Correlation matrix and heatmap to identify relationships

2. **Preprocessing**
   - Drop irrelevant columns (`customerID`, `Charges.Daily`)  
   - One-hot encoding for categorical variables  
   - Train/test split (80/20) with stratification  
   - Standard scaling for models sensitive to feature scale  

3. **Handling Class Imbalance**
   - Applied SMOTE to oversample minority class  
   - Tuned sampling strategy to balance precision and recall  
   - Adjusted decision thresholds via precision–recall curve

4. **Model Training & Evaluation**
   - **Logistic Regression** (scaled inputs + SMOTE)  
   - **Random Forest** (unscaled inputs + SMOTE)  
   - Metrics: accuracy, precision, recall, F1-score, ROC AUC, confusion matrix  
   - Threshold tuning to meet business targets (e.g., ≥75% precision)

5. **Feature Importance**
   - Extracted coefficients from Logistic Regression  
   - Retrieved `feature_importances_` from Random Forest  
   - Identified top predictors of churn

6. **Retention Strategies**
   - Strengthen long-term contracts  
   - Promote add-on services and bundles  
   - Improve billing methods and offer pricing incentives  
   - Proactive support for at-risk customers

## Key Findings
- **Top drivers of churn**: month-to-month contracts, lack of service add-ons (security, tech support), fiber-optic Internet, electronic check payments, higher monthly charges.
- **Model performance**:
  - Logistic Regression: high recall (74%) and ROC AUC (0.80)  
  - Random Forest: higher precision (59%) and overall accuracy (75%)  
- **Optimal trade-off**: threshold tuning at ~0.708 achieves ~75% precision with acceptable recall.

## How to Run
1. Clone the repository:
   ```
   git clone https://github.com/kaio326/alura-telecom-x-2-data-prediction.git
   cd alura-telecom-x-2-data-prediction
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Launch the notebook:
   ```
   jupyter notebook Telecom_X_Prediction.ipynb
   ```

## Future Improvements
- Add cross-validation and hyperparameter optimization  
- Modularize code into reusable functions or scripts  
- Implement an ensemble method for balanced precision–recall  
- Automate data pipeline and model deployment  
- Monitor model drift and retrain periodically

## License
This project is licensed under the MIT License.  
```