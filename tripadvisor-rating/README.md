# Predict TripAdvisor Rating

In this competition we're provided with:
- train and test datasets of 40,000 and 10,000 samples respectivly and 9 features except target feature;
- target feature is **Rating** - discrete number.
- model with hyperparameters that we're **not allowed** to change (**RandomForestRegressor**: {'bootstrap': **True**, 'criterion': '**mse**', 'max_features': '**auto**', 'n_estimators': 100});
- baseline that gives **MAE** = 0.212

There're 4 notebooks created for different steps of project:
1. For data investigation results go to 'bella-k-sf-tripadvisor-rating-**eda-nans**' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-eda-nans)
2. For feature engineering, models testing results and seeing the **best score** go to 'bella-k-sf-tripadvisor-rating-**fe-models**' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-fe-models)
3. For getting out the **trained final model** with processed train dataset go to 'bella-k-sf-tripadvisor-rating-**best-model**' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-best-model):
  - best_model.pkl
  - model_data.csv
  - lists_dict.json
4. For test data processing and getting prediction go to 'bella-k-sf-tripadvisor-rating-**test-data**' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-test-data)

**What has been done and achieved**:
1. New features:
    - restaurant type, area food, country food, spcialities were get from cuisine style feature
    - name of restaurant and its region were get from url
    - chain and chain_scale were get by grouping restaurants' names
    - lasts 2 reviews date delta and last review date delta with max date of review as well as positive and negative words scores were get from reviews feature
    - some normalized and scaled be city numerical features
    - some means and medians
    - polinomial features
    - dummy features
2. 27 tests of model with different features conbinations
3. **MAE** has been reduced to **0.198** and after rounding predict with pitch 0.5 to make continious number discrete - to **0.168** on validation data (**0.1726** on the submission)
