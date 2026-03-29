# Project Deliverable 2: Regression Modeling and Performance Evaluation

**GitHub Repository:** https://github.com/Sandeep271/Project

## Dataset Summary
This deliverable uses the **Online Retail** dataset, which contains transaction-level retail records such as invoice number, product description, quantity, invoice date, unit price, customer ID, and country. After focused cleaning, the transaction data was aggregated to the **customer level** so that each row represented one customer.

The regression target for this deliverable is **LogTotalSpent**, which is the log-transformed version of total customer spending. The log transformation was used because raw customer spending was heavily right-skewed.

## Files Included
- `MSCS_634_Project_Deliverable_2_Submission_Ready_Fixed.ipynb`
- `README.md`

## Data Cleaning and Preparation
The following steps were performed before modeling:
1. Removed duplicate rows.
2. Removed rows with missing `Description` and `CustomerID`.
3. Removed rows with non-positive `Quantity` and `UnitPrice`.
4. Created `TotalSales` at the transaction level.
5. Aggregated the data to the customer level.
6. Created `LogTotalSpent` to reduce skewness in the target.

## Feature Engineering
To improve model performance, two new features were created:
- **AvgQuantityPerTransaction**: total quantity divided by number of transactions.
- **QuantityPriceInteraction**: total quantity multiplied by average unit price.

A quick comparison using linear regression showed that the engineered feature set performed slightly better than the baseline feature set:
- Baseline Linear Regression: **R² = 0.6338**, **RMSE = 0.7665**
- Engineered Linear Regression: **R² = 0.6370**, **RMSE = 0.7632**

## Regression Models
The notebook compares three regression models:
- Linear Regression
- Ridge Regression
- Lasso Regression

## Model Evaluation Results
The final test-set results were:

| Model | R² | MSE | RMSE | MAE |
|---|---:|---:|---:|---:|
| Linear Regression | 0.6370 | 0.5825 | 0.7632 | 0.5823 |
| Ridge Regression | 0.6370 | 0.5825 | 0.7632 | 0.5823 |
| Lasso Regression | 0.6370 | 0.5825 | 0.7632 | 0.5823 |

The best-performing model on the test set was **Lasso Regression**, although the margin was very small and all three models performed almost identically.

## Cross-Validation
Five-fold cross-validation was used to check generalization performance. The cross-validation results were:

| Model | Mean CV R² | CV Standard Deviation |
|---|---:|---:|
| Linear Regression | 0.5710 | 0.1002 |
| Ridge Regression | 0.5709 | 0.1002 |
| Lasso Regression | 0.5710 | 0.1002 |

The cross-validation results show that the models generalize reasonably well, even though the cross-validation score is lower than the single test-set score.

## Key Insights
- Customer spending can be predicted moderately well using customer purchase behavior and pricing patterns.
- Feature engineering produced a modest but meaningful improvement over the baseline feature set.
- Regularization did not create a major performance jump, which suggests the relationships in this dataset are already fairly stable and close to linear.
- The interaction between quantity and price helped capture spending behavior more effectively.

## Challenges and How They Were Addressed
### 1. Skewed target variable
Raw total customer spending had a long right tail. This was addressed by using a log transformation.

### 2. Missing and invalid records
Missing product descriptions, missing customer IDs, and non-positive quantity or price values could have weakened the models. These records were removed before aggregation and modeling.

### 3. Turning transaction data into a regression-ready dataset
The original data was at the invoice-line level, which is not ideal for predicting customer spending. This was handled by aggregating the transactions into a customer-level table.

## Final Note
This deliverable is focused only on the regression phase of the project. It includes the full regression workflow: cleaning, feature engineering, model building, model evaluation, visualization, and cross-validation.
