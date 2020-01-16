Objective:
The objective is to assess the impact of feature selection on training and test datasets.  Two datasets accompany this assignment, ​SPECT_train.csv ​and​ SPECT_test.csv​. The idea is to identify good feature subsets using the training dataset and test these subsets on the test data. In preparing wer submission, we should focus on explaining discrepancies between train and test performance rather than maximising performance.

Requirements:
  1. Use Gradient Boosting as wer classifier. 
  2. As a baseline, we should report performance (accuracy) on the train and test data using all features. The results on the training data can be based on cross validation. The results on the test data can be hold-out, i.e. train on train data and test on test data.  
  3. We should evaluate three alternative feature subset selection strategies: 
	a. One based on using information gain as a filter. 
	b. Wrapper-based forward sequential search. 
	c. Wrapper-based backward elimination. 
  4. At no stage should the test data be used in classifier training or in feature selection. 
  5. We should present a summary of wer results as a bar chart as shown below.  
  6. In discussing wer results, we should comment on the stability and consistency of the results coming from the three feature selection methods.  
  7. Our discussion should comment on the insights into the data that can be derived from the overall analysis.  