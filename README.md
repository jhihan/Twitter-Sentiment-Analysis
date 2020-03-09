# Twitter-Sentiment-Analysis
Sentiment Analysis is the automated process of analyzing text data and sorting it into sentiments positive, negative or neutral. Here we analyze tweets for discrimination information.

## data set
The data is downloaded from this github repository:
https://github.com/sharmaroshan/Twitter-Sentiment-Analysis
## model
### tf-idf vector space representation

### dummy classification to define the baseline of the F1-score in imbalanced classification
Because of the nature of the imbalance classification, 'accurary' is not a good metric to evaluate our prediction. F1-score, which considers both both precision and recall, is a better metric. Now the problem becomes: how good our model is in this metric. Therefore, we need a simple model which can provide us some trivial prediction as a baseline and our trained model must at least outperform the baselines. In sklearn, there is a class called "DummyClassifier", which provides us different kinds of strategyies to construct the dummy classifier.

Logistic Regression, support vector machine and random forest models are applied and compared. 

### Over-sampling methods in imbalanced classification
To deal with the imbalance classification problem, the borderline-SMOTE technique, which is one of the over-sampling methods, is applied after the tf-idf transformation.
