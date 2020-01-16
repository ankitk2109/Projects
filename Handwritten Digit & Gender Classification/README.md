# Handwritten Digit & Gender Classification

## Handwritten Digit classification: Predicting the handwritten digits using SVM.

SVM:A Support Vector Machine (SVM) is a discriminative classifier formally defined by a separating hyperplane. In other words, given labeled training data (supervised learning), the algorithm outputs an optimal hyperplane which categorizes new examples. In two dimensional space this hyperplane is a line dividing a plane in two parts where in each class lay in either side[3].



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

## Gender Classification: Using name features to classify gender as male or female.

We have to think of a new feature that could extract from the data-set to identify male and female; We have to define a fn for it (modifying gender_features) and see what is learned from it in the classification.

Bayes theorem: We can find the probability of A happening, given that B has occurred. Here, B is the evidence and A is the hypothesis. The assumption made here is that the predictors/features are independent[2].

![image](https://user-images.githubusercontent.com/26432753/72310590-07068800-367a-11ea-92c7-b3235ae1bc51.png)

One of the feature that I could extract from the data-set to make the bayes classifier more accurate is:
Combination of Second last and last two letter as shown below: 

![image](https://user-images.githubusercontent.com/26432753/72310600-0b32a580-367a-11ea-96a7-3fc0be092b79.png)

By using the above new feature the accuracy comes to around 80%, whereas when using only the last letter accuracy was approx 76%(as shown below).

![image](https://user-images.githubusercontent.com/26432753/72310611-1259b380-367a-11ea-9009-ba3e6f18ee6d.png)

Comparing the accuracy for both features:

![image](https://user-images.githubusercontent.com/26432753/72310621-1685d100-367a-11ea-8895-c3e5cc333496.png)

Looking at the accuracy it is clear that new feature predicts males and females more accurately then the previous one.
