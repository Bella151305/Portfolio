# Credit scoring
In this competition we're provided with:
- train and test datasets of 73,799 and 36,349 samples respectivly and 18 features except target one;
- model that we're not allowed to change;
- baseline that gives **ROC_AUC = 0.672**;
- target variable **default** is binary;
- the bank has more not defaulted clients (87% vs 13%) - **sampling is unbalanced**

Our model is **Logistic Regression**.

There're 3 notebooks created for different steps of project:
1. For data investigation results go to 'bella-k-sf-dst-credit-scoring-eda-first-model' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-dst-credit-scoring-eda-first-model)
2. For feature engineering, models testing results go to 'bella-k-sf-dst-credit-scoring-models' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-dst-credit-scoring-models)
3. For getting out the trained final model go to 'bella-k-sf-dst-credit-scoring-best-model' (https://www.kaggle.com/bellakorotkina/bella-k-sf-dst-credit-scoring-best-model):

The best model (without additional default samples): **roc_auc = 0.745, f1_score = 0.3371**

***We still have very pure f1_score. But the key metric is ROC_AUC and it's lower in the model with higher f1_score.***

What has been done:
1. Worked out **undersampling**:
- 14 tests of model with step by step multyplication of dataset's default part to find the best combination of ROC_AUC and F1_score: plus 700% of all defaults (more than not default) & split with stratify = y (**roc_auc = 0.736, f1_score = 0.7067**)
2. Working out **hyperparameters** for both models (with and without additional default samples):
- LogisticRegressionCV - to find better C for l2 penalty
- GridSearchCV - to find better rest parameters
3. **Pipeline** for model that includes:
- OneHotEncoder for binary and categorical features
- Logarithm for some numeric features
