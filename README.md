# Market-Regime-Prediction-with-ML

This project attempts to predict market regimes using machine learning. It uses various price and volume features to predict whether the regime of the next day will be bear or bull. This is used to hold or sell accordingly. We utilize a logistic regression model and a random forest model, being compared against a buy-and-hold strategy. This was coded in python using Google Colab. The code is pretty densely commented, but here's the general structure:

In Section 1, we download daily OHLCV(open-high-low-close-volume) data for SPY, the ETF that tracks the S&P 500, from Yahoo Finance. We then create numerous extra features that will assist in prediction, including "target", the regime of the next day which we are trying to predict. Finally, we download this new dataset.

In Section 2, we start by using an 80:20 training to testing split on the data. This split is time-based as chronologicity as we are predicting the regime of the following day, so chronologicity is instrumental. The features are then scaled to ensure equal influence. Then, a logistic regression model is trained and tested on the dataset. Its predictions and corresponding probabilities are stored. 

In Section 3, we print a classification report, classification metrics(accuracy, balanced accuracy, precision, recall, F1 score, and ROC-AUC), a confusion matrix, and an ROC curve for the baseline logistic regression model.

In Section 4, we use cross-validation to find the best combination of hyperparameters for the logistic regression model based on ROC-AUC. We create a pipeline in order to handle scaling and avoid data leakage. We then create a parameter grid with all the hyperparameters that will be tested. The grid-search cross-validation is time-based for the same reason as earlier. The tuned logistic regression model is trained and tested on the dataset. Its predictions and corresponding probabilities are stored, and the best hyperparameters and corresponding ROC-AUC is printed.

In Section 5, we print a classification report, classification metrics, a confusion matrix, and an ROC curve for the tuned logistic regression model.

In Section 6, 
