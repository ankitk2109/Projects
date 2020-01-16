# Classification:

**Task1. Cross Validation using K-NN as base algorithm. Applying a k-NN, to the famous Iris Data set :** 
(i) The split of the training subset vs test subset (split = .67) means roughly 2/3rds training, 1/3rd testing.
(ii) k which is the size of nearest neighbors. The Accuracy of model is determined for test sets; it measures how well it classifications work for the unseen set.

Taking ideas about cross-validation into account; Our job is to first systematically vary the size of the split ; exploring a decent number of other values for it >0.0 and <0.9. Also to systematically vary k on five selected values between 1 and 20.

Then plot the accuracy in a graph for these parameter changes. Now, using this data set, describe an algorithm for doing a 5-fold cross validation on this data set using Python.

Ans. kNN Algorithm: KNN Algorithm is based on feature similarity: How closely out-of-sample features resemble our training set determines how we classify a given data point.
An object/unseen data is classified by a majority vote of its neighbors, with the object being assigned to the class most common among its k nearest neighbors.

n_neighbors(k): Represents the number of neighbors to use for kneighbors queries.
Selected values of k in the program: [3,5,7,9,11]

Split: It decides the training size. Whatever size we give is used for training the model and rest is used for testing. Selected values of split in the program: [0.5,0.6,0.7,0.8,0.9]

On each value of split I have changed k value 5 times and noted the accuracy. Below is graph showing variation of accuracy based on k and split.The legend shows the value of split. 

![image](https://user-images.githubusercontent.com/26432753/72310548-ee966d80-3679-11ea-8ace-d3225926a42e.png)

Fig: Variation of accuracy for different k and splits

Looking at the graph following things can be inferred.
1.When the k values are low the accuracy for most split is low.
2.As we increase the the value of split and k, value of accuracy is also increasing.
3.From this it is clear that when we keep on increasing the the training set our accuracy is also increasing.
4.In most cases when we are taking more number of neighbors into account accuracy is increasing up to a limit and thereafter the model is taking more noise into consideration(Overfitting) hence effecting the accuracy to decrease.

Cross Validation: K-Fold CV is where a given data set is split into a K number of sections/folds where each fold is used as a testing set at some point.For 5-Fold cross validation(K=5) the data set is split into 5 folds. In the first iteration, the first fold is used to test the model and the rest are used to train the model. In the second iteration, 2nd fold is used as the testing set while the rest serve as the training set. This process is repeated until each fold of the 5 folds have been used as the testing set[1].


![image](https://user-images.githubusercontent.com/26432753/72310561-f6561200-3679-11ea-8342-7c5e37987033.png)

Fig: 5-Fold Cross Validation[1]


Step by Step 5-Fold CV implementation.
1.Decide the values of k as we will be using kNN algorithm in 5 fold CV. I have used five value of k as [3,5,7,9,11].
2.Divide the data set into 5 parts.
3.Iterate over data set and in every iteration keeping 1 part as testing and rest for training.Repeat this step five times as we are doing 5-fold cross validation As shown in the figure above.
4.Fit the kNN classifier on training set and evaluate the accuracy score.
5.Calculate the mean of each accuracy score and store it for further plotting.

For each value of k repeat step 3,4 and 5.
Values for each fold and accuracy mean after each iteration is shown below.

![image](https://user-images.githubusercontent.com/26432753/72310568-fb1ac600-3679-11ea-89a9-5a0f2b2ec1b7.png)

Below is the graph for mean accuracy variation for 5-fold cross validation. 

![image](https://user-images.githubusercontent.com/26432753/72310579-ffdf7a00-3679-11ea-9838-5278f2bf8b37.png)

Fig: Mean accuracy after applying 5-fold cross validation on iris data set

By increasing the folds, we train the model on more variation of data set. Hence the results in more accurate model compared to Hold-our training.
Hence it can be seen from graph as well that the accuracy is increasing as we keep on increasing the k-value.  

**Task2. Classify names as Male or Female based upon certain features using Bayes classifiers.**

We have to think of a new feature that could extract from the data-set to identify male and female; We have to define a fn for it (modifying gender_features) and see what is learned from it in the classification.

Ans: Bayes theorem: We can find the probability of A happening, given that B has occurred. Here, B is the evidence and A is the hypothesis. The assumption made here is that the predictors/features are independent[2].

![image](https://user-images.githubusercontent.com/26432753/72310590-07068800-367a-11ea-92c7-b3235ae1bc51.png)

One of the feature that I could extract from the data-set to make the bayes classifier more accurate is:
Combination of Second last and last two letter as shown below: 

![image](https://user-images.githubusercontent.com/26432753/72310600-0b32a580-367a-11ea-96a7-3fc0be092b79.png)

By using the above new feature the accuracy comes to around 80%, whereas when using only the last letter accuracy was approx 76%(as shown below).

![image](https://user-images.githubusercontent.com/26432753/72310611-1259b380-367a-11ea-9009-ba3e6f18ee6d.png)

Comparing the accuracy for both features:

![image](https://user-images.githubusercontent.com/26432753/72310621-1685d100-367a-11ea-8895-c3e5cc333496.png)

Looking at the accuracy it is clear that new feature predicts males and females more accurately then the previous one.


**Task3. Predicting the handwritten digits using SVM.**

Ans: SVM:A Support Vector Machine (SVM) is a discriminative classifier formally defined by a separating hyperplane. In other words, given labeled training data (supervised learning), the algorithm outputs an optimal hyperplane which categorizes new examples. In two dimensional space this hyperplane is a line dividing a plane in two parts where in each class lay in either side[3].



Parameters of SVM
C: regularization parameter, tells the SVM optimization how much you want to avoid misclassifying each training example[3].

![image](https://user-images.githubusercontent.com/26432753/72310711-4f25aa80-367a-11ea-80af-0fbdd7a6cec1.png)

Following pairs of c and gamma values are considered for each set of digits:
1.C=0.5, gamma = 50
2.C= 100,gamma = 5
3.C= 1000, gamma = 0.005
For each pair we are taking 5 handwritten digits to predict them. For each pair below are the outputs

![image](https://user-images.githubusercontent.com/26432753/72310775-9318af80-367a-11ea-8f24-86ad9b13a45a.png)


When C is low the model considers few misclassification and when gamma is high it considers values that are only nearby to the plane/line. Hence in the above output C was very low and gamma was high causing digits to be miss classified. Each digit is classified as [3], whereas the digits are 2,4,5,8 and 9.


![image](https://user-images.githubusercontent.com/26432753/72310818-ae83ba80-367a-11ea-8160-df8e3dd84ad9.png)

When C is high the model avoids misclassification and when gamma is low it considers values far as well to the plane/line. Hence in the above output classifies the digits correctly.

![image](https://user-images.githubusercontent.com/26432753/72310841-be9b9a00-367a-11ea-84a0-77dc9d91d72d.png)

One thing that can be noticed that after a certain values the accuracy does not change. This is because the model is fitted to its limit even after changing C or gamma does not have any affect.

                  
References:
1.Krishni, “K-Fold Cross validation ”, 16, December 2018 [Online]. Available: https://medium.com/datadriveninvestor/k-fold-cross-validation-6b8518070833 [Accessed Oct. 26, 2019]
2.R. Gandhi, “Naive Bayes Classifier ”, 5, May 2018 [Online]. Available: https://towardsdatascience.com/naive-bayes-classifier-81d512f50a7c [Accessed Oct. 26, 2019]
3.S. Patel, “Chapter 2 : SVM (Support Vector Machine) -Theory”, 3, May 2017 [Online]. Available:https://medium.com/machine-learning-101/chapter-2-svm-support-vector-machine-theory-f0812effc72 [Accessed Oct. 26, 2019]
