# Twitter-Sentiment-Analysis
Sentiment Analysis is the automated process of analyzing text data and sorting it into sentiments positive, negative or neutral. Here we analyze tweets for discrimination information.

## Data set
The data is downloaded from this github repository:
https://github.com/sharmaroshan/Twitter-Sentiment-Analysis
## Data preprocessing
## model
### tf-idf vector space representation

### dummy classification to define the baseline of the F1-score in imbalanced classification
Because of the nature of the imbalance classification, 'accurary' is not a good metric to evaluate our prediction. F1-score, which considers both both precision and recall, is a better metric. Now the problem becomes: how good our model is in this metric. Therefore, we need a simple model which can provide us some trivial prediction as a baseline. The baseline model provides a lower bound on performance for model evaluation and our trained model must at least outperform the baseline. In sklearn, there is a class called "DummyClassifier", which provides us different kinds of strategyies to construct the dummy classifier.
More about the baseline of F1 score:
https://stats.stackexchange.com/questions/390200/what-is-the-baseline-of-the-f1-score-for-a-binary-classifier

Here logistic Regression, support vector machine and random forest models are chosen as trined models. 

### Re-sampling methods in imbalanced classification
To deal with the imbalance classification problem, re-sampling methods with "imbalanced-learn" package is applied.
There are over-sampling and and under-sampling methods. In over-sampling methods, more data is generated in the minority class, whereas in under-sampling methods, some datas is generated in belong to majority class are removed. In principle, more data can provide more information, so over-sampling methods sound better. However, in the sentiment analysis problem, the dimensionality of the feature space is very large and the data belong to minority class might be very sparse. The process of over-sampling mostly relies on the concept of nearest neighbors and might create synthesis datas which are more close to the majority class. Therefore, the under-sampling methods are chosen in this project.

The under-sampling method we use in this project is Tomek Link Removal. A pair of samples is called a Tomek link if they belong to different classes and are each other’s nearest neighbors. Under-sampling can be done by removing all tomek links from the dataset. An alternate method is to only remove the majority class samples that are part of a Tomek link.
