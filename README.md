# jane-street-market-predictions

Note 2021-10-08: the dataset for this competition is no longer available.

This dataset contains an anonymized set of features, feature_{0...129}, representing real stock market data. Each row in the dataset represents a trading opportunity, for which you will be predicting an action value: 1 to make the trade and 0 to pass on it. Each trade has an associated weight and resp, which together represents a return on the trade. The date column is an integer which represents the day of the trade, while ts_id represents a time ordering. In addition to anonymized feature values, you are provided with metadata about the features in features.csv.

In the training set, train.csv, you are provided a resp value, as well as several other resp_{1,2,3,4} values that represent returns over different time horizons. These variables are not included in the test set. Trades with weight = 0 were intentionally included in the dataset for completeness, although such trades will not contribute towards the scoring evaluation.

This is a code competition that relies on a time-series API to ensure models do not peek forward in time. To use the API, follow the instructions on the Evaluation page. When you submit your notebook, it will be rerun on an unseen test:

    During the model training phase of the competition, this unseen test set is comprised of approximately 1 million rows of historical data.
    During the live forecasting phase, the test set will use periodically updated live market data.

Note that during the second (forecasting) phase of the competition, the notebook time limits will scale with the number of trades presented in the test set. Refer to the Code Requirements for details.
## Files

    train.csv - the training set, contains historical data and returns
    example_test.csv - a mock test set which represents the structure of the unseen test set. You will not be directly using the test set or sample submission in this competition, as the time-series API will get/set the test set and predictions.
    example_sample_submission.csv - a mock sample submission file in the correct format
    features.csv - metadata pertaining to the anonymized features
