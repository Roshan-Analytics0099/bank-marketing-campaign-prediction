# Bank Marketing Campaign Prediction

Predicting whether a customer will subscribe to a term deposit, using the Bank Marketing dataset and six classification models built in RapidMiner.

## Business Problem
Banks often contact large numbers of customers without knowing who is likely to respond, which drives up campaign costs and lowers success rates. This project builds a model to identify customers most likely to subscribe to a term deposit, so marketing efforts can be better targeted.

## Data
- **Source:** Bank Marketing Dataset (UCI Machine Learning Repository)
- **Features:** demographics (age, job, marital status, education), financial info (balance, housing, loan), and campaign history (contact duration, number of contacts, previous outcomes)
- **Target:** whether the customer subscribed to a term deposit (yes/no)

## Approach
- Preprocessed data in RapidMiner: handled missing values, converted categorical variables to numeric, normalized numeric fields, and set the target as the label
- Ran exploratory analysis on balance distribution and job category vs. subscription outcome to understand customer patterns
- Built and compared six classification models using **10-fold cross-validation** with stratified sampling:
  - Logistic Regression
  - Linear Discriminant Analysis (LDA)
  - K-Nearest Neighbors (K-NN)
  - Naive Bayes
  - Random Forest (Bagging)
  - AdaBoost (Boosting)

## Results

| Model | Accuracy | AUC | Precision | Recall | F1-score |
|---|---|---|---|---|---|
| Logistic Regression | 82.57% | 0.903 | 82.61% | 84.73% | 83.64% |
| LDA | 71.27% | 1.000 | 73.69% | 65.51% | 68.58% |
| K-NN | 75.86% | 0.821 | 77.32% | 69.43% | 73.14% |
| **Random Forest** | **84.90%** | **0.919** | 81.39% | **88.37%** | **84.73%** |
| AdaBoost | 76.98% | 0.819 | 80.56% | 69.18% | 74.84% |

**Random Forest performed best overall**, with the highest accuracy and the highest recall. Recall mattered most for this problem, since a missed subscriber (false negative) is a lost sales opportunity, while a wrongly-flagged customer just costs one extra call.

## Key Insight
Job category and account balance both showed a clear relationship with subscription behavior. Retired customers and those in management roles subscribed at noticeably higher rates than other groups, and balance was highly right-skewed with a small group of high-balance customers.

## Business Recommendation
Banks can use a model like this to prioritize outreach to customers most likely to subscribe rather than contacting their full customer base, reducing campaign cost while improving conversion.

## Tools
RapidMiner, Excel

## Files
- `Bank_Marketing_Report.pdf` — full project write-up, including EDA charts, RapidMiner process diagrams, and detailed model evaluation
