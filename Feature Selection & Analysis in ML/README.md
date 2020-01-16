# Feature Selection & Analysis in ML

The objective is to assess the impact of feature selection on training and test datasets.  Two datasets accompany this project, ​SPECT_train.csv ​and​ SPECT_test.csv​. The idea is to identify good feature subsets using the training dataset and test these subsets on the test data. 

### Requirements:
  1. Use Gradient Boosting as our classifier. 
  2. As a baseline, we should report performance (accuracy) on the train and test data using all features. The results on the training data can be based on cross validation. The results on the test data can be hold-out, i.e. train on train data and test on test data.  
  3. We should evaluate three alternative feature subset selection strategies: 
	a. One based on using information gain as a filter. 
	b. Wrapper-based forward sequential search. 
	c. Wrapper-based backward elimination. 
  4. At no stage should the test data be used in classifier training or in feature selection. 
  5. We should present a summary of our results as a bar chart as shown below.  
  6. In discussing our results, we should comment on the stability and consistency of the results coming from the three feature selection methods.  
  7. I will discuss on the insights into the data that can be derived from the overall analysis. 
  
### Implementation:

**Gradient Boosting**

Gradient Boosting builds an additive model in a forward stage-wise fashion; it allows for the optimization of arbitrary differentiable loss functions. In each stage nclasses regression trees are fit on the negative gradient of the binomial or multinomial deviance loss function.

After applying Gradient Boosting classifier

![image](https://user-images.githubusercontent.com/26432753/72554322-56270580-3892-11ea-9ed9-cebfd54ebd8e.png)
  
**Feature Selection**

In Feature selection we need to find the best subset of all available features, which contains the smallest number of features which contribute most to the accuracy. Discard the remaining, unimportant features.

**Feature Selection Strategies**

1. Filter: During Pre-processing step it ranks the features independently of the choice of classifier that will be subsequently applied. It returns a score value which is predictivness of the features.

Example: Information Gain, Gini index.

2. Wrapper: The classifier is “wrapped” in the feature selection mechanism. Feature subsets are evaluated directly based on their performance when used with that specific classifier. A key aspect of wrappers is the search strategy which generates the candidate feature subsets for evaluation. One of the feature search stratergy is Sequential search. Two type of sequential search are given below:
		
	1. Forward Sequential Selection: In this we start with an empty subset. Find the most informative feature and add it to the subset. Then repeat this process until there is no improvement by adding features.
	
	2. Backward Elimination: Start with the complete set of features. Then remove the least informative feature and repeat until there is no improvement by dropping features.

**Information Gain**

![image](https://user-images.githubusercontent.com/26432753/72554836-6390bf80-3893-11ea-9901-2e61c480e148.png)

**Selecting k Best Features**

![image](https://user-images.githubusercontent.com/26432753/72554898-81f6bb00-3893-11ea-9b6c-af9c80e8aa3e.png)

![image](https://user-images.githubusercontent.com/26432753/72554943-9470f480-3893-11ea-9c3e-92599dff2290.png)

![image](https://user-images.githubusercontent.com/26432753/72554979-a5ba0100-3893-11ea-90ce-f9b33b11d98d.png)


**Wrapper**

1. Wrapper approache are based on greedy search algorithms as they compare all possible combinations and pick the combination that produces the best outcome for a given machine learning algorithm.

2. Step Forward Feature Selection: In the first phase, the classifier's performance is evaluated in accordance with each feature. Of all the features, the features that performs the best is selected.

3. In next step, the first feature is then tested in combination with all other features. The resultant features that produce the best performance are selected.

**Wrapper-Forward**

![image](https://user-images.githubusercontent.com/26432753/72555151-f7fb2200-3893-11ea-9720-9a6e91889cbb.png)

Sequential forward selection

![image](https://user-images.githubusercontent.com/26432753/72555214-1103d300-3894-11ea-8248-dc133e347407.png)

![image](https://user-images.githubusercontent.com/26432753/72555284-2bd64780-3894-11ea-837f-0f2e5dc89c6d.png)

**Wrapper-Backward**

![image](https://user-images.githubusercontent.com/26432753/72555336-44466200-3894-11ea-9658-2839b3422f1f.png)

![image](https://user-images.githubusercontent.com/26432753/72555364-50caba80-3894-11ea-9e2b-ed2c8852c165.png)

![image](https://user-images.githubusercontent.com/26432753/72555384-5c1de600-3894-11ea-91fe-5c0653ee2b76.png)


### Conclusion

![image](https://user-images.githubusercontent.com/26432753/72555436-748e0080-3894-11ea-9fad-59f4c9e022c7.png)

Based on the resultant graph, the accuracy of the test dataset is similar throughout the selection strategy but the accuracy of the training dataset in the case of Wrapper-based methods eventually increases.

Filter methods may not find the best subset of features in cases where insufficient data are available to model the statistical correlation of features, but wrapper methods can always provide the best subset of features due to their exhaustive existence.
