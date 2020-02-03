# Credit Card Fraud Detection using sklearn
### A similar approach to project completed using Tibco Spotfire DataScience.

### Input
Please find the dataset on: https://www.kaggle.com/mlg-ulb/creditcardfraud/data#

### Output
Accuracy achieved through Isolation forest and Random forest are nearly same as the dataset is imbalanced. However the main difference is visible when the number of errors are counted.

Isolation forest: 148
Random Forest: 27

Hence Random Forest is a better model in this case

### MAIN CHALLENGES IN CREDIT CARD FRAUD DETECTION:

• Enormous Data is processed every day and the model build must be fast enough to respond to the scam in time.

• Imbalanced Data i.e most of the transactions(99.8%) are not fraudulent which makes it really hard for detecting the fraudulent ones

• Data availability as the data is mostly private.

• Misclassified Data can be another major issue, as not every fraudulent transaction is caught and reported.

• And last but not the least, Adaptive techniques used against the model by the scammers.

How to tackle these challenges?
* The model used must be simple and fast enough to detect the anomaly and classify it as a fraudulent transaction as quickly as possible.
* Imbalance can be dealt with by properly using methods mentioned above.
For protecting the privacy of the user the dimensionality of the data can be reduced.
* A more trustworthy source must be taken which double-check the data, at least for training the model.
* We can make the model simple and interpretable so that when the scammer adapts to it with just some tweaks we can have a new model up and running to deploy.


DEALING WITH IMBALANCE DATASET
1. Dealing with Imbalance data-set: 
• ML algorithms tend to tremble when faced with imbalanced classification data sets. Moreover, they result in biased predictions and misleading accuracies.
• With imbalanced data sets, an algorithm doesn’t get the necessary information about the minority class to make an accurate prediction. Hence it is desirable to use ML algorithm with balanced dataset.

2. What is Imbalanced classification?
• Imbalanced classification is a supervised learning problem where one class outnumbers other class by a large proportion. This problem is faced more frequently in binary classification problems than multi-level classification problems.

3. Why do standard ML algorithms struggle with accuracy on imbalanced data?
• ML algorithms struggle with accuracy because of the unequal distribution in dependent variable. This causes the performance of existing classifiers to get biased towards majority class.
• The algorithms are accuracy driven i.e. they aim to minimize the overall error to which the minority class contributes very little.
• ML algorithms assume that the data set has balanced class distributions.

4. Methods to deal with imbalanced data sets?
Sampling methods
• Undersampling
• Oversampling
• synthetic data generation
• cost sensitive learning

i) Undersampling: This method works with majority class. It reduces the number of observations from majority class to make the data set balanced
• This method is best to use when the data set is huge and reducing the number of training samples helps to improve run time and storage troubles.
a. Random undersampling: this method randomly chooses observations from majority class which are eliminated until the data set gets balanced.
b. Informative undersampling: This follows a pre-specified selection criterion to remove the observations from majority class.
• PROBLEM: Apparently, removing observations may cause the training data to lose important information pertaining to majority class.

ii) Oversampling: This method works with minority class. It replicates the observations from minority class to balance the data. It is also known as upsampling. Similar to undersampling, this method also can be divided into two types: Random Oversampling and Informative Oversampling.
• An advantage of using this method is that it leads to no information loss.
• Disadvantage: oversampling simply adds replicated observations in original data set, it ends up adding multiple observations of several types, thus leading to overfitting. Although, the training accuracy of such data set will be high, but the accuracy on unseen data will be worse.

iii) Synthetic Data Generation:  Instead of replicating and adding the observations from the minority class, it overcome imbalances by generates artificial data. It is also a type of oversampling technique.
• In regards to synthetic data generation, synthetic minority oversampling technique (SMOTE) is a powerful and widely used method.
• SMOTE algorithm creates artificial data based on feature space (rather than data space) similarities from minority samples.
• We can also say, it generates a random set of minority class observations to shift the classifier learning bias towards minority class.
• To generate artificial data, it uses bootstrapping and k-nearest neighbors.

iv) Cost Sensitive Learning (CSL): This method evaluates the cost associated with misclassifying observations. 
• It does not create balanced data distribution. Instead, it highlights the imbalanced learning problem by using cost matrices which describes the cost for misclassification in a particular scenario.
• Recent researches have shown that cost sensitive learning have many a times outperformed sampling methods.
Taking a example where we have to identify a person whether the person has a bomb or not.
Having a bomb is identified as True Positive(TP). Not having a bomb is considered as True Negative(TN). But, the cost associated with identifying a person with bomb as negative (False Negative) is much more dangerous than identifying a person without bomb as positive (False Positive).
Cost Matrix is similar of confusion matrix. It’s just, we are here more concerned about false positives and false negatives.

### Evaluation

Which performance metrics to use to evaluate accuracy ?

Most classification algorithms calculate accuracy based on the percentage of observations correctly classified. With imbalanced data, the results are high deceiving since minority classes hold minimum effect on overall accuracy.

The difference between confusion matrix and cost matrix is that, cost matrix provides information only about the misclassification cost, whereas confusion matrix describes the entire set of possibilities using TP, TN, FP, FN.

The most frequently used metrics are Accuracy & Error Rate

Accuracy: (TP + TN)/(TP+TN+FP+FN)

Error Rate = 1 - Accuracy = (FP+FN)/(TP+TN+FP+FN)

Precision: It is a measure of correctness achieved in positive prediction i.e. of observations labeled as positive, how many are actually labeled positive.
• Precision = TP / (TP + FP)

Recall: It is a measure of actual observations which are labeled (predicted) correctly i.e. how many observations of positive class are labeled correctly. It is also known as ‘Sensitivity’.
• Recall = TP / (TP + FN)

F measure: It combines precision and recall as a measure of effectiveness of classification in terms of ratio of weighted importance on either recall or precision as determined by β coefficient.
• F measure = ((1 + β)² × Recall × Precision) / ( β² × Recall + Precision )
• β is usually taken as 1.

### CRITERIA TO IDENTIFY AN OUTLIER:
1. Data points that falls outside of 1.5 times of an interquartile range above the 3rd quartile and below the 1st quartile.
IQR = Q3 - Q1
       = 75% - 25%

2. Data points that falls outside of 3 standard deviations. we can use z-score and if the z score falls outside of 2 standard deviation.

Suppose, X = [1,2,3,4,5] mean= 3 and std_Dev = 1
z = Xi - mean/std_dev. If any data point lies away from z<=3, it is know as outlier.

VARIOUS WAYS OF FINDING THE OUTLIER
1. Using Scatter plots
2. Box Plots
3. Using z score
4. Using the IQR interquantile range

### Anamoly detection algorithm
Isolation Forest: https://quantdare.com/isolation-forest-algorithm/
