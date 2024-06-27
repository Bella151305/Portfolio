# Portfolio
Different challenges

## Painter Classification
This is a ***technical assignment from Art Recognition (ArtTech startup)***. The task was to reconstruct the model described in the given article, collect data, repeat the experiment and propose improvements to the model.

The article describes the new approach in solving the problem of painting classification and its advantages over previous state-of-the-art approach. This advantage consists in replacing manual feature extraction for the model with automatic. The authors suggest using an autoencoder, a neural network built on convolution layers, which, by self-learning to restore images after convolution, finds the most important signs distinguishing the style/manner of one artist from another, which is the basis for the authentication of an artwork. After the autoencoder has learned to restore images, the head of the classifier is put in place of the decoder, which in turn is no longer trained from scratch, but on the weights of the autoencoder (transfer learning).

There're 2 notebooks created for different steps of project:
1. IMAGES_DATA for collecting paintings from the wikiart (using wikiart API);
2. CAE_CNN for models and their modifications.


## Credit scoring
- target variable (**default**) is binary
- sampling is **unbalanced**
- model is **Logistic Regression** that we're not allowed to change
- baseline that gives **ROC_AUC = 0.672**
- the best model: **roc_auc = 0.745 (0.73723 on the submission), f1_score = 0.3371**

There're 3 notebooks created for different steps of project:
1. For data investigation results go to 'bella-k-sf-dst-credit-scoring-eda-first-model' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-dst-credit-scoring-eda-first-model)
2. For feature engineering, models testing results go to 'bella-k-sf-dst-credit-scoring-models' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-dst-credit-scoring-models)
3. For getting out the trained final model go to 'bella-k-sf-dst-credit-scoring-best-model' (https://www.kaggle.com/bellakorotkina/bella-k-sf-dst-credit-scoring-best-model)


## Predict TripAdvisor Rating
- target variable (**Rating**) is discrete number
- model with hyperparameters that we're not allowed to change (**RandomForestRegressor: {'bootstrap': True, 'criterion': 'mse', 'max_features': 'auto', 'n_estimators': 100}**)
- baseline that gives **MAE = 0.212**
- the best model: **MAE = 0.168 (0.1726 on the submission)**

There're 4 notebooks created for different steps of project:
1. For data investigation results go to 'bella-k-sf-tripadvisor-rating-eda-nans' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-eda-nans)
2. For feature engineering, models testing results and seeing the best score go to 'bella-k-sf-tripadvisor-rating-fe-models' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-fe-models)
3. For getting out the trained final model with processed train dataset go to 'bella-k-sf-tripadvisor-rating-best-model' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-best-model)
4. For test data processing and getting prediction go to 'bella-k-sf-tripadvisor-rating-test-data' (https://www.kaggle.com/code/bellakorotkina/bella-k-sf-tripadvisor-rating-test-data)
