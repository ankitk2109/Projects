# Building Fairer Algorithm-Algorithm Bias

The aim is to assess the impact of algorithm bias on machine learning algorithms trained with imbalance data.

**DATA: BREAST CANCER**
**Algorithms to compare: k-NN, Decision Trees, Logistic regression and Naive Bayes.**

Comparing accuracies using __Hold out__ and __Cross Validation__

Below are the results for Hold out and Cross validation.

#### Hold-Out Testing

![image](https://user-images.githubusercontent.com/26432753/72551549-fa0db280-388c-11ea-9ac3-4253e96f5134.png)


#### Cross-Validation Testing

![image](https://user-images.githubusercontent.com/26432753/72551687-43f69880-388d-11ea-84c8-a72cc70e0c36.png)

**FP and TP Rate are calculated, based upon that the following conclusion was derived.**

![image](https://user-images.githubusercontent.com/26432753/72551848-9c2d9a80-388d-11ea-948e-352b0512a771.png)

Looking at the results of both the methods for all algorithms, it can be seen that cross validation performs better with high accuracy rates. However, it can be seen that malignant is a minority class but still our predicted values are less then the actual test values showing that these algorithms are biased over majority class.

### Oversampling stratergy for dealing with Imbalance dataset

When the distribution of classes present in a data is not uniform such that the number of instances of a class significantly out numbers the instances of another class leads to class imbalance.

Using Random Sampling to deal with Imbalance dataset.

**FP rates of each Algorithms:**
kNN : 0.0888
Decision Tree: 0.0333
Gaussian Naive Bayes: 0.0777
Logarithmic Regression: 0.0222

Random Oversampling: This method works with minority class. It replicates the observations from minority class to balance the data. It randomly oversampling the minority class. An advantage of using this method is that it leads to no information loss.

After applying random oversampling the FP rates significantly decreases for each algorithm implying that algorithms are now less biased.The disadvantage of using this method is that, since oversampling simply adds replicated observations in original data set, it ends up adding multiple observations of several types, thus leading to overfitting. Although, the training accuracy of such data set will be high, but the accuracy on unseen data will be worse.

Based on the results the FP rate of Logarithmic Regression least hence performing best in my case.

### Using same hold-out and Cross-Validation for CRYOTHERAPY DATASET.

**DataSet: Crytherapy Dataset: This dataset is used to classify whether the person was treated successfully or not based on six features age,sex,time,Number_of_Warts,type and area**

FP-Rate for each algorithms:
**Hold-Out**
kNN: 0.3243
Decison Tree: 0.324
Gaussian naive Bayes: 0.486 
Logistic Regression: 0.21

**Oversampling**
kNN: 0.28
Decison Tree: 024
Gaussian naive Bayes: 0.36
Logistic Regression: 0.16

**Conclusion**
As the dataset was imbalanced the intial hand-out algorithms were biased. After applying oversampling it can be seen above that the FP rate decreases for each classification alorithm.
